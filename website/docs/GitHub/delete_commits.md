---
sidebar_position: 2
---

# Remove Unwanted Commits

> 🎯 **Goal**: Remove unwanted commits from your GitHub Branch.

---

## ✅ What You Need:

* Git installed on your computer
* Visual Studio Code installed
* A GitHub repository cloned locally
* The branch you want to clean (e.g., `main`)

---

## 🪄 Step-by-Step Guide

### 1. Open Your Project in VS Code

Open the folder that contains your GitHub project in **Visual Studio Code**.

---

### 2. Open the Terminal in VS Code

* Click on **Terminal → New Terminal**
* Or press [ Ctrl + ` ] to open the terminal inside VS Code.

---

### 3. Check the Commit History

Type this command in the terminal:

```bash
git log --oneline
```

This will show a list of commits like:

```
<commit_hash> Commit message 1
<commit_hash> Commit message 2
<commit_hash> Commit message 3
<commit_hash> Commit message 4
<commit_hash> Commit message 5
```

Each line is one commit. The top one is the **most recent**.

---

### 4. Start Interactive Rebase

Choose how many commits you want to review. If it’s the last 5, type:

```bash
git rebase -i HEAD~5
```

This opens a text file in VS Code. (or usually default editor like `vim`)

---

### 5. Edit the File to Delete Commits

You’ll see something like this:

```
pick <commit_hash> Commit message 1
pick <commit_hash> Commit message 2
pick <commit_hash> Commit message 3
pick <commit_hash> Commit message 4
pick <commit_hash> Commit message 5
```

To **delete** a commit, change `pick` to `drop`.

Example to keep only the first commit:

```
pick <commit_hash> Commit message 1
drop <commit_hash> Commit message 2
drop <commit_hash> Commit message 3
drop <commit_hash> Commit message 4
pick <commit_hash> Commit message 5
```

---

### 6. Save and Close the File

* Press `Ctrl + S` to **save** the file.
* Press `Ctrl + W` to **close** the file tab.

Git will now remove the commits you marked as `drop`.

---

### 7. Push Your Changes to GitHub

Since you changed the commit history, do a **force push**:

```bash
git push origin your-branch-name --force
```

For example:

```bash
git push origin dev --force
```

---

## 🎉 You’re Done!

Your branch now contains only the commits you want.

---

## 💡 Tips:

* Always double-check before force-pushing!
* To be safe, create a backup:

```bash
git checkout -b backup-branch
```

---

> This guide is perfect for beginners or anyone cleaning up their Git commit history.