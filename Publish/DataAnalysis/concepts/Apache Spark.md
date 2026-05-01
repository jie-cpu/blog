---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
Here's a simple, clean markdown blog post based on your Spark summary:

---

markdown
# Apache Spark: Big Data Processing Made Simple

Apache Spark is a super-fast engine for processing huge amounts of data. It keeps data in memory, making it much faster than older systems.

## The Big Picture

Think of Spark as a **company**:

| Role | Spark Component | What They Do |
|------|----------------|---------------|
| Project Manager | Driver (with SparkContext) | Assigns tasks, runs 1 application |
| HR Team | Cluster Manager | Schedules resources |
| Employees | Workers (Executors) | Perform actual operations |
| Client Machine | Client | Submits the job |

## How SparkContext Works

1. Connects to Cluster Manager (gets resources)
2. Acquires Executors on worker nodes
3. Sends application code to executors
4. Distributes tasks to run separately

> Each driver runs **only one** application.

## RDD — The Core Concept

**RDD** = Resilient Distributed Dataset

| Property | Meaning |
|----------|---------|
| **Resilient** | Fault-tolerant — can rebuild lost data |
| **Distributed** | Data spread across multiple nodes |
| **Dataset** | Partitioned collection of data |

### Two Types of RDD Operations

```
Transformations (lazy, not immediate)
├── map()
├── filter()
└── ...

Actions (executes now)
├── saveAsTextFile()
├── reduce()
└── count()
```

## Data Abstraction Evolution

```
RDD (basic)
    ↓
DataFrames (organized like SQL tables)
    ↓
Datasets (type-safe)
```

## The DAG Engine

Spark uses a **DAG** (Directed Acyclic Graph) execution engine that supports:
- ✅ Cyclic data flow
- ✅ In-memory computing

## One-Line Summary

> Spark = in-memory, fault-tolerant, unified engine for batch + real-time + ML + graph processing.

---

*Related: `[[SparkContext]]` · `[[RDD]]` · `[[DAG]]` · `[[Cluster Manager]]`*


---
