

**Q: What makes this different from AutoGPT or simple agent loops?**

This models an *organization*, not a single agent. Four specialized agents with distinct roles, tools, and handoff protocols. The orchestrator is a hand-written state machine (6 states, 7 valid transitions) + topological sort (Kahn's algorithm) + file-based checkpointing.

**Q: Why pure Python instead of LangGraph / CrewAI / AutoGen?**

Those frameworks abstract away the state management, checkpointing, and routing logic. In this project, those are the interesting parts — the state machine, dependency graph, checkpoint serialization, and heartbeat monitor are all deliberately hand-written to show understanding. Each module can be swapped for a framework later without changing the agent implementations (decomposer, coder, judge).

**Q: How do you prevent infinite loops?**

Three mechanisms: (1) iteration limit per task (configurable), (2) escalation threshold — 5 revision loops between SE and Tester triggers pause, (3) task-level timeout that resets context on expiry.

**Q: How do you evaluate AI-generated code?**

Two-tier gate: (a) LLM-as-judge scores code on 5 dimensions (correctness, security, quality, error handling, testability) — gives 1-10 per dimension with specific issue locations; (b) static analysis fallback detects hardcoded secrets, missing validation, absent error handling, missing type hints. Both produce a pass/fail decision against a configurable threshold.

**Q: How do you handle 16+ hour runs?**

File-based checkpointing via `CheckpointManager`. After each completed task, full session state is serialized to `data/checkpoints/` as a JSON file with rolling window retention (default 50). `SessionManager` handles lifecycle — `--resume` reloads the latest checkpoint, rebuilds state, skips completed tasks. SIGINT triggers immediate checkpoint save before exit.

**Q: Can you run this locally without cloud APIs?**

Yes. `make dry-run` uses rule-based decomposition and static-analysis judging — no API calls. All tasks in the goal lifecycle complete without internet access.

**Q: What actually writes real code?**

The SE Agent (LLM mode, requires API key) generates FastAPI code files and writes them to `platform/backend/app/`. The code includes async endpoints, Pydantic models, proper error handling, type hints, and docstrings. Without an API key, it falls back to simulated output.

---