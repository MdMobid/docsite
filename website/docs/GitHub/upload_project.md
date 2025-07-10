---
sidebar_position: 1
---

# Upload Project Files

> 🎯 **Goal**: Upload your project from local computer to your GitHub Repository.

---

There are two main ways to upload files to GitHub:  
- ✅ Using the GitHub website (for small uploads)  
- ✅ Using Git & the command line (recommended for projects)

---

## ✅ Method 1: Upload via GitHub Website

1. Go to [https://github.com](https://github.com) and log in.
2. Click the **"+"** icon in the top right → **"New repository"**.
3. Name your repository and click **"Create repository"**.
4. On the new repo page, click **"Add file" → "Upload files"**.
5. Drag & drop your files or click to select.
6. Scroll down, add a commit message.
7. Click **"Commit changes"**.

---

## ✅ Method 2: Upload Using Git

### 🛠 Prerequisites & Steps
- [Download Git](https://git-scm.com/downloads)
- Create a [GitHub account](https://github.com)

### Step 1: Go to your project folder
```
cd path/to/your/project
```

### Step 2: Initialize a Git repository
```
git init
```

### Step 3: Add all your files
```
git add .
```

### Step 4: Commit your files
```
git commit -m "Initial commit"
```

### Step 5: Add your GitHub repo as remote
```
git remote add origin https://github.com/<your-username>/<your-repo-name>.git
```

### Step 6: Push your files

using 'main' as default branch

```
git branch -M main
git push -u origin main
```

You’ll see your repository online — your files have been uploaded successfully.

---

## 🎉 Done!

You now know how to upload your files to your GitHub Repository.