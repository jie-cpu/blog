---
date: 2026-05-30
updated: 2026-05-30
description:
---
----
# **Aria2 Quick Guide 🚀**

## **What is aria2?**

**aria2** is a command-line download tool that is faster and more stable than a browser.

It supports:

- Multi-thread downloading
- Resume broken downloads
- Large file downloads

👉 Think of it as a faster downloader for your terminal.

---

## **Why use it?**

|**Browser**|**aria2**|
|---|---|
|Slow|Fast 🚀|
|Single thread|Multi-thread|
|Can break|Resume supported|

Best for large files like datasets or videos.

---

## **Install**

### **macOS**

```bash
brew install aria2
```

### **Ubuntu**

```bash
sudo apt install aria2
```

Check:

```bash
aria2c --version
```

---

## **Basic usage**

### **Normal download**

```bash
aria2c URL
```

### **Fast download (recommended)**

```bash
aria2c -x 16 -s 16 URL
```

### **Resume download**

```bash
aria2c -c URL
```

---

## **Example**

```bash
aria2c -x 16 -s 16 -c \
https://boldmomentsdataset.csail.mit.edu/stimuli_metadata/stimulus_set.zip
```

---

## **Summary**

- Faster than browser
- Supports resume
- Best for large datasets 🚀