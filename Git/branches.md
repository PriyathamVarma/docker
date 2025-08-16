# Branches 🌿

Branches are used to **track changes and build new features** without breaking the main project.  
They let multiple developers work in parallel and merge their work safely.

Think of a branch as a **copy of the project timeline** where you can experiment without affecting the main code.

---

## Basic Git Workflow 🔄

```bash
# Step 1: Initialize a Git repository in your working directory
git init
# (creates a hidden .git folder to track changes)

# Step 2: Check your current branch
git branch
# (by default, Git creates "master" or "main")

# Step 3: Check the status of your working directory
git status
# (tells you which files are staged, modified, or untracked)

# Step 4: Add files to the staging area
git add .
# (stages all files for commit)

# Step 5: Commit with a message
git commit -m "Initial commit"
# (creates a snapshot of the project with a message)

# Step 6: Configure Git (only once per machine)
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
# (sets your identity for commits)

# Step 7: Rename the default branch to 'main'
git branch -M main

# Step 8: View commit history
git log
# (shows commits, authors, timestamps, and hashes)
```

---

## Creating & Switching Branches 🛠️

```bash
# Create a new branch
git branch feature-login

# Switch to the new branch
git checkout feature-login

# Create & switch in one step
git checkout -b feature-login
```

Now you’re working inside the `feature-login` branch.
All commits will go here until you switch back.

---

## Merging Branches 🔀

When your feature is ready, merge it back into `main`.

```bash
# Switch to main branch
git checkout main

# Merge changes from feature branch into main
git merge feature-login
```

If there are conflicts, Git will tell you which files need fixing.
After fixing → `git add <file>` → `git commit`.

---

## Deleting Branches 🧹

```bash
# Delete local branch after merging
git branch -d feature-login

# Force delete (if not merged)
git branch -D feature-login
```

---

## Visualizing Branches 🖼️

Diagram of branching:

```
(main) ----A----B----C---------------
                \
               (feature-login)---D---E
```

- `A, B, C` → Commits on main branch
- `D, E` → Commits on feature-login branch
- Once feature is complete, merge `D & E` into `main`.

---

## Useful Commands Recap 📋

| Command                    | Description                 |
| -------------------------- | --------------------------- |
| `git init`                 | Initialize repo             |
| `git branch`               | List branches               |
| `git checkout <branch>`    | Switch branch               |
| `git checkout -b <branch>` | Create & switch branch      |
| `git branch -M main`       | Rename default branch       |
| `git log`                  | View commit history         |
| `git merge <branch>`       | Merge a branch into current |
| `git branch -d <branch>`   | Delete branch               |

---

## Other commands

| Command                                         | Description                  |
| ----------------------------------------------- | ---------------------------- |
| `git push --set-upstream origin <branche-name>` | Changing the branch upstream |

---

### Merging branch

git merge <branch-to-merge> from master branch

### Understandinh HEAD

- Latest commits in a branch

### Understanding Detached HEAD

### Git switch(git 2.23)

### deleting working directory changes

- git rm <file-name>

### Undoing unstaged changes

git clean

### Undoing staged changes

git reset <log>

git restore

---

✅ **Summary**

- Branches = safe environment to develop features.
- You can **create, switch, merge, delete** branches easily.
- Branching makes Git powerful for teamwork and large projects.
