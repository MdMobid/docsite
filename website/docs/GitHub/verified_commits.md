---
sidebar_position: 3
---

# Make Verified Commits

> 🎯 **Goal**: How to make commits that show the green "Verified" badge on GitHub.

---

## ✅ What You Need:

* A GitHub account
* Git installed on your computer
* GitHub CLI or GPG/SSH key setup (explained below)

---

## ✨ What is a Verified Commit?

A **verified commit** means GitHub has confirmed the commit was made by you and was **signed** with a trusted key (GPG or SSH).

You'll see a **green Verified badge** next to the commit like this:

```
✔️ Verified
```

---

## 🎓 Method 1: Verified Commits Using SSH Key

### Step 1: Check if You Already Have an SSH Key

Open your terminal and run:

```bash
ls ~/.ssh
```

Look for a file like `id_ed25519.pub` or `id_rsa.pub`. If you don't see one, generate a new key.

### Step 2: Generate a New SSH Key (If Needed)

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

Just press Enter for each prompt.

### Step 3: Add the SSH Key to GitHub

1. Copy the SSH key:

```bash
cat ~/.ssh/id_ed25519.pub
```

2. Go to [GitHub SSH Settings](https://github.com/settings/ssh/new)
3. Paste the key, give it a name, and click **Add SSH Key**

### Step 4: Tell Git to Use This Key

Edit or create the file `~/.ssh/config`:

```
Host github.com
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_ed25519
  IdentitiesOnly yes
```

---

### Step 5: Make a Commit That is Verified

Now that your identity is confirmed by SSH:

1. Make a change to your code
2. Commit it:

```bash
git commit -m "🌟 Your message"
```

3. Push:

```bash
git push origin branch-name
```

GitHub will show the **Verified** badge!

---

## 🔐 Method 2: Verified Commits Using GPG Key

### Step 1: Install GPG

* **Windows**: Install [Gpg4win](https://gpg4win.org/)
* **macOS**: Run `brew install gnupg`
* **Linux**: Run `sudo apt install gnupg`

### Step 2: Generate a GPG Key

```bash
gpg --full-generate-key
```

* Choose option `1` (RSA and RSA)
* Use key size `4096`
* Set expiration if desired
* Enter your GitHub email address when prompted

### Step 3: List Your Keys

```bash
gpg --list-secret-keys --keyid-format LONG
```

You’ll see something like:

```
sec   rsa4096/3AA5C34371567BD2 2025-05-06 [SC]
```

Copy the part after `rsa4096/` — in this case, `3AA5C34371567BD2`

### Step 4: Tell Git to Use This Key

```bash
git config --global user.signingkey 3AA5C34371567BD2
git config --global commit.gpgsign true
```

### Step 5: Add the Key to GitHub

1. Export your public GPG key:

```bash
gpg --armor --export your_email@example.com
```

2. Copy the output
3. Go to [GitHub GPG Settings](https://github.com/settings/keys) → **New GPG key**
4. Paste and save

### Step 6: Make a Verified Commit

Now commit and push:

```bash
git commit -m "🔐 Verified via GPG"
git push origin branch-name
```

Your commit will now show as **Verified**.

---

## 🎉 Done!

You now know how to make verified commits using **either SSH or GPG**.
