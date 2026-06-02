These fields represent **rich multimodal annotations** for each video in the BOLD-Moments dataset. Here's what they are and why they're included:

| Field                     | Purpose                                                       | Why it's there                                                                                     |
| ------------------------- | ------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| **bmd_matrixfilename**    | Internal identifier (e.g., "vid_idx0001")                     | Links to the corresponding fMRI beta values in the GLM analysis                                    |
| **MiT_url, MiT_filename** | Source video location                                         | The videos come from the **Moments in Time** (MiT) dataset—a large-scale video corpus from MIT-IBM |
| **set**                   | Train/test split                                              | For supervised learning / model evaluation                                                         |
| **objects**               | Multiple lists of detected objects per frame                  | Provides visual grounding; useful for understanding what brain regions activate                    |
| **scenes**                | Scene categories (e.g., "pond", "garage/indoor", "kitchen")   | Contextualize the video environment; scenes may activate different brain regions                   |
| **actions**               | Action labels (e.g., "swimming", "dancing", "eating/feeding") | Core semantic content; predicts which motor/sensory brain areas respond                            |
| **text_descriptions**     | Human-written descriptions                                    | Language-based label; enables text-to-brain analysis                                               |
| **spoken_transcription**  | Audio transcription                                           | Speech content; activates language and auditory cortices                                           |
| **memorability_score**    | Numeric [0–1] rating                                          | Measure of how well humans remember the video; predicts memory-related brain activity              |
| **memorability_decay**    | Rate of forgetting over time                                  | Temporal dynamics of memory encoding in the brain                                                  |
| **THINGS_uniqueID**       | References to THINGS object taxonomy                          | Standardized object labels for cross-dataset comparison                                            |
| **PLACES365_classID**     | Scene class IDs from PLACES365                                | Standardized scene taxonomy (same as MiT uses)                                                     |
| **MiT_classID**           | Action class IDs from Moments in Time                         | Action class taxonomy; e.g., "46" = driving, "160" = swimming                                      |

**Why all of this?**

The BOLD-Moments dataset is designed for **multimodal brain decoding**—predicting brain activity (beta values) from:
- Visual content (objects, scenes)
- Semantics (actions, text descriptions)
- Audio (transcription)
- Cognitive properties (memorability)

The annotations enable researchers to correlate which aspects of a video trigger specific neural responses.