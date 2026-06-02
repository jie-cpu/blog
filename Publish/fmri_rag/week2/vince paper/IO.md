## Stage 1: fMRI Tokenizer Training1

| Item                    | Content                                                                                                      |
| ----------------------- | ------------------------------------------------------------------------------------------------------------ |
| **Input**               | Preprocessed fMRI matrix `X ∈ ℝ^{160×450}` (160 time points, 450 ROIs)                                       |
| **Auxiliary Input**     | General text (e.g., OpenWebText) with embeddings extracted by a **frozen GPT-2 text encoder**                |
| **Trainable Modules**   | fMRI Tokenizer (ViT encoder + vector quantizer + lightweight decoder)                                        |
| **Frozen Modules**      | Text encoder (GPT-2)                                                                                         |
| **Training Objectives** | Reconstruction loss + contrastive alignment loss + domain-adversarial loss                                   |
| **Output**              | Discrete token sequence `z~ ∈ ℝ^{5×450}` (5 time windows, 450 tokens per window) + trained tokenizer weights |

---

## Stage 2: LLM Fine-Tuning and Temporal Modeling

| Item                    | Content                                                                                                                                                |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Input**               | Discrete token sequence from Stage 1 (from fMRI) + synthetic text descriptions (generated from four domains: FC, FG, graph theory, ICA) + general text |
| **Trainable Modules**   | Pretrained LLM (GPT-2 124M, can be fully fine-tuned or use LoRA)                                                                                       |
| **Frozen Modules**      | Stage 1 trained fMRI Tokenizer                                                                                                                         |
| **Training Objectives** | F2F (fMRI→fMRI prediction, weight α=0.1) + F2T (fMRI→text generation, weight 1.0) + T2T (text→text, weight β=0.5)                                      |
| **Output**              | Fine-tuned LLM capable of understanding fMRI token sequences and generating text descriptions from fMRI                                                |

---

## Stage 3: Multi-Task Instruction Tuning

|Item|Content|
|---|---|
|**Input**|fMRI token sequence + natural language instructions (three paradigms: single Q&A, multi Q&A, open-ended generation)|
|**Auxiliary Input**|High-level semantic descriptions constructed from demographics, phenotypic, cognitive, and physical attributes (**Stage 3 only**)|
|**Trainable Modules**|LLM (continued fine-tuning, full or LoRA)|
|**Frozen Modules**|Stage 1 trained fMRI Tokenizer|
|**Task Types**|Classification (sex, disease diagnosis, etc.), regression (age, cognitive scores, etc.), open-ended text generation|
|**Output**|Final model capable of answering various natural language questions and performing downstream tasks (zero-shot, few-shot, full supervision)|

---
