---
sidebar_position: 3
---

# Rename Commits

Sometimes, you might make a commit in Git but realize the message is wrong or unclear. This guide will help you **rename a commit message** easily.

---

## 🔄 Rename the Most Recent Commit

If you just made the commit and want to change its message:

```bash
git commit --amend -m "New commit message"
```

👉 This replaces the last commit message with your new one.

### 🚀 If You Already Pushed the Commit

You’ll need to force push:

```bash
git push --force
```

> ⚠️ Force pushing can overwrite commits on GitHub, so only do this if you're sure.

---

## 🔁 Rename an Older Commit

If the commit you want to rename is not the most recent one:

### 1. Start an Interactive Rebase

Example: To go back 3 commits:

```bash
git rebase -i HEAD~3
```

### 2. Mark the Commit for Renaming

You’ll see something like this:

```
pick 123abc First commit
pick 456def Second commit
pick 789ghi Third commit
```

➡️ Change `pick` to `reword` on the commit you want to rename:

```
pick 123abc First commit
reword 456def Second commit
pick 789ghi Third commit
```

Then save and close the editor.

### 3. Edit the Commit Message

Git will now ask you to change the message for the commit you marked. Type the new message, save, and close.

---

## 🛠 Push the Changes

If you've already pushed these commits before, you must force push:

```bash
git push --force
```

---

## ⚠️ Important Notes

- Force pushing can affect other team members. Avoid it on shared branches like `main` or `master`.
- Always double-check the history after rebasing using:

```bash
git log --oneline
```

---

## ✅ Summary

| Task                      | Command                                       |
|---------------------------|-----------------------------------------------|
| Rename last commit        | `git commit --amend -m "New message"`         |
| Rename older commit       | `git rebase -i HEAD~N` → change `pick` to `reword` |
| Push after rename         | `git push --force`                            |

---

Happy committing! 🎉
