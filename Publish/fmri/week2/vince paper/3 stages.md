
**Stage 1: Train a Text-Aligned fMRI Tokenizer**

- **Goal**: Convert raw, continuous fMRI signals into **discrete tokens**. More importantly, the embedding representations of these tokens need to be aligned with a **frozen text encoder** (e.g., GPT-2's text embedding space).

- **Why it's necessary**: Without this "translator", raw fMRI data cannot be understood by a subsequent LLM. An LLM cannot process high-dimensional, continuous fMRI signals directly.

---

**Stage 2: Fine-tune the LLM for Temporal Modeling**

- **Goal**: Freeze the well-trained "fMRI tokenizer" from the previous stage, then fine-tune the LLM. In this stage, the LLM learns two abilities:

    - **fMRI-to-fMRI (F2F)**: Predict the next time step's token based on the fMRI tokens from the previous time step (similar to temporal dynamics prediction of brain signals).

    - **fMRI-to-Text (F2T)**: Generate corresponding text descriptions based on fMRI tokens (using the synthetic text constructed in Stage 1).

- **Why it's necessary**: Through this stage, the LLM not only learns the **temporal patterns** of fMRI signals but also initially establishes the mapping capability from "brain activity" to "linguistic description".

---

**Stage 3: Multi-Task, Multi-Paradigm Instruction Tuning**

- **Goal**: Based on Stage 2, use a large amount of **instruction data** (e.g., "Please determine the subject's gender based on the fMRI", "Describe the subject's cognitive status") to fine-tune the LLM.

- **Why it's necessary**: This stage is **key for application**. The first two stages allow the LLM to "understand" fMRI, but this stage enables it to **learn how to answer specific questions and perform specific tasks** (classification, Q&A, report generation, etc.). Without this step, the model is just a "brain signal description generator", not a general-purpose "fMRI assistant".

---