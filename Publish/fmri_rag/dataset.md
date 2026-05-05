
## Dataset Overview: BOLD Moments Dataset (BMD)

| Property         | Details                                                                 |
| ---------------- | ----------------------------------------------------------------------- |
| **Full Name**    | BOLD Moments Dataset                                                    |
| **Publication**  | *Nature Communications* (2024)                                          |
| **Subjects**     | 10 human adults                                                         |
| **Stimuli**      | 1,102 short videos (3 seconds each)                                     |
| **Total Trials** | 40,200 single-trial responses                                           |
| **Access**       | OpenNeuro (ds005165) – Open access, no application required             |
| **License**      | Open access (stimulus video download requires agreeing to terms of use) |

---

## Phase 1: Baseline System (Offline Index Building)

| Phase       | Step                            | Dataset Component                      | Description                                                                                               | Size / Format                             |
| ----------- | ------------------------------- | -------------------------------------- | --------------------------------------------------------------------------------------------------------- | ----------------------------------------- |
| **Phase 1** | Raw fMRI Input                  | BMD version B (GLMsingle preprocessed) | Whole-brain fMRI BOLD responses to 1,102 videos; higher quality with better registration                  | MNI152 volume space, z-scored per session |
| **Phase 1** | Preprocessed Signals            | BMD version B derivatives              | Ready-to-use fMRI time series; recommended for analysis                                                   | NIfTI format                              |
| **Phase 1** | Text Annotations (for indexing) | Human-annotated metadata               | Five sentence-level text descriptions per video (13 words avg); spoken transcriptions (27 words avg)      | CSV / JSON files                          |
| **Phase 1** | Word-level labels (alternative) | Object + Scene + Action labels         | 15 object labels + scene labels + action labels per video (from Places365, THINGS, Multi-Moments in Time) | CSV files                                 |

**Note for Phase 1 - Train/Test Split**: 
- Training set: 1,000 videos
- Testing set: 102 videos

---

## Phase 2: RAG System (Retrieval + Generation)

| Phase | Step | Dataset Component | Description | Purpose in RAG |
|-------|------|-------------------|-------------|----------------|
| **Phase 2** | Vector Database (Index) | BMD fMRI responses (training set) | fMRI vectors from 1,000 videos, each paired with text descriptions | **Retrieval corpus** — historical brain events to search |
| **Phase 2** | Query Input | BMD fMRI responses (test set) | New/unseen fMRI samples from the 102 test videos | **Query** — what you want to decode |
| **Phase 2** | Ground Truth for Evaluation | BMD text annotations (test set) | Sentence descriptions for the 102 test videos | **Evaluation** — compare generated text against ground truth |
| **Phase 2** | Optional: Memorability Scores | BMD behavioral metadata | Memorability score (0.84 mean) and decay rate per video | **Auxiliary analysis** — test if memorable events are retrieved more accurately |

---

## Phase 3: Evaluation & Analysis

| Phase | Dataset Component | Description | Use |
|-------|-------------------|-------------|-----|
| **Phase 3** | Test set predictions | Your model's outputs on 102 videos | BLEU / ROUGE / BERTScore calculation |
| **Phase 3** | Ground truth labels | Original sentence descriptions | Reference for metric computation |
| **Phase 3** | (Optional) Video features | M4 TSM ResNet50 features from BMD GitHub | Compare retrieval results against visual similarity baseline |

---

## Summary Table: What Data for What Stage

| Pipeline Stage                      | What Data You Need                     | Where to Find It                        |
| ----------------------------------- | -------------------------------------- | --------------------------------------- |
| **Build fMRI Encoder**              | fMRI responses (1,000 training videos) | BMD version B `/derivatives`            |
| **Build Text Embeddings**           | Sentence descriptions for 1,000 videos | BMD metadata files                      |
| **Create Vector Index**             | fMRI embeddings + text embeddings      | Your code output                        |
| **Run RAG Retrieval**               | Test fMRI (102 videos)                 | BMD test split                          |
| **Evaluate Generation**             | Ground truth text for 102 videos       | BMD test metadata                       |
| **(Optional) Video Encoding Model** | Video stimuli + fMRI                   | BMD stimulus set + M4 TSM ResNet50 code |

---

## Download Instructions

### fMRI Data (OpenNeuro)
```bash
# Using AWS CLI (recommended)
aws s3 sync --no-sign-request s3://openneuro.org/ds005165 /your/local/path

# Using openneuro-py
pip install openneuro-py
openneuro download ds005165 --target ./bmd_data
```

**Recommended**: Download only `version B` derivatives (higher quality)

### Stimulus Videos
- Visit the BMD stimulus download page (link in GitHub README)
- Read and agree to the terms of use
- Download with the provided password

### Starter Code
```bash
git clone https://github.com/blahner/BOLDMomentsDataset.git
```

---

## One-Sentence Summary

> **The BOLD Moments Dataset provides everything you need in one place: fMRI responses to 1,102 short videos + rich text annotations (sentence descriptions, object/scene/action labels, spoken transcriptions) + behavioral memorability scores. Train on 1,000 videos, test on 102 — no need to combine multiple datasets.**

---
