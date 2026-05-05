## Project: Retrieval‑Augmented Generation (RAG) for fMRI‑to‑Text Decoding

### 1. Core Idea
Build a **retrieval‑augmented generation (RAG) system** that uses a pre‑trained fMRI encoder (e.g., MindLLM, fMRI‑LM) and an LLM (e.g., Gemma, Llama) to decode natural language from brain activity.  
The key novelty is that the system **retrieves semantically similar historical brain‑event descriptions** from a vector database and uses them as contextual evidence to improve the LLM’s decoding accuracy.  
### 2. Why This is Feasible (Technical Backing)

- **fMRI → text decoding already works**  
  *Semantic reconstruction of continuous language* (Tang et al., *Nature Neuroscience* 2023) – the seminal work that reconstructs perceived language from fMRI.

- **Pre‑trained fMRI encoders + LLMs exist**  
  - *MindLLM* (ICML 2025) – subject‑agnostic fMRI encoder + off‑the‑shelf LLM.  
  - *fMRI‑LM* (arXiv 2025) – three‑stage foundation model that maps fMRI to language tokens.  
  - *BrainDEC* (arXiv 2024) – multimodal LLM for text decoding from brain recordings.

- **Retrieval‑augmented brain decoding is an emerging direction**  
  - *QA‑Emb* (NeurIPS 2024) – uses LLM‑generated yes/no questions to create interpretable embeddings, shown to improve fMRI prediction.  
  - *Brain‑Aug* (ACM MM 2024) – directly enhances text queries with fMRI signals.

- **All required models are already pre‑trained** → No need to train heavy models; the work focuses on **integration and systematic evaluation**.

### 3. Required Resources (What I Need to Provide)

| Resource                       | Provided by                                                                                              | Status                                  |
| ------------------------------ | -------------------------------------------------------------------------------------------------------- | --------------------------------------- |
| **Pre‑trained fMRI encoder**   | MindLLM / fMRI‑LM (open‑source)                                                                          | ✅ Available                             |
| **Pre‑trained LLM**            | Llama 3 / Gemma / OpenAI API                                                                             | ✅ Available                             |
| **Text embedding model**       | Sentence‑BERT / QA‑Emb                                                                                   | ✅ Available                             |
| **Vector database**            | FAISS / Chroma                                                                                           | ✅ Open‑source                           |
| **Public fMRI + text dataset** | BOLD Moments Dataset (Nature Communications 2024) – 1,102 short video events, each with rich text labels | ✅ Open‑access (no application required) |
| **Hardware**                   | 1 GPU (e.g., RTX 3090/4090)                                                                              | To be confirmed                         |

### 4. Work Plan (4–5 months)

#### Phase 1: Baseline System (Weeks 1–3)
- Set up environment and download the BOLD Moments Dataset.
- Run a pre‑trained fMRI encoder + LLM to obtain baseline decoding performance (BLEU/ROUGE/BERTScore).
- Confirm that the baseline is reproducible.

#### Phase 2: RAG System (Weeks 4–7)
- Build a vector index (FAISS) of training‑set fMRI descriptors (text descriptions from the dataset).
- Implement retrieval: given a new fMRI sample, retrieve the top‑K most similar historical events.
- Feed the retrieved texts as context into the LLM for decoding.

#### Phase 3: Evaluation & Writing (Weeks 8–12)
- Compare baseline vs. RAG: demonstrate improvement with statistical significance.
- Run ablation studies (effect of K, different text granularity, etc.).
- Write the Master’s thesis.

### 5. Potential Concerns & Mitigations

| Concern | Mitigation |
|---------|-------------|
| “People have already done fMRI + LLM” | Yes, but **RAG for fMRI‑to‑text is not systematically studied**. My contribution is showing that retrieval adds value. |
| “Dataset may be too short or not diverse enough” | BOLD Moments Dataset provides **1,102 independent 3‑second events** – ideal for RAG index construction, unlike long continuous narratives. |
| “Do I need to train models?” | **No.** All models are pre‑trained; I will use them as is, focusing on the retrieval integration. |
| “Is a single GPU sufficient?” | Yes. All inference‑only steps (encoding, retrieval, LLM generation) fit on one RTX 3090/4090. |

### 7. Next Steps (If You Approve)

1. **Confirm resources** – access to 1 GPU and ~200‑500 GB storage.
2. **Download the BOLD Moments Dataset** (open‑acces?).
3. **Run baseline** – reproduce MindLLM or fMRI‑LM on this dataset.
4. **Implement RAG** – build FAISS index + retrieval pipeline.
5. **Write report** with comparison experiments.

---

## 

> **Topic:** Retrieval‑Augmented Generation (RAG) for fMRI‑to‑Text Decoding  
> **Core idea:** Use a pre‑trained fMRI encoder + LLM + vector retrieval (FAISS) to decode natural language from brain signals. The system first retrieves semantically similar historical brain‑event descriptions and then uses them as context for the LLM – turning closed‑book decoding into open‑book decoding.  
> **Feasibility:**  
> - Published work already validates fMRI→text (Tang et al., Nat Neurosci 2023), pre‑trained fMRI encoders (MindLLM, fMRI‑LM), and retrieval‑augmented brain processing (QA‑Emb, Brain‑Aug).  
> - All models are pre‑trained – my role is integration and evaluation.  
> - Open dataset: BOLD Moments Dataset (1,102 short video events + rich text labels) – no application needed.  
> **Plan:** Baseline (3 weeks) → RAG (4 weeks) → experiments & writing (5 weeks).  
> **Request:** Access to 1 GPU and your supervision. I can provide a detailed 1‑page Exposé.
