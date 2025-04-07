# 🐙 Git Cheatsheet

A quick reference guide to commonly used Git and GitHub commands. 🎉

---

## 📋 Table of Contents

- [Configuration](#configuration)
- [Creating Repositories](#creating-repositories)
- [Cloning Repositories](#cloning-repositories)
- [Making Changes](#making-changes)
- [Branching & Merging](#branching--merging)
- [Merge Conflicts](#merge-conflicts)
- [Inspecting & Comparing](#inspecting--comparing)
- [Undoing Changes](#undoing-changes)
- [Stashing](#stashing)
- [Remote Repositories](#remote-repositories)
- [Tags](#tags)
- [GitHub Workflow](#github-workflow)
- [Git Bash Shortcuts](#git-bash-shortcuts)
- [Additional Tips](#additional-tips)

---

## ⚙️ Configuration

Configure your identity and editor:

```bash
# Set user name
git config --global user.name "Your Name"

# Set email
git config --global user.email "you@example.com"

# Set default editor (e.g., VSCode)
git config --global core.editor "code --wait"

# View all settings
git config --list
```😊

---

## 🆕 Creating Repositories

```bash
# Initialize a new Git repository in current folder
git init

# Create README and push to GitHub
echo "# Project Title" >> README.md
git add README.md
git commit -m "Add README"

# Add remote origin and push to GitHub
git remote add origin https://github.com/username/repo.git
git branch -M main
git push -u origin main
```🚀

---

## 📥 Cloning Repositories

```bash
# Clone an existing repository
git clone https://github.com/username/repo.git

# Clone via SSH
git clone git@github.com:username/repo.git
```🔗

---

## 🛠 Making Changes

```bash
# Create a new empty file or update timestamp
touch <filename>  # 📄

# Check repository status
git status  # 🧐

# Stage files for commit
git add <file1> <file2>  # ➕

# Stage all changes
git add .  # 🔥

# Commit staged changes
git commit -m "Your commit message"  # 💬

# Commit with verbose diff
git commit -v  # 🔍
```✨

---

## 🌿 Branching & Merging

```bash
# List branches
git branch  # 🌿

# Create a new branch
git branch feature-branch  # 🌱

# Switch to branch
git checkout feature-branch  # 🚶

# Create and switch in one command
git checkout -b feature-branch  # 🌱➡️🚶

# Merge branch into current
git checkout main
git merge feature-branch  # 🌿🔀

# Delete local branch
git branch -d feature-branch  # ❌🌱

# Delete remote branch
git push origin --delete feature-branch  # 🌐❌🌱
```👍

---

## ⚔️ Merge Conflicts

When merging branches, you may encounter conflicts if the same lines were changed differently:

```bash
# Attempt to merge feature branch into main
git checkout main
git merge feature-branch  # ⚔️
```

If there are conflicts, Git will pause the merge and mark conflicted files:

```bash
# View files with conflicts
git status  # 🛑
```

Conflict markers look like this in the file:

```diff
<<<<<<< HEAD
Your changes on main branch
=======
Changes from feature-branch
>>>>>>> feature-branch
```

**To resolve conflicts:**
1. Open the conflicted files and decide which changes to keep (or combine them). ✏️
2. Remove the conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`). 🧹
3. Stage the resolved files:
   ```bash
   git add <file>  # ✅
   ```
4. Continue the merge by committing:
   ```bash
   git commit -m "Resolve merge conflicts between main and feature-branch"  # 🎉
   ```

**Abort a merge:**

```bash
# If you want to cancel the merge and return to the previous state
git merge --abort  # ❌🔀
```

---

## 🔍 Inspecting & Comparing

```bash
# Show commit history
git log  # 📜

git log --oneline --graph --decorate --all  # 🌳

# Show changes (unstaged)
git diff  # ⚡

# Show staged changes
git diff --staged  # 🔍

# Show changes for a file
git diff <file>  # 📄
```👀

---

## 🔄 Undoing Changes

```bash
# Unstage a file
git reset HEAD <file>  # ↩️

# Discard unstaged changes
git checkout -- <file>  # 🗑️

# Amend last commit (without changing message)
git commit --amend --no-edit  # 🖊️

# Reset to a previous commit (destructive)
git reset --hard <commit-hash>  # 💥

# Revert a commit (safe)
git revert <commit-hash>  # 🔄
```🛡️

---

## 🧳 Stashing

```bash
# Stash changes
git stash  # 🏷️

# Stash with message
git stash save "WIP: message"  # 🏷️📝

# List stashes
git stash list  # 📋

# Apply latest stash
git stash apply  # 🔄

# Apply and drop stash
git stash pop  # 📥

# Drop a stash
git stash drop stash@{0}  # ❌

# Clear all stashes
git stash clear  # 🧹
```🚀

---

## 🌐 Remote Repositories

```bash
# Show remotes
git remote -v  # 🌐

# Add remote
git remote add origin <url>  # ➕

# Fetch changes
git fetch origin  # ⬇️

# Pull changes and merge
git pull origin main  # ⬇️🔀

# Push changes
git push origin main  # ⬆️
```🔗

---

## 🏷️ Tags

```bash
# List tags
git tag  # 🏷️

# Create annotated tag
git tag -a v1.0 -m "Release v1.0"  # 🏷️✨

# Push tag to remote
git push origin v1.0  # 🌐🏷️

# Push all tags
git push origin --tags  # 🌐🏷️🚀
```🎯

---

## 🚀 GitHub Workflow

1. Fork a repository on GitHub. 🍴
2. Clone your fork locally. 📥
3. Create a feature branch. 🌱
4. Make changes and commit. 💬
5. Push branch to your fork. ⬆️
6. Open a Pull Request against the upstream repository. 🔀
7. Address review comments. 📝
8. Merge when approved. ✅

---

## ⌨️ Git Bash Shortcuts

| Shortcut         | Description                             |
|------------------|-----------------------------------------|
| Ctrl + L         | Clear screen                            |
| Tab              | Autocomplete file/folder names          |
| Up/Down Arrows   | Navigate command history                |
| Ctrl + R         | Reverse search command history          |
```⚡

---

## 💡 Additional Tips

- Use `.gitignore` to exclude files/folders. 🚫
- Write clear, concise commit messages. 🖋️
- Pull before pushing to avoid conflicts. 🔄
- Review changes with `git status` and `git diff` often. 🧐
- Use branching strategy (e.g., Git Flow, GitHub Flow). 🌳

---

*Happy coding!* 🎉

