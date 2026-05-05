---
title: My Post Title
date: 2026-05-02
updated: 2026-04-28
description: Optional short description
---
----


If you're reviewing this project for a hiring conversation:

1. **Why not LangChain?** — For a linear 6-step pipeline, hand-written `asyncio` is simpler to debug and has zero framework lock-in. The data flow is explicit function calls, not a graph abstraction
2. **How do you handle failures?** — Each step has try/except. If the LLM call fails, the pipeline falls back to pure-skill article generation. Rate limiting prevents abuse. The queue module has exponential-backoff retry
3. **How would you scale this?** — Extract the orchestrator into a separate worker process, replace the in-process rate limiter with Redis, swap SQLite for PostgreSQL
4. **How did you evaluate quality?** — 18 unit tests across all modules. The LLM prompt is engineered for structured JSON output. `_parse_json_response` handles model quirks (markdown fences, missing JSON mode)
5. **What was the hardest part?** — Making `faster-whisper` work async (it has a sync API, wrapped via `asyncio.to_thread`). DeepSeek's API doesn't support `response_format: json_object`, so the JSON parser needed markdown-fence stripping
