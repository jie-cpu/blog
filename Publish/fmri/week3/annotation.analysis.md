## 📊 Summary: What You Need vs. What You Don't

### ✅ **USE THESE** (Core for your research)

| File/Field              | Location                                                 | Purpose                                            | Priority |
| ----------------------- | -------------------------------------------------------- | -------------------------------------------------- | -------- |
| **organized_betas.pkl** | `derivatives/versionB/MNI152/GLM/sub-XX/prepared_betas/` | fMRI brain responses to videos (Beta coefficients) | ⭐⭐⭐⭐⭐    |
| **text_descriptions**   | Inside `annotations.json`                                | 5 human-written sentences per video                | ⭐⭐⭐⭐⭐    |
| **set** (train/test)    | Inside `annotations.json`                                | Split data for training vs. evaluation             | ⭐⭐⭐⭐⭐    |
| **bmd_matrixfilename**  | Inside `annotations.json`                                | Links video ID → fMRI beta column                  | ⭐⭐⭐⭐⭐    |

### 🔶 **OPTIONAL** (May help, but not required)

| File/Field | Location | Purpose | When to use |
|------------|----------|---------|-------------|
| **actions** | Inside `annotations.json` | Action labels (e.g., "swimming") | Auxiliary training or filtering |
| **objects** | Inside `annotations.json` | Object labels (e.g., "squirrel") | Interpretability or multi-task learning |
| **scenes** | Inside `annotations.json` | Scene labels (e.g., "forest") | Contextual grounding |

### ❌ **SKIP THESE** (Not relevant for your goal)

| File/Field | Reason to Skip |
|------------|----------------|
| **Raw fMRI NIfTI files** | Too large, noisy, not preprocessed |
| **memorability_score / memorability_decay** | Cognitive property, not semantic content |
| **spoken_transcription** | Audio content (not in your pipeline) |
| **MiT_url, MiT_filename** | Source metadata only |
| **THINGS_uniqueID, PLACES365_classID, MiT_classID** | Taxonomy IDs (human-readable labels already available) |
| **contrasts_tvalues.pkl** | Different statistical measure (you need betas) |
| **noiseceiling_*.pkl** | Quality control, not for alignment training |

---

## 📁 Final File Checklist

```
Your download should include ONLY these:

derivatives/versionB/MNI152/GLM/
├── sub-01/prepared_betas/
│   ├── sub-01_organized_betas_task-train_normalized.pkl  ✅
│   └── sub-01_organized_betas_task-test_normalized.pkl   ✅
├── sub-02/prepared_betas/
│   ├── sub-02_organized_betas_task-train_normalized.pkl  ✅
│   └── sub-02_organized_betas_task-test_normalized.pkl   ✅
├── ... (sub-03 to sub-10)                                 ✅
│
derivatives/stimuli_metadata/
└── annotations.json                                       ✅

Total: 20 .pkl files + 1 .json file
```

---

## 🎯 One-Sentence Summary

> **You need the `organized_betas.pkl` files (fMRI responses) + `text_descriptions` from `annotations.json` (text labels) + the `set` and `bmd_matrixfilename` fields (to split and match data) — everything else is optional or unnecessary for your text-fMRI alignment research.**