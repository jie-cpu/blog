
---

## 📊 Raw fMRI vs. Organized Betas (.pkl)

| Feature | Raw fMRI Data | Organized Betas (.pkl) |
|---------|---------------|------------------------|
| **What it is** | Direct scanner output: BOLD signal over time | Statistical estimates from GLM analysis |
| **Dimensionality** | 4D (3D brain volume + time) | 2D (ROIs/voxels × conditions) |
| **Time information** | Yes (TR = 1-2 seconds, hundreds of time points) | No (time dimension compressed into beta estimates) |
| **File format** | `.nii` or `.nii.gz` (NIfTI) | `.pkl` (Python pickle) |
| **File size** | Large (several GB per run) | Small (tens to hundreds of MB) |
| **Human readability** | Binary, requires neuroimaging software | Loadable with Python's `pickle` |
| **Signal type** | Raw BOLD signal (arbitrary units) | Beta coefficients (standardized effect sizes) |
| **Noise level** | High (physiological noise, motion artifacts) | Low (after GLM denoising) |
| **What you see** | Blood flow fluctuations over time | "How strongly each condition activates each brain region" |
| **Use case** | Preprocessing, GLM fitting | RSA, MVPA, cross-modal alignment (your study) |

---

## 🔄 Processing Pipeline: Raw fMRI → Organized Betas

Here's how the raw fMRI data is transformed into your `.pkl` files:

```
Step 1: Raw Scanner Output                    Step 2: Preprocessing
┌─────────────────────┐                      ┌─────────────────────────┐
│ Raw fMRI (4D NIfTI) │                      │ Motion correction       │
│ - 100,000+ voxels   │  ──────────────────► │ Slice timing correction │
│ - 200-400 timepoints│                      │ Spatial normalization   │
│ - Several GB        │                      │ to MNI152 space         │
└─────────────────────┘                      └─────────────────────────┘
                                                           │
                                                           ▼
Step 5: Organized Betas (.pkl)                Step 3: GLM Fitting (GLMsingle)
┌─────────────────────┐                      ┌─────────────────────────┐
│ 2D matrix saved as  │                      │ For each voxel:         │
│ Python pickle file  │  ◄────────────────── │ Estimate beta for each  │
│ - Shape: (n_ROI,    │                      │ experimental condition  │
│   n_conditions)     │                      │ using design matrix     │
│ - Normalized across │                      │ + HRF convolution       │
│   subjects/conditions│                      └─────────────────────────┘
└─────────────────────┘                                  │
                                                          ▼
                                                Step 4: Denoising
                                          ┌─────────────────────────┐
                                          │ GLMsingle noise         │
                                          │ regression:             │
                                          │ - Remove physiological  │
                                          │   noise                 │
                                          │ - Correct for           │
                                          │   trial-to-trial        │
                                          │   variability           │
                                          │ - Normalize betas       │
                                          └─────────────────────────┘
```

---

## 📝 Detailed Step-by-Step Explanation

### **Step 1: Raw fMRI Acquisition**
- Participants watch 3-second video clips while inside an MRI scanner
- Scanner measures BOLD (Blood Oxygen Level Dependent) signal every 1-2 seconds (TR)
- Output: 4D matrix with dimensions [X, Y, Z, Time]

### **Step 2: Preprocessing**
- **Motion correction**: Align all timepoints to correct for head movement
- **Slice timing correction**: Adjust for different acquisition times of brain slices
- **Spatial normalization**: Warp individual brains into standard MNI152 template space (so data can be compared across subjects)

### **Step 3: GLM Fitting (GLMsingle)**
- **Design matrix**: Specify which video was shown at each timepoint
- **HRF convolution**: Model how blood flow responds to neural activity (hemodynamic response function)
- **Beta estimation**: For each voxel and each condition (video), solve the GLM equation:
  
  `Y = X × β + ε`
  
  where:
  - Y = observed BOLD signal
  - X = design matrix (when each video was shown)
  - β = beta coefficient (what we want: brain response strength)
  - ε = error/noise

### **Step 4: Denoising & Normalization (GLMsingle specific)**
- **Noise regression**: Remove physiological noise (heartbeat, breathing)
- **Cross-validation**: Estimate noise ceilings and reliability
- **Normalization**: Scale betas so they are comparable across subjects and conditions

### **Step 5: Organized Output (.pkl)**
- Reshape beta maps from 3D volume to 2D matrix
- Save as Python pickle file for easy loading
- Shape: `(n_conditions, n_voxels)` or `(n_ROIs, n_conditions)`

---

## 🧪 Simple Analogy

| Stage | Analogy |
|-------|---------|
| **Raw fMRI** | Recording a movie of someone's facial expressions while they watch videos |
| **GLM fitting** | Analyzing the movie frame-by-frame to measure "how happy did they look during each video?" |
| **Organized Betas** | A spreadsheet with one row per video, one column per facial muscle, containing a single number: "smile intensity score" |

---

## ✅ For Your Research

**You need the `.pkl` files (organized betas), NOT the raw fMRI.**

Why?
1. **Better signal-to-noise** → cleaner embeddings for alignment
2. **Standardized across subjects** → can average or compare
3. **Already denoised** → GLMsingle is state-of-the-art for this dataset
4. **Computationally feasible** → 2D matrix instead of 4D volume

The paper specifically recommends **Version B** (GLMsingle-processed) for cross-modal analysis like yours.