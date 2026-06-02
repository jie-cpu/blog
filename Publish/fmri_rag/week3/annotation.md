
## ✅ The One File You Need

| File | Why You Need It |
| :--- | :--- |
| **`annotations.json`** | Contains the **5 human-annotated sentence descriptions** for each of the 1,102 videos. This is the text data you will pair with your fMRI betas for training MindLLM. |

---

## ❌ Files You Can Ignore (for your current project)

| File/Folder | Why You Can Ignore It |
| :--- | :--- |
| `annotations_fieldnames.json` | Just a description of the fields, not the actual data |
| `llm_frame_annotations.json` | Contains **machine-generated** captions (GIT model) for a **single frame**, not human descriptions of the full 3-second video. The paper shows human descriptions correlate better with brain activity. |
| `ME_feats_matlab/` | Motion energy features – not needed for text-based MindLLM |
| `frames/` | Video frames – not needed for text embedding |
| `stimuli/` | The actual .mp4 videos – not needed for text embedding (only if you need video features) |
| `mp4_h264/` | Compressed videos – not needed |
| `frames_middle/` | Middle frame images – not needed |
| `stimuli_access.txt` | Password for video download – not needed (you don't need videos) |

---

## 📋 Summary Table

| Your Goal | File to Use |
| :--- | :--- |
| **Text descriptions for fMRI-text alignment** | `annotations.json` ✅ |
| Video features (if you add video modality later) | `stimuli/` folder (requires password) |
| Machine-generated single-frame captions | `llm_frame_annotations.json` (not recommended) |

---

## 📂 Final Path for Your Project

```
./derivatives/stimuli_metadata/
└── annotations.json    # ← THIS IS YOUR TEXT DATA
```

**One file. That's all you need from the `stimuli_metadata` folder.**