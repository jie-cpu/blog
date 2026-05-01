---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# Stream Processing

Real-time processing of continuous data streams for applications like autonomous driving, sensor analysis, and traffic monitoring.

## Applications

| Application | Description |
|-------------|-------------|
| **Autonomous driving** | Real-time sensor fusion, decision making |
| **Sensor data analysis** | IoT, industrial monitoring |
| **Traffic monitoring** | Real-time congestion detection, flow optimization |

## Core Model

```
Events ──Query──→ Events
         ↓
      State
```

- **Events** flow continuously
- **Queries** operate on event streams
- **State** maintained across events

## Stream Processing Frameworks

### Alternatives

| Framework | Description |
|-----------|-------------|
| **Apache Storm** | Low-latency, record-at-a-time processing |
| **Spark Streaming** | Micro-batch processing on Spark |
| **Apache Samza** | Kafka-integrated, stateful processing |
| **Apache Flink** | True streaming, similar to Spark but better streaming support |

## Spark Streaming vs Flink

### Core Difference

| Aspect | Spark Streaming | Apache Flink |
|--------|-----------------|---------------|
| **Processing Model** | **Micro-batching** | **True streaming** (record-at-a-time) |
| **API** | Split input into mini-batches | Direct API to access events in real-time |
| **Latency** | Higher (batch interval) | Lower (continuous) |
| **Streaming Support** | Mapped on batch process | Native streaming |

### Processing Models Visualized

```
Spark Streaming (Micro-batching)
Events: [e1][e2][e3] [e4][e5][e6] [e7][e8][e9]...
         └───batch1───┘ └───batch2───┘ └───batch3───┘
              ↓               ↓               ↓
           Process         Process         Process

Flink (True Streaming)
Events: e1→e2→e3→e4→e5→e6→e7→e8→e9→...
         ↓   ↓   ↓   ↓   ↓   ↓   ↓   ↓
       Process each event immediately
```

## Windowed Aggregation

| Framework | Scaling | Offset |
|-----------|---------|--------|
| **Spark Streaming** | ✅ Good scaling | Slight offset (due to batching) |
| **Flink** | ✅ Good scaling | Lower offset (true streaming) |

> [!note]
> Both frameworks scale well for windowed aggregations, but Spark has a **slight offset** due to its micro-batching nature.

## Framework Selection Guide

| Use Case | Recommended |
|----------|-------------|
| **Low latency required** (milliseconds) | Flink (true streaming) |
| **Existing Spark infrastructure** | Spark Streaming |
| **Exactly-once semantics** | Both support |
| **Batch + streaming unified** | Spark (unified batch/streaming API) |
| **Event time processing** | Flink (stronger support) |
| **Kafka integration** | Samza, Flink, Spark all work |

## One-Line Summary

> Stream processing = real-time event handling — Spark uses micro-batches, Flink does true streaming with lower latency.

## Related

- [[Apache Spark]]
- [[Apache Flink]]
- [[Apache Kafka]]
- [[Real-Time Processing]]
- [[Event Streaming]]
- [[Windowed Aggregation]]
- [[Lambda Architecture]]
- [[Kappa Architecture]]
```

---

This version is:

- **Obsidian-ready** — copy and paste
- **Applications table** (autonomous, sensor, traffic)
- **Core model** (Events → Query → State)
- **Framework alternatives** listed
- **Spark vs Flink comparison** table
- **ASCII visualization** of micro-batching vs true streaming
- **Windowed aggregation note** about offset
- **Selection guide** by use case
- **Links ready** for related concepts

Want me to add code examples (Spark Streaming vs Flink API) or deeper explanation of event time vs processing time?