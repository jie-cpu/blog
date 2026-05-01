---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# JupyterHub vs. Jupyter Notebook

A comprehensive comparison between Jupyter Notebook/JupyterLab (single-user) and JupyterHub (multi-user server).

## Core Concepts

### Jupyter Notebook / JupyterLab

| Aspect | Description |
|--------|-------------|
| **Definition** | Open-source web app for creating documents with live code, equations, visualizations, and narrative text |
| **Scope** | **Single-user application** — runs server on local machine or controlled server |
| **Primary Function** | Interactive coding and data analysis for an **individual** |

### JupyterHub

| Aspect | Description |
|--------|-------------|
| **Definition** | **Multi-user server** that spawns and manages individual Jupyter instances for authenticated users |
| **Scope** | Designed for **multiple users** — central gateway for teams, classes, or organizations |
| **Primary Function** | Provides managed access to Jupyter environments for **groups** |

## Architecture Comparison

| Feature | Jupyter Notebook/Lab | JupyterHub |
|---------|---------------------|------------|
| **User Model** | Single-user | Multi-user |
| **Deployment** | Local machine or single remote server | Server-based (on-premises or cloud) |
| **Process** | One server process per session | Central Hub + multiple single-user servers |
| **File System** | Direct access to local/server file system | Isolated workspace per user |

## Key Features & Differences

| Feature | Jupyter Notebook/Lab | JupyterHub |
|---------|---------------------|------------|
| **Primary Goal** | Interactive computing for individuals | Managed computing for groups |
| **User Management** | N/A (single user) | Built-in authentication |
| **Resource Allocation** | Uses machine resources | Can limit resources per user |
| **Scalability** | Limited to one machine | Scales to many users (e.g., Kubernetes) |
| **Setup Complexity** | Simple (`pip install jupyterlab`) | Complex server setup required |
| **Collaboration** | Indirect (share `.ipynb` files) | Shared platform for teams |
| **Environment Control** | User controls environment | Admin controls base environments |
| **Cost** | Free + hardware costs | Free software + infrastructure costs |

## When to Choose Which

### Choose Jupyter Notebook/Lab if:

- ✅ Working primarily **by yourself**
- ✅ Prefer managing your own local environment
- ✅ Need **quick and easy** setup
- ✅ Workflow involves local `.md` files

### Choose JupyterHub if:

- ✅ Need to provide environments to **multiple users**
- ✅ Require **centralized management** of users, resources, and software
- ✅ Supporting a **classroom, research team, or corporate group**
- ✅ **Consistency** across environments is important
- ✅ Can invest time in **setup and administration**

## One-Line Summary

> Jupyter Notebook = single-user · JupyterHub = multi-user server that manages many notebooks for many people.

## Related

- [[JupyterLab]]
- [[Jupyter Notebook]]
- [[Project Jupyter]]
- [[Kernel]]
- [[.ipynb]]