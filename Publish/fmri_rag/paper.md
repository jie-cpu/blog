## Core Papers (Must Read)

### 1. fMRI-LM: Towards a Universal Foundation Model for Language-Aligned fMRI Understanding
- **Authors**: Yuxiang Wei, Yanteng Zhang, Xi Xiao, et al.
- **Venue**: arXiv 2025
- **Link**: https://arxiv.org/abs/2511.21760
- **Why important**: Three-stage framework mapping fMRI to discrete tokens embedded in language space; constructs descriptive corpus for fMRI→text description. Core reference for your RAG indexing pipeline .

### 2. MindLLM: A Subject-Agnostic and Versatile Model for fMRI-to-Text Decoding
- **Authors**: Weikang Qiu, et al.
- **Venue**: ICML 2025 / arXiv:2502.15786
- **Link**: https://arxiv.org/abs/2502.15786
- **Why important**: fMRI encoder + off-the-shelf LLM with neuroscience-informed attention mechanism; handles variable input shapes across subjects. Code available at https://github.com/Graph-and-Geometric-Learning/ .

### 3. Semantic reconstruction of continuous language from non-invasive brain recordings
- **Authors**: Jerry Tang, Amanda LeBel, Shailee Jain, Alexander G. Huth
- **Venue**: Nature Neuroscience, 2023, 26(5):858-866
- **Link**: https://www.nature.com/articles/s41593-023-01304-9
- **DOI**: 10.1038/s41593-023-01304-9
- **Why important**: Foundational work proving fMRI can reconstruct continuous language from cortical semantic representations .

---

## Dataset Paper

### 4. Modeling short visual events through the BOLD moments video fMRI dataset and metadata (BOLD Moments Dataset - BMD)
- **Authors**: Benjamin Lahner, Kshitij Dwivedi, Polina Iamshchinina, et al.
- **Venue**: Nature Communications, Vol 15, Article 1-26, 2024
- **Link**: https://www.nature.com/articles/s41467-024-50310-3
- **DOI**: 10.1038/s41467-024-50310-3
- **Why important**: 10 subjects, 1,102 fMRI responses to 3-second videos with sentence-level text descriptions, object/scene/action labels, and memorability scores. Your primary dataset .

---

## RAG & Retrieval Related

### 5. QA-Emb: Question Answering as an Embedding Model
- **Venue**: NeurIPS 2024
- **Why important**: Uses LLM-generated yes/no questions to create interpretable embeddings; relevant for making your retrieval interpretable (each dimension corresponds to a human-readable question).

### 6. Brain-Aug: fMRI-Augmented Text Retrieval
- **Venue**: ACM MM 2024
- **Why important**: Directly uses fMRI signals to enhance text queries. Closest existing work to your RAG-fMRI idea.

---

## Additional References (Useful for Background)

### 7. BrainCodec: Neural fMRI codec for the decoding of cognitive brain states
- **Authors**: Amano Lab
- **Venue**: arXiv 2024
- **Link**: https://arxiv.org/abs/2410.04383
- **Why important**: fMRI compression and denoising method; code and weights available at https://github.com/amano-k-lab/BrainCodec .

### 8. BrainDEC: A Multimodal LLM for the Non-Invasive Decoding of Text from Brain Recordings
- **Venue**: arXiv 2024
- **Why important**: Direct "fMRI + multimodal LLM" decoding pipeline with instruction tuning.

---

## Summary Table

| Paper                   | Venue          | Link                                               | In Your Pipeline                       |
| ----------------------- | -------------- | -------------------------------------------------- | -------------------------------------- |
| fMRI-LM                 | arXiv 2025     | https://arxiv.org/abs/2511.21760                   | fMRI Encoder + Descriptive Corpus      |
| MindLLM                 | ICML 2025      | https://arxiv.org/abs/2502.15786                   | fMRI Encoder + Subject-Agnostic Design |
| Semantic Reconstruction | Nat Neuro 2023 | https://www.nature.com/articles/s41593-023-01304-9 | Foundational Baseline                  |
| BOLD Moments Dataset    | Nat Comm 2024  | https://www.nature.com/articles/s41467-024-50310-3 | Your Primary Dataset                   |
| QA-Emb                  | NeurIPS 2024   | (searchable)                                       | Interpretable Retrieval                |
| Brain-Aug               | ACM MM 2024    | (searchable)                                       | RAG Reference                          |
| BrainCodec              | arXiv 2024     | https://arxiv.org/abs/2410.04383                   | fMRI Compression (optional)            |

---

Reading Order

1. **Week 1**: Semantic Reconstruction (Nature Neuro 2023) → Understand the foundation
2. **Week 2**: MindLLM (ICML 2025) + fMRI-LM (arXiv 2025) → Understand modern architectures
3. **Week 3**: BOLD Moments Dataset paper (Nature Comm 2024) → Understand your data
4. **Week 4**: QA-Emb + Brain-Aug → Understand RAG for brain signals

---
