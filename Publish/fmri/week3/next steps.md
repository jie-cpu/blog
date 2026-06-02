

### Prepare BMD Data for MindLLM (Static Format)

Your raw data has the shape `(n_videos, n_repetitions, n_voxels)`. MindLLM requires a simple 2D matrix of shape `(n_samples, n_voxels)`.

Here are the specific steps:

1.  **Load the data** from `sub-XX_organized_betas_task-train_normalized.pkl` and the `_test_` version.
2.  **Reshape the `betas` array** from 3D to 2D. Merge the first two dimensions (`n_videos` and `n_repetitions`) into a single `n_samples` dimension.
    *   **Training set:** `(1000, 3, 108219)` ➔ `(3000, 108219)`
    *   **Testing set:** `(102, 10, 108219)` ➔ `(1020, 108219)`
3.  **Create the final input dictionary** for MindLLM. It must contain at least the reshaped `'values'` and the `'coords'` from the original pickle file (no mask needed).
4.  **Pair each sample with text** from `stimuli_metadata/annotations.json` using the `video_id` from your `trial_info`.

### 🚀 The Core Python Code

```python
# Load your data
with open('sub-01_organized_betas_task-train_normalized.pkl', 'rb') as f:
    train_data = pickle.load(f)

# The critical step: reshape to 2D
n_voxels = train_data['betas'].shape[-1]
train_values_2d = train_data['betas'].reshape(-1, n_voxels) # Shape becomes (3000, 108219)

# Package for MindLLM
mindllm_train_input = {
    'values': train_values_2d,        # The 2D matrix
    'coords': train_data['coords']    # Voxel coordinates from the file
}
```

### ✅ Summary

| Your Data's Current Shape | MindLLM's Required Shape | Action |
| :--- | :--- | :--- |
| `(1000, 3, 108219)` | `(3000, 108219)` | **Reshape** (flatten the first two dimensions) |
| `(102, 10, 108219)` | `(1020, 108219)` | **Reshape** (flatten the first two dimensions) |

That is the only major transformation you need. The `'coords'` from your pickle file are ready to use, and you do not need an external mask. After reshaping, your data will be in the correct static format for MindLLM.

Does this summary match your understanding? Would you like the code to also handle flattening the `trial_info` to match the new sample order?