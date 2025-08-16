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

## Pushing Changes

| Command                                        | Description                                             |
| ---------------------------------------------- | ------------------------------------------------------- |
| `git push --set-upstream origin <branch-name>` | Push branch to remote for the first time & set upstream |
| `git push`                                     | Push commits to the remote (after upstream is set)      |

> 💡 Setting upstream links your local branch with the remote one.  
> Next time you can just use `git push` or `git pull` without extra arguments.

---

## Merging Branches 🔀

To merge a feature branch into `main`:

```bash
git checkout main
git merge <branch-to-merge>
```

- If there are conflicts → Git will mark them inside the file (`<<<<<<<` markers).
- Fix conflicts → `git add <file>` → `git commit`.

---

## Understanding HEAD 📌

- **HEAD** points to the **current commit** you’re working on.
- Usually, HEAD points to the **latest commit of the current branch**.

Example:

```
(main) A---B---C (HEAD)
```

Here, HEAD points to commit **C** on the `main` branch.

---

## Detached HEAD State 🧩

- Happens when HEAD points **directly to a commit** instead of a branch.

- Example:

  ```bash
  git checkout a1b2c3d
  ```

  Now you’re not on `main` or any branch → just at commit `a1b2c3d`.

- Any new commits here will be "lost" unless you create a new branch:

  ```bash
  git checkout -b hotfix-123
  ```

---

## Git Switch (since Git 2.23) 🔄

`git switch` is a simpler alternative to `git checkout` for branch operations.

```bash
git switch <branch-name>        # Switch branches
git switch -c <new-branch-name> # Create & switch
```

---

## Deleting Working Directory Changes 🗑️

- Remove a file from Git & working directory:

  ```bash
  git rm <file-name>
  git commit -m "Removed file"
  ```

- If you only want to delete it from Git (but keep locally):

  ```bash
  git rm --cached <file-name>
  ```

---

## Undoing Changes 🔙

### Undoing Unstaged Changes

```bash
git restore <file>
```

- Discards changes in working directory for that file.

Or clean everything untracked:

```bash
git clean -fd
```

- `-f` = force, `-d` = delete untracked directories.
  ⚠️ Use with caution — this **permanently deletes untracked files**.

---

### Undoing Staged Changes

```bash
git reset <file>
```

- Removes file from staging area, but keeps changes in working directory.

---

## Git Reset (3 Modes) 🔧

1. **Soft Reset**

   ```bash
   git reset --soft <commit-id>
   ```

   - Moves HEAD to given commit.
   - Keeps changes in **staging area** (you can recommit them).

2. **Mixed Reset** (default)

   ```bash
   git reset <commit-id>
   ```

   - Moves HEAD to commit.
   - Keeps changes in **working directory**, unstages them.

3. **Hard Reset**

   ```bash
   git reset --hard <commit-id>
   ```

   - Moves HEAD to commit.
   - **Deletes all changes** in staging and working directory.
     ⚠️ Dangerous – cannot be undone.

---

## Deleting Branches 🧹

```bash
git branch -d <branch>   # Delete local branch (safe, only if merged)
git branch -D <branch>   # Force delete branch (even if unmerged)

git push origin --delete <branch>  # Delete remote branch
```

---

✅ **Summary**

- Branches = safe environment to develop features.
- You can **create, switch, merge, delete** branches easily.
- Branching makes Git powerful for teamwork and large projects.
- HEAD = pointer to latest commit.
- Detached HEAD = not on a branch (useful for exploring old commits).
- `git switch` is the modern way to switch branches.
- Use **reset** carefully → `--soft`, `--mixed`, `--hard` behave very differently.
- Branches can be safely deleted locally or remotely.
