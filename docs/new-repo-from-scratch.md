# 🚀 HOW TO CREATE A NEW REPO FROM SCRATCH
## Using Terminal + Git + GitHub CLI (gh)
### Lieutenant Commander Data & Science Officer Spock
### Created: 27.05.2026

---

## 🧠 Mental Model — Before We Start

```
mkdir        →  "Create an empty room on your laptop" 🏠
git init     →  "Put a diary in that room — now git tracks changes" 📓
git add      →  "Pick up files and put them in an envelope" 📬
git commit   →  "Seal the envelope with a label — this is a snapshot" 📸
gh repo create → "Create a mailbox on GitHub and send the envelope there" 📮
git push     →  "All future envelopes go to that mailbox automatically" 🔄
```

---

## 📋 PREREQUISITES

Before following this guide, make sure:
- [ ] `git` is installed — run `git --version` to check
- [ ] `gh` (GitHub CLI) is installed — run `gh --version` to check
- [ ] You are logged in to GitHub CLI — run `gh auth status` to check
- [ ] You have a GitHub account

---

## 🪜 STEP-BY-STEP

### Step 0 — Decide where the repo will live locally

All repos live in the same parent folder for consistency:
```
/Users/your-name/Desktop/vs_code/
```

### Step 1 — Create the local folder

```bash
mkdir /Users/your-name/Desktop/vs_code/your-repo-name
```

**Expected output:** No output = success. The folder now exists.

```bash
mkdir        →  "make directory" — creates a new empty folder 📁
```

---

### Step 2 — Initialize git

```bash
cd /Users/your-name/Desktop/vs_code/your-repo-name
git init
```

**Expected output:**
```
Initialized empty Git repository in /path/to/your-repo-name/.git/
```

You may also see a hint about branch naming — ignore it for now, we fix it in Step 3.

---

### Step 3 — Rename default branch to main

```bash
git branch -m main
```

**Why:** Git's default branch is still called `master` in older versions. GitHub uses `main`. We rename it now to avoid confusion later.

**Expected output:** No output = success.

---

### Step 4 — Create your first files

At minimum, create:
- `README.md` — what the project is
- `.gitignore` — what git should NOT track

Example for a Python project `.gitignore`:
```
__pycache__/
*.py[cod]
.venv/
venv/
.env
.DS_Store
.ipynb_checkpoints/
.vscode/
```

You can create files directly in terminal:
```bash
echo "# your-repo-name" > README.md
```

Or write them with a text editor / VS Code.

---

### Step 5 — Stage all files

```bash
git add .
```

**What this does:** Stages ALL files in the current folder for commit.
The `.` means "everything here".

**Verify what will be committed:**
```bash
git status
```

Read the output carefully. Only files listed under "Changes to be committed" will go into the commit. Make sure nothing private is staged.

---

### Step 6 — First commit

```bash
git commit -m "Initialize repo

- README with project purpose
- .gitignore for Python/macOS
- Initial folder structure"
```

**Commit message rule:**
- First line: short imperative summary (max 72 characters)
- Blank line
- Bullet points with details

**Expected output:**
```
[main (root-commit) abc1234] Initialize repo
 2 files changed, 10 insertions(+)
```

---

### Step 7 — Create GitHub repo and push in one command

```bash
gh repo create your-repo-name --public --source=. --remote=origin --push
```

**What each flag does:**
```
your-repo-name   →  name of the repo on GitHub
--public         →  visible to everyone (use --private for private repos)
--source=.       →  use the current folder as source
--remote=origin  →  name the GitHub connection "origin" (standard convention)
--push           →  push the first commit immediately
```

**Expected output:**
```
✓ Created repository your-username/your-repo-name on github.com
  https://github.com/your-username/your-repo-name
✓ Added remote
✓ Pushed commits to https://github.com/your-username/your-repo-name.git
```

---

### Step 8 — Verify

```bash
git status
git log --oneline
```

**Expected output:**
```
On branch main
Your branch is up to date with 'origin/main'.
nothing to commit, working tree clean
```

```
abc1234 Initialize repo
```

Open the GitHub URL from Step 7 in your browser — you should see your repo live.

---

## 🔧 TROUBLESHOOTING

**Problem: `gh: command not found`**
GitHub CLI is not installed.
Fix: `brew install gh` (on macOS)

**Problem: `gh auth status` shows "not logged in"**
Fix: `gh auth login` — follow the prompts, choose GitHub.com and HTTPS.

**Problem: branch is called `master` after push**
Fix before pushing: `git branch -m main`
If already pushed: `git push origin --delete master` then `git push -u origin main`

**Problem: committed a file you didn't want**
Fix: `git rm --cached filename` then commit again.
This removes the file from git tracking but keeps it on your laptop.

**Problem: wrong commit message**
Fix (only before pushing): `git commit --amend -m "corrected message"`

---

## 🧠 Mental Model — Summary

```
Local laptop                    GitHub (cloud)
─────────────────               ──────────────────
mkdir        → empty folder
git init     → start tracking
git add .    → stage files
git commit   → save snapshot
                              gh repo create → create mailbox
git push     ──────────────► sends snapshot to GitHub
```

---

## ✅ Notes for Students

**What is the most important thing to understand here?**

`git` and `gh` are two separate tools. `git` manages your local history — it works entirely on your laptop. `gh` is a command-line interface for GitHub — it talks to the internet. You need both, but they do different things. Most confusion comes from mixing them up.

**What is the most common mistake?**

Forgetting to run `git branch -m main` before the first push. You end up with a `master` branch locally and `main` on GitHub, and git gets confused about which one to track. Do it right after `git init` — every time.

The second most common mistake: committing without reading `git status` first. Always check what is staged. One accidental commit of a `.env` file or a private document to a public repo is a serious problem that is painful to undo.

**What should you remember next time?**

The order never changes: `mkdir` → `git init` → `git branch -m main` → create files → `git add` → `git status` (read it!) → `git commit` → `gh repo create --push`. Memorize this sequence. After ten repos, it takes thirty seconds.
