
# Git Basics – Step‑by‑Step Walkthrough

This README recreates the exact sequence of commits in this repository so you (or anyone following along) can practise core Git commands:

| Step | Files touched | Commit message |
|------|---------------|----------------|
| 1 | `index.html`, `script.js`, `style.css` | **Initial commit** |
| 2 | `index.html` | **Added new task** |
| 3 | `README.md` | **Create README.md** |
| 4 | `.gitignore`, `index.html` | **Added task 5** |
| 5 | `index.html` | **Added Task 6** |
| 6 | `login.html` on branch `feature/login` | **Added Login page** |
| 7 | merge `feature/login` → `main` | **Merge pull request #1 from ragulkumar-v/feature/login** |
| 8 | `git_cmd_cheatsheet.md` | **Git command cheatsheet** |

---

## Prerequisites
- Git installed (`git --version`)
- A GitHub account with SSH key set up

## 1 · Create the project locally

```bash
mkdir Git-Basics && cd Git-Basics

# Add initial files
touch index.html script.js style.css
code .              # or open with your editor
```

Add starter HTML/CSS/JS (see the *Initial commit* in this repo for reference) then:

```bash
git init
git add .
git commit -m "Initial commit"
```

## 2 · Create a remote repository

1. Sign in to GitHub → **New repository**
2. Name it **Git-Basics** (public or private)
3. Copy the SSH URL (`git@github.com:<user>/Git-Basics.git`)

```bash
git remote add origin git@github.com:<user>/Git-Basics.git
git branch -M main          # rename master → main if needed
git push -u origin main
```

## 3 · Iterate with small commits

### Add a new task (Step 2)

```bash
# edit index.html – add <li>Task 4</li>
git add index.html
git commit -m "Added new task"
git push
```

### Create a README (Step 3)

```bash
echo -e "# Git Basics\n\nThis a demo project for my Git tutorial." > README.md
git add README.md
git commit -m "Create README.md"
git push
```

### Add a .gitignore & Task 5 (Step 4)

```bash
echo ".env" > .gitignore
# edit index.html – add <li>Task 5</li>
git add .gitignore index.html
git commit -m "Added task 5"
git push
```

### Add Task 6 (Step 5)

```bash
# edit index.html – add <li>Task 6</li>
git add index.html
git commit -m "Added Task 6"
git push
```

## 4 · Work on a feature branch (Login page)

```bash
git checkout -b feature/login
touch login.html
# add HTML skeleton for login page
git add login.html
git commit -m "Added Login page"
git push -u origin feature/login
```

Open a **Pull Request** on GitHub → merge after review:

```bash
git checkout main
git pull                 # brings in the merge commit
```

## 5 · Add reference docs

```bash
# Assume cheatsheet already exists; otherwise create/edit
git add git_cmd_cheatsheet.md
git commit -m "Git command cheatsheet"
git push
```

## 6 · Continue…

Use branches for every new feature and keep commits focused and atomic.

---

### One‑liner to clone & run

```bash
git clone git@github.com:<user>/Git-Basics.git && cd Git-Basics
code .
```

Happy Coding! 🎉
