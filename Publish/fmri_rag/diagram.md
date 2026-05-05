- ## RAG Inference (Online)
```mermaid
flowchart TB
    A[Raw fMRI Signals] --> B[Preprocessing]
    C[Text Annotations] --> D[Text Encoder<br/>Sentence-BERT]
    B --> E[fMRI Encoder<br/>MindLLM or fMRI-LM]
    E --> F[fMRI Embedding]
    D --> G[Text Embedding]
    F --> H[Vector Database<br/>FAISS]
    G --> H
    H --> I[Index Ready]
```
- ## RAG Inference (Online)
```mermaid
flowchart TB
    A[New fMRI Scan] --> B[fMRI Encoder<br/>MindLLM or fMRI-LM]
    B --> C[Query Vector]
    C --> D[FAISS Similarity Search]
    D --> E[Top-K Similar Texts]
    E --> F[Build Prompt with Retrieved Texts]
    F --> G[LLM Generation<br/>Gemma-2B or Llama-3-8B]
    G --> H[Decoded Text]
    H --> I[BELU / ROUGE Evaluation]
```

- ## Diagram 3: End-to-End Pipeline
```mermaid
flowchart LR
    subgraph Offline
        X[Historical fMRI + Text] --> Y[Encoders] --> Z[Vector DB]
    end
    subgraph Online
        M[New fMRI] --> N[Encode] --> O[Retrieve] --> P[LLM] --> Q[Output Text]
    end
    Z -.-> O
```




|Component|Model|Source|
|---|---|---|
|fMRI Encoder|MindLLM or fMRI-LM|GitHub (open source)|
|Text Encoder|Sentence-BERT|`sentence-transformers`|
|Vector Database|FAISS|`pip install faiss-gpu`|
|LLM Generator|Gemma-2B or Llama-3-8B|HuggingFace|