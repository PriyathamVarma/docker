# Git Deep Dive 🔍

---

## Git Stash Command 📦

Sometimes you’re in the middle of changes, but need to **switch branches** or **pull updates** without committing half-done work.  
That’s where `git stash` helps.

```bash
git stash              # Save current changes to stash & clean working directory
git stash list         # Show list of stashes
git stash apply        # Apply latest stash (but keep it in stash list)
git stash pop          # Apply & remove stash
git stash drop         # Delete a specific stash
```

Example:

```bash
# Work on file, but not ready to commit
git stash
git pull origin main   # Pull latest changes safely
git stash pop          # Get back your unfinished work
```

---

## Git Reflog 🕒

`git reflog` tracks **every move of HEAD** (commits, resets, checkouts, merges).
It’s your **safety net** when commits/branches are lost.

```bash
git reflog             # Show history of HEAD movements
git checkout <commit>  # Go back to a lost commit
git branch recover <commit>  # Create a new branch from lost commit
```

👉 Use case: If you **deleted a branch by mistake**, recover it with `git reflog`.

---

## Merge Types 🔀

### 1. Fast-Forward Merge

- Happens when the target branch is **direct ancestor** of the source branch.
- Git just **moves the pointer** forward.

```bash
(main) A---B
(feature)   \---C---D
```

Merge result:

```
(main) A---B---C---D
```

Command:

```bash
git checkout main
git merge feature
```

---

### 2. Non Fast-Forward Merge (3-way merge)

- Happens when branches have diverged (different commits).
- Creates a new **merge commit**.

```
(main) A---B---C
              \
(feature)      D---E
```

Merge result:

```
(main) A---B---C---------M
              \         /
(feature)      D---E----
```

---

## Rebasing 🌱

Rebase = **replaying commits** from one branch on top of another.
Instead of creating a merge commit, it makes history **linear**.

```bash
git checkout feature
git rebase main
```

Before:

```
(main) A---B---C
              \
(feature)      D---E
```

After:

```
(main) A---B---C---D'---E'
```

⚠️ **Warning:**

- Rebase **creates new commits (D', E')** instead of moving old ones.
- Never rebase commits that were already pushed/shared.

Rule: _Rebase local, merge shared._ ✅

---

## Handling Merge Conflicts ⚔️

If two branches modify the same part of a file → conflict occurs.

Example:

```bash
git diff             # See changes
git merge feature    # Merge attempt → conflict shown
```

Files will have markers like:

```diff
code from feature branch
```

Steps:

1. Edit file manually → keep correct code.
2. Mark resolved:

   ```bash
   git add <file>
   git commit
   ```

---

## Merge vs Rebase vs Cherry Pick 🆚

| Action          | What it Does                                                  | When to Use                                    |
| --------------- | ------------------------------------------------------------- | ---------------------------------------------- |
| **Merge**       | Combines histories, keeps all commits, may add a merge commit | Safe collaboration, preserve history           |
| **Rebase**      | Moves commits onto new base, creates linear history           | Clean commit history, personal/local work      |
| **Cherry Pick** | Apply a specific commit from one branch into another          | When you want only 1 commit (not whole branch) |

Cherry Pick Example:

```bash
git checkout main
git cherry-pick <commit-hash>
```

---

## Git Tags 🏷️

Tags are used to mark specific points in history (often for **releases**).

### Creating Tags

```bash
git tag v1.0.0             # Lightweight tag
git tag -a v1.0.0 -m "Release v1.0.0"   # Annotated tag with message
```

### Listing & Viewing Tags

```bash
git tag                    # List all tags
git show v1.0.0            # Show details of tag (commit, message, diff)
```

### Pushing Tags to Remote

```bash
git push origin v1.0.0
git push --tags            # Push all tags
```

---

✅ **Summary**

- **Stash** → temporary storage for unfinished work.
- **Reflog** → recover lost commits/branches.
- **Merge** → join branches (fast-forward or 3-way).
- **Rebase** → linear history, creates new commits.
- **Cherry-pick** → copy specific commits.
- **Tags** → mark versions/releases.
