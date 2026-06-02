# Detailed Guide to Pickle File Structure

## TL;DR - What's Inside Each Pickle File

### Train PKL: `sub-01_organized_betas_task-train_normalized.pkl`
  

```python

(

betas: ndarray (1000, 3, 108219), # 1000 videos × 3 conditions × 108k voxels

vids: list of 1000 strings, # ['vid0001', 'vid0002', ..., 'vid1000']

mask: Nifti1Image (62, 77, 61), # Brain mask + affine for MNI coord transform

)

```

**Contains**: Training set with 1000 videos, 3 beta conditions each.

---
### Test PKL: `sub-01_organized_betas_task-test_normalized.pkl`

```python

(

betas: ndarray (102, 10, 108219), # 102 videos × 10 conditions × 108k voxels

vids: list of 102 strings, # ['vid1001', 'vid1002', ..., 'vid1102']

mask: Nifti1Image (62, 77, 61), # Same brain mask + affine (identical to train)

)

```
  **Contains**: Test set with 102 videos, 10 beta conditions each.
---
### Key Differences
| Aspect | Train | Test |

|--------|-------|------|

| **Videos** | 1000 | 102 |

| **Beta conditions** (axis 1) | 3 | 10 |

| **Voxels per video** (axis 2) | 108,219 | 108,219 |

| **Video ID range** | vid0001–vid1000 | vid1001–vid1102 |

| **Brain mask** | Identical | Identical |

| **Total beta values** | 324.7M | 110.4M |
---
## Detailed Breakdown
## Element [0]: Beta Coefficients
**What**: GLM regression coefficients (brain activation values)
**Shape** (videos × conditions × voxels):

- Train: (1000, 3, 108219)

- Test: (102, 10, 108219)
**Axes**:

- Axis 0: Video index → maps to vids[i]

- Axis 1: Beta conditions (3 train / 10 test) — different preprocessing stages

- Axis 2: Voxel index (108,219) — brain tissue inside mask
**Data type**: float64 | **Range**: ≈ [-9.62, 9.88]
**Quick access**:

```python

betas[video_idx, :, :] # All conditions for one video

betas[video_idx, cond, :] # One condition, one video → (108219,)

```
---
## Element [1]: Video Identifiers

**What**: List of video ID strings

**Content**:
- Train: 1000 IDs (vid0001–vid1000)

- Test: 102 IDs (vid1001–vid1102)

**Key property**: Order preserved — `betas[i]` ↔ `vids[i]` ↔ `ann[vids[i][3:]]`
**Map to annotations.json**:

```python

key = vids[i][3:] # Remove "vid" prefix (e.g., 'vid0001' → '0001')

metadata = ann[key]

```

---

## Element [2]: Brain Mask (Nifti1Image)

**What**: 3D brain mask + affine transformation matrix

**Mask data**:

- Shape: (62, 77, 61) voxels

- Values: Binary [0, 1] → 1 = voxel in analysis

- Selected: 108,219 / 291,094 (37.2% brain tissue)

**Affine matrix** (4×4) — transforms voxel indices ↔ MNI152 mm:

```

[[ 2.5 0. 0. -76. ]

[ 0. 2.5 0. -112. ]

[ 0. 0. 2.75 -78. ]

[ 0. 0. 0. 1. ]]

```

Voxel size: 2.5 × 2.5 × 2.75 mm³
**Get all MNI coordinates (108,219):**
```python

mask_data = brain_mask.get_fdata()

voxel_coords = np.where(mask_data > 0) # Get voxel indices

voxel_matrix = np.column_stack(voxel_coords) # (108219, 3)

voxel_homo = np.hstack([voxel_matrix, np.ones((108219, 1))]) # Homogeneous

mni_coords = (brain_mask.affine @ voxel_homo.T).T[:, :3] # (108219, 3) mm

```
---
## Complete Workflow: From Pickle to Brain Space

Here's an example combining all three elements:
```python

import json

import pickle

import numpy as np

  

# Load all data

ann = json.load(open("annotations.json", "r", encoding="utf-8"))

betas, vids, brain_mask = pickle.load(

open("GLM/sub-01/prepared_betas/sub-01_organized_betas_task-train_normalized.pkl", "rb")

)

  

# 1. Select a video

video_idx = 0

video_id = vids[video_idx] # 'vid0001'

ann_key = video_id[3:] # '0001'

metadata = ann[ann_key] # Rich annotations (scenes, objects, etc.)

  

# 2. Get brain activation for this video

activation_all_conditions = betas[video_idx, :, :] # shape (3, 108219)

  

# 3. Get spatial coordinates for each voxel

mask_data = brain_mask.get_fdata()

voxel_coords = np.where(mask_data > 0)

voxel_matrix = np.column_stack(voxel_coords) # shape (108219, 3)

voxel_homo = np.hstack([voxel_matrix, np.ones((108219, 1))])

mni_coords = (brain_mask.affine @ voxel_homo.T).T[:, :3] # shape (108219, 3)

  

# 4. Create a DataFrame combining everything

import pandas as pd

  

for cond_idx in range(activation_all_conditions.shape[0]):

df = pd.DataFrame({

'video_id': video_id,

'annotation_key': ann_key,

'memorability': metadata['memorability_score'],

'condition': cond_idx,

'voxel_idx': np.arange(108219),

'mni_x': mni_coords[:, 0],

'mni_y': mni_coords[:, 1],

'mni_z': mni_coords[:, 2],

'beta_activation': activation_all_conditions[cond_idx, :]

})

print(f"Condition {cond_idx}: {len(df)} voxels")

```

  

---

  

## Quick Reference

  

| Metric | Train | Test |

|--------|-------|---------|

| **Videos** | 1000 | 102 |

| **Beta conditions** | 3 | 10 |

| **Betas per video** | 324k | 1.08M |

| **Total values** | 324.7M | 110.4M |

| **File size** | ~2.5 GB | ~0.85 GB |

| **Video ID range** | vid0001–vid1000 | vid1001–vid1102 |

  

**Brain**: 108,219 voxels selected (37.2% of full 62×77×61 volume)

  

---

  

## Common Pitfalls & Tips

  

### ✅ DO

  

- **Preserve row order**: Don't shuffle betas without shuffling vids simultaneously

- **Use float precision**: Keep betas as float64 for statistical analyses

- **Cache coordinates**: Pre-compute all 108,219 MNI coordinates once, not per-video

- **Check alignment**: Always verify `betas.shape[2] == (mask_data > 0).sum()`

  

### ❌ DON'T

  

- **Reshape the mask**: The (62, 77, 61) shape is standardized; changing it breaks affine mapping

- **Assume axis 1 meaning**: Don't hard-code interpretation of the 3 vs 10 conditions; document it separately

- **Lose the affine**: Without the affine matrix, voxel indices are meaningless for neuroscience

- **Mix train/test**: The two PKL files use different coordinate systems (3 vs 10 conditions)

  

---

  

## Related Files

  

- `annotations.json` — Video metadata to join with betas

- `annotation_beta_mapping.md` — Quick reference for row alignment

- MNI152 template images — For visualization/reference (not in this repo)