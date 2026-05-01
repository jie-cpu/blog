---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# CUDA (Compute Unified Device Architecture)

NVIDIA's platform for parallel programming on GPUs. Enables massive speedup for data-parallel tasks.

## Key Concepts

| Concept | Description |
|---------|-------------|
| **Host** | CPU + system memory |
| **Device** | GPU + its own memory |
| **Kernel** | Function that runs in parallel on the GPU |
| **Thread hierarchy** | Threads → Blocks → Grid |

## Typical Workflow

1. Copy data from host to device
2. Launch kernel on device (many threads)
3. Copy results back from device to host

## Common Use Cases

- Deep learning training
- Matrix operations
- Image processing
- Scientific simulation

## Related

- [[GPU Architecture]]
- [[Parallel Computing]]
- [[NVIDIA]]
- [[PyTorch CUDA]]