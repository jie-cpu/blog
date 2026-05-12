# From Classroom Codes to Production Systems: My AI Engineering Journey

*October 2024 – Present*

Hi there! I'm Jie, an AI/Software Engineer currently pursuing my Master's in Germany. Over the past two years, I've built everything from AI agents that write code to brain-age prediction systems. Here's what I learned

---

## 🧠 What I Do (The 10-Second Version)

I build **things that actually work**:
- AI systems that answer questions accurately without making stuff up
- Multi-agent teams that build software autonomously for 16+ hours
- Backend services that handle 400+ users at once
- Brain-age prediction models that run faster and better than existing ones

---

## 🤖 Project 1: RAGFlow — The Enterprise Q&A System That Doesn't Hallucinate

**April 2026 – present**

**The Problem:**  
Companies have thousands of internal documents. Generic AI chatbots either give wrong answers ("hallucinate") or cost a fortune to run.

**What I Built:**  
A question-answering system that actually reads your documents and gives correct answers—without breaking the bank.

**How It Works (Simple Version):**
1. When you ask a question, it searches documents two ways (keywords + semantic meaning) to find the most relevant chunks
2. It double-checks relevance using a re-ranking model (like having a second opinion)
3. Simple questions (like "what's the WiFi password?") go to cheaper AI models; complex ones go to top-tier models

**Results You'd Care About:**
- **Fewer wrong answers** — The re-ranking step filters out irrelevant info before the AI even sees it
- **Lower costs** — Cheap models handle ~70% of everyday questions without quality loss
- **Measurable quality** — Built dashboards tracking accuracy (MRR/MAP/Precision@K) and latency for 10,000 queries/day

**Tech Stack:** pgvector, Elasticsearch, BGE (reranking), DeepSeek, Gemini, Python

---

## 👥 Project 2: Multi-Agent System — AI Team That Builds Web Apps

**March 2026 – April 2026**

**The Problem:**  
One AI agent trying to do everything (write code, test it, deploy it) is fragile—if it fails at one step, everything breaks.

**What I Built:**  
A team of four specialized AI agents that work like a software company:

| Agent | Role |
|-------|------|
| **Engineer** | Writes the code |
| **Tester** | Finds bugs |
| **Monitor** | Watches for issues |
| **PM** | Coordinates everyone |

**Why This Matters for Business:**
- **Fault tolerance** — If the Tester agent crashes, the other three keep working
- **Long-running autonomy** — Runs 16+ hours unattended (with checkpoint/resume if something goes wrong)
- **Graceful shutdown** — Saves progress before stopping, so you don't lose work

**Tech Stack:** LangGraph, Python, State Machine, DAG scheduling

---

## 🛡️ Project 3: Tool-Using AI Agent — Safe and Observable

**January 2026 – February 2026**

**The Problem:**  
AI agents that can use tools (search web, write files, call APIs) are powerful but risky—they could do something harmful.

**What I Built:**  
An AI agent that can use external tools BUT has safety checks at every step.

**Three Layers of Safety:**
1. **Input check** — Is the user's request malicious?
2. **Execution check** — Is the AI about to do something dangerous?
3. **Output check** — Is the response safe to show?

**Cool Feature - Full Observability:**  
Every decision the AI makes is logged. You can pause at any step, see what it's thinking, and resume. No "black box" surprises.

**Performance:** Each safety layer adds only ~120ms latency, and if one AI provider fails, it automatically switches to another.

**Tech Stack:** ReAct agent pattern, Python, multi-LLM providers (OpenAI, Anthropic, local models)

---

## 📱 Project 4: Telegram Personal Knowledge Bot

**November 2025 – December 2026**

**The Problem:**  
My notes were everywhere—voice memos on my phone, screenshots in gallery, links in browser bookmarks, text in various apps. Never organized.

**What I Built:**  
A Telegram bot (because everyone uses Telegram) that takes ANYTHING you send and turns it into structured notes.

**Supported Inputs:**
- Voice messages → transcribed text
- Images → extracted text (OCR)
- Links → saved with metadata
- Plain text → directly stored

**Behind the Scenes:**
- Asynchronous processing (doesn't freeze while handling voice files)
- SQLite database for persistence
- 18 automated integration tests (CI runs on every change)

**The Result:** One unified knowledge base. No more "where did I save that?"

**Tech Stack:** Python, Telegram Bot API, SQLite, GitHub Actions (CI), OCR libraries

---

## 🧬 Project 5: Edge-based GNN for Brain Age Prediction

**April 2025 – October 2025**

**The Problem:**  
Researchers want to predict "brain age" from MRI scans—a younger-looking brain relative to actual age might indicate better health. Existing models were slow and not accurate enough.

**What I Built:**  
A Graph Neural Network that looks at **connections** between brain regions (not just regions themselves). Think: it's not about which areas light up, but how they talk to each other.

**The Data:** UK Biobank — 50,000 brain scans

**The Win:** Better accuracy than standard GCN and CNN models

**The Scaling Challenge:** Training on a single GPU would take a week

**What I Did:** Distributed training across university HPC clusters (using SLURM) → **cut training time from 7 days to under 48 hours**

**Reproducibility Bonus:** Fixed random seeds, TensorBoard logging, and edge-level importance scores so researchers can trust and explain the results.

**Tech Stack:** PyTorch, PyTorch Geometric, SLURM, HPC, TensorBoard

---

## 🔬 Project 6: Research Assistant @ University of Greifswald

**February 2025 – September 2025**

**The Problem:**  
Research teams were building 3D graphics pipelines (Gaussian Splatting) but metadata handling was manual and error-prone.

**What I Did:**
- Built FastAPI services to automatically extract and manage metadata
- Containerized everything with Docker so other researchers could run the same code
- Set up CI/CD pipelines (every code change automatically tested and deployed)
- Connected data ingestion → processing → monitoring across multiple teams

**Why It Mattered:** Reproducible research. No more "it works on my machine."

**Tech Stack:** FastAPI, Docker, CI/CD (GitLab), Python

---

## 💼 Industry Experience (Before Germany)

### Backend Developer @ Yingfu Kids & Teens, Shanghai
**March 2024 – August 2024**

**What I Built:**  
Go microservices for an online examination platform—login (RBAC权限), session management, exam lifecycle.

**Scale:** Deployed on Kubernetes (Tencent Cloud), supported 400+ concurrent users.

**Tech Stack:** Go, Kubernetes, Docker, Tencent Cloud, PostgreSQL

### Frontend Intern @ Liu Wan Fan, Shanghai
**October 2023 – February 2024**

**What I Built:**  
A restaurant ordering web app that reduced table wait time by 25% for 110+ daily customers.

**Cool Feature:** Real-time admin dashboard with WebSocket + WeChat Mini Program QR scanning—staff saw orders instantly.

**Tech Stack:** React, TypeScript, WebSocket, Tailwind

---

## 🎓 Education

| Degree | School | Year |
|--------|--------|------|
| **M.Sc. Computational Modeling & Simulation** | TU Dresden, Germany | 2024–present |
| **B.Eng. Network Engineering** (GPA: 3.5/4.0) | Anhui Agricultural University, China | 2020–2024 |

---

## 🛠️ Skills Summary

**AI & Machine Learning:**
- LLM Agents (LangGraph, LangChain) — making AI do multi-step tasks
- RAG (Retrieval-Augmented Generation) — AI that reads your documents
- Model evaluation — knowing if your AI is actually good
- GNNs, PyTorch, TensorFlow

**DevOps & Cloud:**
- Docker, Kubernetes — packaging and running applications anywhere
- CI/CD — automatic testing and deployment
- Linux, GCP, HPC clusters (SLURM) — running big jobs fast

**Backend:**
- Python, Go, Java, TypeScript
- FastAPI, REST APIs
- PostgreSQL, MySQL, Elasticsearch

**Frontend:**
- React, Vue.js, Tailwind
- Mobile (Android, iOS basics)

**Languages:**
- Mandarin (native)
- English (C1 — fluent professional)
- German (B1 — everyday conversation)

---

## 💡 What I've Learned (The Non-Technical Takeaways)

1. **Cost matters** — Routing simple queries to cheap models isn't just optimization; it's economics.
2. **Observability is non-negotiable** — If you can't see what your AI is thinking, you can't trust it.
3. **Fault tolerance beats perfection** — A system that fails gracefully is better than one that fails catastrophically.
4. **Time is the real currency** — Cutting training from 7 days to 48 hours isn't a tech win; it's a researcher's sanity win.
5. **Boring tech wins** — The Telegram bot didn't use fancy AI; it just worked reliably. Users loved it.

---

## 📫 Let's Connect

- **Email:** jiepeng9527@gmail.com
- **Portfolio:** [jie-cpu.github.io/profile](https://jie-cpu.github.io/profile)
- **GitHub:** [github.com/jie-cpu](https://github.com/jie-cpu)
- **Location:** Germany

---

*Thanks for reading! If you're hiring someone who can build AI systems that actually work in production—and explain them to non-engineers—let's talk.*