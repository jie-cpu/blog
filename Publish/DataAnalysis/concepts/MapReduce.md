---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# MapReduce, Hadoop & Spark: Evolution of Big Data Processing

## Google MapReduce (Original)

**Closed source** — the pioneering distributed processing framework.

### Components

| Phase | Operation |
|-------|-----------|
| Input | Raw data |
| Split | Divide into chunks |
| **Map** | Filtering and sorting |
| Shuffle/Sort | Organize intermediate data |
| Merge | Combine results |
| **Reduce** | Summary operation |
| Output | Final result |

**Flow:** `Input → Split → Map → Sort → Merge → Reduce → Output`

---

## Apache Hadoop

**Open source** — inspired by Google MapReduce. Disk-based, slow but stable.

### Core Components

| Component | Function |
|-----------|----------|
| **HDFS** | Distributed file system (data warehouse oriented files) |
| **MapReduce** | Data processor |
| **YARN** | Job scheduler |

### Ecosystem

```
Hadoop Ecosystem
├── HDFS (storage)
│   └── HIVE (SQL queries on HDFS tables)
├── MapReduce (processing)
└── YARN (scheduling)
```

### Limitations

| Limitation | Description |
|------------|-------------|
| ❌ Missing core DBMS features | No indexes, ACID, etc. |
| ❌ Incompatible with many tools | Limited ecosystem integration |
| ❌ Non-interactive | Batch-only, no real-time |
| ❌ Complex task transformation | Difficult to express complex jobs |
| ❌ No iterations | Poor fit for ML algorithms |

---

## Apache Spark

**Memory-based** — fast and multifunctional.

### Key Improvements over Hadoop

| Aspect | Hadoop | Spark |
|--------|--------|-------|
| **Storage** | Disk (slow) | Memory (fast) |
| **Speed** | Slower | Up to 100x faster |
| **Iterations** | Not supported | Built-in |
| **Interactivity** | Batch only | Interactive possible |

### Capabilities

- ✅ Batch processing
- ✅ Real-time streaming
- ✅ Machine learning (MLlib)
- ✅ Graph processing (GraphX)
- ✅ SQL queries (Spark SQL)

---

## Evolution Summary

```
Google MapReduce (closed source)
        ↓
Apache Hadoop (open source, disk, stable)
        ↓
Apache Spark (memory, fast, multifunctional)
```

| Generation | Key Characteristic |
|------------|---------------------|
| MapReduce | Pioneer, closed source |
| Hadoop | Disk-based, stable, open source |
| Spark | Memory-based, fast, unified engine |

## One-Line Summary

> Hadoop = disk-based stable workhorse · Spark = memory-based speed demon · Both process big data at scale.

## Related

- [[HDFS]]
- [[HIVE]]
- [[YARN]]
- [[MapReduce]]
- [[Spark vs Hadoop]]
- [[RDD]]
```

---

This version is:

- **Obsidian-ready** — copy and paste
- **Three clear sections** — MapReduce → Hadoop → Spark
- **Flow diagram** for MapReduce phases
- **Table of Hadoop limitations** (5 points)
- **Comparison table** Hadoop vs Spark
- **Evolution timeline** visualization
- **Links preserved** for related concepts

Want me to add more detail on HDFS replication, YARN architecture, or Spark RDDs?