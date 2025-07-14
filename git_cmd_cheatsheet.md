# Git Commands Cheatsheet  <!-- git_commands_cheatsheet.md -->

> Quick reference distilled from handwritten study notes.  
> Feel free to copy‑paste or cherry‑pick sections into your own **de‑journey** repo.

---

## 1. The Four Git Areas

| Stage | Purpose | Key Commands |
|-------|---------|--------------|
| **Working directory** | Your local files | `git checkout` (switch branch) |
| **Staging area** | Temporary holding space before a commit | `git add <file>` · `git status` |
| **Local repository** | Committed history on your machine | `git commit -m "msg"` |
| **Remote repository** | Cloud store (GitHub, Bitbucket, …) | `git push` · `git pull` · `git fetch` |

---

## 2. Everyday Workflow

```bash
# Initialise once
git init                              # turn a folder into a repo
git remote add origin <ssh-url>       # link to GitHub

# Each change set
git status                            # what changed?
git add <file> | git add .            # stage
git commit -m "feat: concise message" # snapshot
git push -u origin main               # publish (first push sets upstream)
```

*Add & commit in one go:* `git commit -am "quick fix"`

---

## 3. Syncing Code

| Action | When to use | Command |
|--------|-------------|---------|
| **Clone** entire repo | First time on a machine | `git clone <ssh/https-url>` |
| **Pull** & merge | Bring down *and* integrate remote changes | `git pull` |
| **Fetch** only | See remote changes first, merge later | `git fetch` then `git merge` |
| **Fork** | Copy a public repo to your account | GitHub ➜ **Fork** button |

---

## 4. Branching & Pull Requests

```bash
# Create & switch
git checkout -b feature/login

# List branches
git branch

# Work ➜ commit ➜ publish branch
git push -u origin feature/login

# Switch back
git checkout main

# Merge the branch locally, then push
git merge feature/login
git push origin main

# Delete local branch after merge
git branch -d feature/login
```

1. Open a **Pull Request** on GitHub.  
2. Resolve any merge conflicts, push again if needed.  
3. Repo owner merges, branch can be deleted.

---

## 5. SSH Key Setup (once per machine)

```bash
ssh-keygen -t ed25519 -C "you@example.com"   # generate (RSA 4096 also fine)
cat ~/.ssh/id_ed25519.pub                    # copy
# GitHub ➜ Settings › SSH & GPG keys › New Key
ssh -T git@github.com                        # test
```

---

## 6. Housekeeping Files

| File | Why |
|------|-----|
| **README.md** | Uses Markdown to describe the project. |
| **.gitignore** | Lists files / folders Git should *skip* (e.g. `__pycache__/`, `.venv/`). |

---

### 7. One‑Line Reference

```bash
git init && git add . && git commit -m "first commit" && git branch -M main && git remote add origin <ssh-url> && git push -u origin main
```

---

*Tip: deploy front‑end branches quickly via **Vercel** for live previews.*  
Happy version‑controlling! 🎉
