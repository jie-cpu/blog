---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
## **💡 1. Core Questions & Answers**

### 

### **1.**

**How do I configure Git to only track the** **`Publish/`** **folder?**

**Answer (internals):**  
Git tracks files via its **index (staging area)**, not the filesystem directly. When you run:

```gitignore
*
!Publish/
!Publish/**
```

You’re defining **pattern-based ignore rules** applied during `git add`.

- `*` → matches all files recursively → marks everything as ignored
- `!Publish/` → negates ignore for the directory itself
- `!Publish/**` → re-includes all nested content

**Important internal detail:**  
Git evaluates `.gitignore` rules **top-down**, and later rules override earlier ones.

But this only affects **untracked files**. If a file is already in the index, `.gitignore` does nothing. That’s why you needed to reset the index (see next question).

---

### 

### **2.**

**Why did I need** **`git rm -r --cached .`****?**

**Answer (internals):**  
Git has three layers:

1. **Working Directory** (your actual files)
2. **Index (Staging Area)** ← what Git tracks
3. **Repository (commits)**

`.gitignore` only affects step **1 → 2 transition** (`git add`).

If files are already in the index, Git continues tracking them regardless of `.gitignore`.

```bash
git rm -r --cached .
```

- `--cached` → removes files **only from the index**, not disk
- This effectively says:  
    👉 “Forget everything you’re tracking”

Then:

```bash
git add .
```

Now Git re-adds files **respecting** **`.gitignore`** **rules**, so only `Publish/` enters the index.

---

### 

### **3.**

**Why did Git show** **`delete mode 100644`****?**

**Answer (internals):**  
When you removed files from the index, Git compared:

- Previous commit (which had `.obsidian/`, `n8n/`, etc.)
- New index (which no longer includes them)

So Git interprets this as:

“These files are being deleted from the repository”

`100644` is the **file mode** (normal non-executable file in Git’s object model).

**Key detail:**  
Git is not deleting files locally. It’s updating the **tree object** in the next commit.

---

### 

### **4.**

**Why are my local files still there after “deletion”?**

**Answer (internals):**

Because:

- `git rm --cached` modifies only the **index**
- Your **working directory is untouched**

Git is not a filesystem manager—it’s a **content tracker**.

So:

|**Layer**|**State**|
|---|---|
|Working directory|unchanged ✅|
|Index|cleaned|
|Repo (next commit)|updated|

---

### 

### **5.**

**Why did** **`git commit`** **say “nothing to commit”?**

**Answer (internals):**

Git determines commit necessity by comparing:

- **Index vs last commit (HEAD)**

If no differences:

```bash
nothing to commit, working tree clean
```

In your case:

- You already committed the changes (removing files from index)
- No new changes exist in the index

So Git correctly blocks redundant commits.

---

### 

### **6.**

**What does “branch is ahead of origin/main by 1 commit” mean?**

**Answer (internals):**

Git stores history as a **directed acyclic graph (DAG)** of commits.

Your situation:

```
origin/main: A ── B
local main:  A ── B ── C
```

- `C` exists only locally
- Remote pointer (`origin/main`) hasn’t moved

So Git tells you:

“You have commits not yet pushed”

---

### 

### **7.**

**What actually happens during** **`git push`****?**

**Answer (internals):**

When you run:

```bash
git push
```

Git:

1. Compares commit graphs (local vs remote)
2. Finds missing commits (e.g., `C`)
3. Sends:
    - commit objects
    - tree objects
    - blob objects (file contents)
4. Updates remote ref:

```
origin/main → C
```

**Important:**  
Because your new commit removed files, the remote repo will:

- Stop referencing those blobs
- Eventually garbage collect them

---

### 

### **8.**

**Why** **`.gitignore`** **doesn’t affect already committed files?**

**Answer (internals):**

`.gitignore` is **not a filter on the repository**, it’s a filter on:

“What gets added to the index”

Git does **not retroactively apply rules** to history or tracked files.

This is a design choice to avoid accidental data loss.

---

## **🕵️ 2. Key Misconceptions & Blind Spots**

### **❌ Misconception 1:**

“.gitignore will automatically stop tracking files”

**Reality:**  
It only prevents **future tracking**, not existing index entries.

👉 Missing concept: **Git index as a persistent tracking layer**

---

### **❌ Misconception 2:**

“delete mode means files are deleted locally”

**Reality:**  
It reflects changes in the **next commit tree**, not filesystem state.

👉 Missing concept: **Git tracks snapshots, not live files**

---

### **❌ Misconception 3:**

“I need to commit again after seeing status”

**Reality:**  
Git already committed your changes. You were looking at a **post-commit clean state**.

👉 Missing concept: **difference between working tree vs commit state**

---

### **⚠️ Blind Spot:**

You’re treating Git like a sync tool, not a **content-addressable database**.

Key missing mental model:

Git = snapshot system (tree + blobs + commits), not file operations

---

## **🏗️ 3. Architectural Takeaways**

### 

### **1.**

**Separation of concerns: Source vs Publish**

You implicitly designed:

```
Blog/
├── (Obsidian workspace)   ← authoring layer
├── Publish/               ← deployment layer
```

This is **correct architecture**:

- Source = messy, rich, local
- Publish = clean, deterministic, versioned

---

### 

### **2.**

**Using Git as a deployment boundary**

By only tracking `Publish/`, you turned Git into:

“A controlled export pipeline”

This is effectively a **manual build step**, similar to:

- `dist/` in frontend builds
- compiled artifacts in CI/CD

---

## **🚀 4. Practical Next Steps**

### **✅ Immediate Action**

1. **Push your commit**

```bash
git push
```

2. **Verify on GitHub**

- Confirm only `Publish/` exists
- Ensure no hidden `.obsidian` remnants

---

### **🔥 High-Impact Upgrade (do this next)**

Automate your pipeline:

```
Obsidian → Publish/ → Git commit → Deploy
```

Options:

- Git hook (`post-commit`)
- Script (Node / Bash)
- Or your earlier idea: **n8n automation**

---

### **🧠 The “Next Question” (ask this)**

**“How do I design a fully automated content pipeline where Obsidian changes trigger a build step that transforms markdown into a production-ready blog and deploys it via CI/CD?”**

This will force you to learn:

- Git hooks vs CI pipelines
- Static site generators (Astro, Hugo, Next.js)
- Content transformation (Markdown → HTML)
- Deployment systems (Vercel / GitHub Pages)

---

## **🧩 Final Insight**

You didn’t just “fix `.gitignore`”.

You accidentally implemented the foundation of a **content publishing system**.

The next step is to make it:

**automatic, reproducible, and deployable**.