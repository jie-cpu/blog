---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# ** Upload Local Project to GitHub (Standard Workflow)**

## 

## **Step 1: Create a repository on**

**GitHub**

- Go to GitHub
- Create a new repository
- Copy the repository URL (HTTPS or SSH)

---

## ** Step 2: Initialize Git locally**

```bash
git init
```

👉 Initializes a new Git repository in your project folder

---

## **Step 3: Stage your files**

```bash
git add .
```

👉 Adds all files to the staging area

---
## **Step 4: Commit your changes**

```bash
git commit -m "Initial commit"
```

👉 Saves your changes locally

---
## **Step 5: Connect to remote repository**

```bash
git remote add origin <your-repo-url>
```

👉 Links your local repo to GitHub

---
## **Step 6: Rename branch to**

**`main`**

**(recommended)**

```bash
git branch -M main
```

👉 Ensures your branch matches GitHub default (`main`)

---

## **Step 7: Push to GitHub**

```bash
git push -u origin main
```

👉 Uploads your code and sets upstream tracking

---

# **🎯 Final Result**

- Local branch: `main`
- Remote branch: `origin/main`
- Tracking established ✅

---

# **🚀 After this, you only need:**

```bash
git push
git pull
```

---

# **⚠️ Common mistake**

❌ Using:

```bash
git push origin master
```

👉 This creates a **new** **`master`** **branch remotely**, which can mess things up

---

# **🧠 Short version (you can memorize this)**

```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin <url>
git branch -M main
git push -u origin main
```

---
