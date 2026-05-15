---
date: 2026-05-16
updated: 2026-05-16
description:
---
----
### Part 1  

#### Agent Frameworks (LangChain & Self-Developed)
- Experienced with general-purpose Agent frameworks (LangChain, etc.) for rapid prototyping.
- Aware of limitations of generic frameworks in production (observability, custom components, internal infrastructure integration).
- Willing and able to adapt to **self-developed internal frameworks** – focusing on engineering fundamentals over framework lock-in.

#### Production-Ready Distributed Architecture & Model Deployment
- Hands-on exposure to **vLLM**: high-throughput LLM inference with PagedAttention.
- Familiar with **Ray** (Ray Serve, Ray Actors) for distributed orchestration and complex inference pipelines.
- Understand trade-offs between latency, throughput, GPU utilization, and serving stack choices (vLLM / Triton / KServe).

---

### Part 2 

#### On LangChain & Self-Developed Frameworks
- *"General frameworks like LangChain are great for quick demos, but production systems often need custom control – observability, internal storage, fine-grained caching. That's why many companies build their own, and I'm comfortable adapting to whatever framework is used."*

- *"I see frameworks as tools, not religions. What matters is understanding the underlying patterns – prompt chaining, routing, memory, tools – not just the API of one library."*

#### On vLLM & Ray
- *"For production LLM serving, vLLM is a game-changer because of PagedAttention – it dramatically improves throughput and GPU memory efficiency compared to naive HF pipelines."*

- *"Ray is more than just a cluster launcher. With Ray Serve, you can build multi-model pipelines, handle batching, and scale dynamically. It's especially useful when you have pre-processing, LLM inference, and post-processing in one flow."*

#### On Production Mindset
- *"A model is not production-ready just because it works on a notebook. You need to think about: request batching, GPU utilization, fallback strategies, canary deployment, and observability – from day one."*

- *"I keep an eye on emerging tools like vLLM and Ray, but I always evaluate them against real requirements: latency SLO, cost, scalability, and team expertise."*

---

| Topic | Key Point | One-Liner |
|-------|-----------|------------|
| LangChain | Good for prototyping | *"LangChain is a starting point, not an ending point."* |
| Self-developed framework | Companies need customization | *"I adapt to the framework – I don't marry one."* |
| vLLM | High-throughput inference | *"vLLM makes LLM serving actually efficient."* |
| Ray | Distributed orchestration | *"Ray is for pipelines, not just for clusters."* |
| Prod readiness | Beyond the notebook | *"Latency, cost, observability – the real triad."* |
