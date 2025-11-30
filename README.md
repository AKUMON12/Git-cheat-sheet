# 📚 GitHub Workflow & Command Cheat-Sheet

A full guide to Git commands, folder setup, GitHub collaboration, branching, merging, and MySQL access using XAMPP — all in one place.

---

## 🔘 📁 Basic Terminal / Git Folder Structure Commands

| Command | Purpose / Description |
|---------|------------------------|
| `mkdir <folder-name>` | **Make Directory** – Creates a new folder at the current location. |
| `cd <folder-name>` | **Change Directory** – Navigates into a specified folder. |
| `touch <filename>` | **Create File** – Creates an empty file in the current folder. |
| `cd ..` | **Go Up a Level** – Moves to the parent directory (one level up). Useful when navigating back after creating a folder structure. |

---

## 🔘 🎯 Essential Git Commands (Summary)

| Command | Purpose |
|---------|---------|
| `git clone <repo_URL>` | **Clone a Repository** – Downloads a copy of a remote GitHub repository to your local system. |
| `cd <repository-name>` | **Navigate into Project** – Moves into the project directory. |
| `git status` | **Check File Changes** – Lists files that are modified, added, or deleted. |
| `git add .` | **Stage All Changes** – Prepares all changed files for commit. |
| `git commit -m "message"` | **Save Changes** – Commits staged changes with a message. |
| `git push origin main` | **Push to GitHub** – Uploads commits to the `main` branch on GitHub. |
| `git pull origin main` | **Pull from GitHub** – Downloads and integrates changes from the remote repository to local. |

---

## 🔘 🌱 Working on a Specific Branch (`frontend_Elvinia` example)

### ✅ Step-by-Step Git Branch Workflow

```bash
git clone https://github.com/<username>/<repository-name>.git   # Clone the repository
cd <repository-name>                                            # Enter the repository folder
git branch -a                                                   # Show all branches (local and remote)
git checkout -b <branch_name>                                   # Switch to a specific branch
git pull origin <branch_name>                                   # Update local branch with latest remote changes
code .                                                          # Open folder in code editor (e.g., VS Code)
git status                                                      # Check file changes
git add .                                                       # Stage all changes
git commit -m "Describe your changes"                           # Commit changes
git push origin <branch_name>                                   # Push changes to the remote branch
```

### 💡 Additional Branching Tips

- `git branch` – Shows all local branches. The active one is marked with `*`.
- `git pull origin <branch_name>` – Always pull before pushing to avoid merge conflicts.
- `git checkout -b backend-feature-xyz` – Create a new feature branch from the current branch.

---

## 🔘 🗂️ Uploading Local Files to GitHub (First-Time Setup)

### ✅ Initial Setup & First Push

```bash
cd path/to/your-project-folder             # Navigate to your local folder
git init                                   # Initialize a Git repository
git add .                                  # Add all files to staging
git commit -m "Initial commit"             # Commit with a message
git branch -M main                         # Renames the current branch to main
git remote add origin <repo_URL>           # Link your local repo to GitHub
git push -u origin main                    # Push to the main branch
```

---

## 🔘 📄 Uploading a Specific Edited File

When you edit just one file and want to commit only that:

```bash
git status                                 # Check modified files
git add <filename>                         # Stage the specific file
git commit -m "Updated <filename>"         # Commit with a specific message
git push origin main                       # Push changes
```

---

## 🔘 🔁 Pull → Edit → Push Workflow

### Step-by-Step

1. **Pull Latest Changes:**

```bash
cd path/to/your-project-folder
git pull origin main
```

2. **Edit Files** in VS Code or any editor.

3. **Stage and Commit:**

```bash
git status
git add .
git commit -m "Description of your changes"
```

4. **Push Back:**

```bash
git push origin main
```

---

## 🔘 🔀 Git Branching & Merging Guide

### 1️⃣ Setup

```bash
git clone <repo_URL>   # Clone a repo
git init               # Or initialize a new local repo
```

### 2️⃣ Create & Switch Branches

```bash
git checkout -b <branch_name>   # Create and switch to new branch
git branch                      # Show current branch
```

### 3️⃣ Stage & Commit

```bash
git add <filename>  # Or use git add . to stage all
git commit -m "Describe changes"
```

### 4️⃣ Push Branch

```bash
git push -u origin <branch_name>  # Push new branch
git push                          # Push updates
```

### 5️⃣ Switch Branch

```bash
git checkout <branch_name>
```

### 6️⃣ Merge into Main

```bash
git checkout main
git pull origin main              # Optional but recommended
git merge <branch_name>           # Merge feature branch into main
```

### 7️⃣ Resolve Merge Conflicts (if any)

When conflicts happen:

```bash
# Manually edit files where conflicts are marked with <<<<<<<, =======, >>>>>>>
git add <resolved_file>
git commit -m "Resolve merge conflicts"
```

### 8️⃣ Push Merged Main Branch

```bash
git push origin main
```

### 9️⃣ Delete Branch (Optional)

```bash
git branch -d <branch_name>        # Delete local merged branch
git branch -D <branch_name>        # Force delete local branch
git push origin --delete <branch_name>  # Delete remote branch
```

---

## 🔘 ⬇️ Cloning a Specific Branch Only

### ✅ One-Branch Clone Workflow

```bash
git --version                                        # Check Git is installed
cd /path/to/your/directory                           # Navigate where to clone
git clone --single-branch --branch <branch-name> https://github.com/username/repository.git
cd repository                                        # Move into cloned folder
git branch                                           # Confirm branch
git pull origin <branch-name>                        # Pull updates (optional)
```

### 🔍 Notes:

- Switch to another branch later:
```bash
git fetch origin <branch-name>
git checkout <branch-name>
```

- Fetch all branches (without re-cloning):
```bash
git fetch --all
```

---

## 🔘 📌 Pull Requests → Merging into `staging` & `main`

### 1. Create a Pull Request

- Go to **Pull Requests** tab on GitHub.
- Click **New Pull Request**.
- Set:
  - Base branch: `staging`
  - Compare branch: `<your-branch>`
- Add description and submit PR.

### 2. Review & Merge

- **Leader (e.g., Santoya)** reviews and merges to `staging`.
- After testing, `staging` is merged into `main`.

---

## 🔘 🛠️ MySQL via XAMPP Shell

```bash
# 1. Open XAMPP Shell
# 2. Login to MySQL:
mysql -u root -p

# 3. Select your database:
USE student_info_system;

# 4. Show all tables:
SHOW TABLES;
```

---
