# Git Version Control Guide

### A Complete Introduction for Absolute Beginners

---

## What Even Is Git?git status

Git is a free, open-source, distributed version control system (VCS) designed to manage changes to files or source code during software development. It allows multiple developers to work collaboratively on the same project without overwriting each other's work, tracking every changes made, and enabling users to revert to previous versions if needed.

Imagine you're writing a long essay. Every time you make big changes, you save a copy: `essay_v1.docx`, `essay_v2.docx`, `essay_FINAL.docx`, `essay_FINAL_real.docx`...

Git replaces that chaos with a clean, automatic system. It tracks every change you make to your project, lets you write a note explaining _why_ you made it, and lets you go back to any earlier version — instantly.

Git is used by virtually every software team in the world. Learning it is one of the highest-value skills you can pick up as a developer, data scientist, or anyone who works with files and code.

---

## Why Should You Learn It?

- ✅ Never lose work again — every version is saved
- ✅ Understand what changed, when, and why
- ✅ Experiment freely without breaking anything
- ✅ Collaborate with others on the same project
- ✅ It's required for almost every tech job

---

## How Git Thinks About Your Project

Before learning commands, it helps to understand Git's mental model.

Git thinks of your project in **three zones**:

```
[Working Directory]  →  [Staging Area]  →  [Repository]
  (your files)           (what you're       (saved history /
                          about to save)      "commits")
```

1. **Working Directory** — your actual files on disk. You edit these normally.
2. **Staging Area** — a "preview" of what your next save will include. You choose what goes here.
3. **Repository** — the permanent record. Once committed, it's in Git's history forever.

The two-step process (stage → commit) might feel awkward at first, but it's powerful: it lets you save only _some_ of your changes in one commit, keeping your history clean and meaningful.

---

## Part 1 — Setting Up Git

### Install Git

- **Mac**: run `git --version` in Terminal — it will prompt you to install if needed
- **Windows**: download from [git-scm.com](https://git-scm.com)
- **Linux**: `sudo apt install git`

### Introduce Yourself to Git

Git needs to know who you are so it can label your work. Run these once:

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

---

## Part 2 — Starting a Repository

### Option A: Start fresh in a new folder

```bash
mkdir my-project
cd my-project
git init
```

`git init` creates a hidden `.git` folder — that's where Git stores everything. You never need to touch it directly.

### Option B: Clone an existing project (from GitHub, etc.)

```bash
git clone https://github.com/username/repo-name.git
```

This downloads the entire project, including its full history, to your machine.

---

## Part 3 — The Daily Workflow

This is what you'll do most often:

### Step 1: Check what's changed

```bash
git status
```

This shows you three categories:

- **Untracked files** — new files Git has never seen
- **Modified files** — existing files you've changed
- **Staged files** — changes ready to be committed

Run `git status` constantly. It's completely safe and tells you exactly where you stand.

### Step 2: Stage your changes

Add specific files:

```bash
git add filename.py
```

Add everything in the current folder:

```bash
git add .
```

> **Tip:** Be thoughtful about `git add .` — it stages _everything_, including files you may not want to commit. Check `git status` first.

### Step 3: Commit with a message

```bash
git commit -m "Add data cleaning script for missing values"
```

A commit is a permanent snapshot. The `-m` flag lets you write a short message describing what you did.

**Writing good commit messages:**

| ❌ Bad      | ✅ Good                                    |
| ----------- | ------------------------------------------ |
| `"fix"`     | `"Fix crash when input file is empty"`     |
| `"changes"` | `"Add user login form with validation"`    |
| `"stuff"`   | `"Remove duplicate rows from raw dataset"` |

Write messages as if you're telling a colleague what you did — your future self will thank you.

### Putting it all together

```bash
# 1. See what changed
git status

# 2. Stage the changes you want
git add analysis.py

# 3. Save a snapshot with a message
git commit -m "Add exploratory analysis for sales data"
```

---

## Part 4 — Viewing History

### See all past commits

```bash
git log
```

Shows each commit with its ID, author, date, and message.

For a compact view:

```bash
git log --oneline
```

Output looks like:

```
a3f8c21 Fix bug in data loader
9d12e05 Add model training script
3b77a1c Initial project setup
```

### See what changed in a specific commit

```bash
git show a3f8c21
```

---

## Part 5 — Undoing Things

This is where Git really saves you.

### Undo changes to a file (before staging)

You edited a file but want to go back to how it was at the last commit:

```bash
git restore filename.py
```

⚠️ This permanently discards your unsaved changes to that file.

### Unstage a file (before committing)

You staged a file but changed your mind:

```bash
git restore --staged filename.py
```

The file stays modified — it's just removed from the staging area.

### Go back to an old version (safely)

```bash
git checkout a3f8c21
```

This lets you _look at_ an old version without deleting anything. To go back to normal:

```bash
git checkout main
```

---

## Part 6 — Branches

Branches let you work on new ideas without touching your main, working code.

Think of it like making a photocopy of your project to experiment on — and then merging your changes back in if they work out.

### Create a new branch and switch to it

```bash
git switch -c my-new-feature
```

(`-c` means "create")

### See all branches

```bash
git branch
```

The current branch has a `*` next to it.

### Switch between branches

```bash
git switch main
git switch my-new-feature
```

### Merge a branch back into main

Once your experiment works:

```bash
git switch main
git merge my-new-feature
```

### Delete a branch you no longer need

```bash
git branch -d my-new-feature
```

---

## Part 7 — Working with GitHub (Remotes)

A **remote** is a copy of your repository stored online — typically on GitHub, GitLab, or Bitbucket. It lets you back up your work and collaborate with others.

### Connect your local repo to GitHub

After creating a new repo on github.com:

```bash
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO.git
```

`origin` is just the conventional nickname for your main remote.

### Push your commits to GitHub

```bash
git push -u origin main
```

(`-u` sets the default so future pushes just need `git push`)

### Pull changes from GitHub

Download commits that others (or you on another machine) have pushed:

```bash
git pull
```

### Typical collaboration flow

```bash
git pull                        # get latest changes first
# ... make your edits ...
git add .
git commit -m "Your message"
git push                        # send your commits up
```

---

## Part 8 — The `.gitignore` File

Some files should never be committed: passwords, API keys, large data files, auto-generated folders.

Create a file called `.gitignore` in your project root and list what to exclude:

```
# Ignore Python cache files
__pycache__/
*.pyc

# Ignore environment files with secrets
.env

# Ignore large data files
data/raw/*.csv

# Ignore OS clutter
.DS_Store
```

Git will completely ignore anything listed here.

---

## Quick Reference Cheat Sheet

```bash
# Setup
git config --global user.name "Name"
git config --global user.email "email"

# Starting out
git init                        # new repo
git clone <url>                 # download existing repo

# Daily workflow
git status                      # see what changed
git add <file>                  # stage a file
git add .                       # stage everything
git commit -m "message"         # save a snapshot

# History
git log                         # full history
git log --oneline               # compact history

# Undoing
git restore <file>              # discard file changes
git restore --staged <file>     # unstage a file

# Branches
git switch -c <branch>          # create + switch
git switch <branch>             # switch branch
git merge <branch>              # merge into current
git branch -d <branch>          # delete branch

# Remotes (GitHub)
git remote add origin <url>     # connect to remote
git push -u origin main         # first push
git push                        # push commits
git pull                        # get latest commits
```

---

## Common Mistakes to Avoid

| ❌ Mistake                                    | ✅ Fix                                                          |
| --------------------------------------------- | --------------------------------------------------------------- |
| Committing passwords or API keys              | Use `.gitignore` and a `.env` file for secrets                  |
| Vague commit messages like `"fix"`            | Describe _what_ and _why_: `"Fix null error in loader"`         |
| Only committing at the end of a big day       | Commit small and often — easier to undo specific changes        |
| Forgetting to `git pull` before starting work | Always pull first to avoid conflicts                            |
| Panicking when Git says "merge conflict"      | It's just Git asking you to manually pick which version to keep |

---

## Where to Practice

- **[learngitbranching.js.org](https://learngitbranching.js.org)** — Visual, interactive Git exercises in your browser
- **[github.com](https://github.com)** — Create a free account and make your first real repo
- **[ohshitgit.com](https://ohshitgit.com)** — Plain-English fixes for common Git disasters

---

## You're Ready

Git has a reputation for being confusing, but the daily reality is simpler than it seems: `status` → `add` → `commit` → `push`. That covers 90% of what you'll do.

Start by creating a repo for a personal project, making some commits, and pushing it to GitHub. The commands will become muscle memory faster than you think.
