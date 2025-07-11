---
sidebar_position: 5
---

# Create Orphan Branch

This guide will show you how to create a **new, empty Git branch** (called an **orphan branch**) that has no history from your current branch. This is useful for things like deploying to GitHub Pages (`gh-pages`), maintaining documentation, or creating a fresh start.

---

## 🧠 What is an Orphan Branch?

An **orphan branch** is a new branch that starts with **no previous commits or history**. It’s like starting with a blank project, even though you're in the same Git repository.

---

## ✅ Step-by-Step Instructions

### 1. Open your terminal and navigate to your project folder.

```bash
cd your-project-folder
```

---

### 2. Create a new orphan branch

Replace `new-branch-name` with the name you want (for example: `gh-pages`, `docs`, `clean-start`, etc.)

```bash
git switch --orphan new-branch-name
```

> 📝 This will switch you to a new branch **without** any commit history.

---

### 3. (Optional) Delete all existing files from the working directory

You may still see your old files. If you want to start fresh, remove them:

```bash
git rm -rf .
```

> ⚠️ This only removes files from the orphan branch, **not** your main branch.

---

### 4. Make an initial commit

Create an empty first commit to initialize the branch:

```bash
git commit --allow-empty -m "Initial commit"
```

---

### 5. Push the branch to GitHub (or other remote)

Replace `origin` with your remote name (default is usually `origin`) and `new-branch-name` with your branch name.

```bash
git push -u origin new-branch-name
```

> 🚀 This pushes your new branch and sets it to track the remote version.

---

## 🧼 You’re Done!

You now have a clean branch with no history, ready for whatever purpose you need — like documentation, a demo site, or a different version of your project.

---

## 💡 Tips

- Switch back to your main branch anytime with:

  ```bash
  git switch main
  ```

- List all branches (local and remote):

  ```bash
  git branch -a
  ```

---

## 🔁 Example: Creating a `gh-pages` Branch for GitHub Pages

```bash
git switch --orphan gh-pages
git rm -rf .
git commit --allow-empty -m "Initial commit"
git push -u origin gh-pages
```

> You can now add your static site files and push again to publish.

---

Happy coding! 🎉
