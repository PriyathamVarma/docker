# GitHub Deep Dive

## What is GitHub?

- A **cloud-based hosting service** for Git repositories.
- Provides collaboration tools for developers to share, manage, and track changes.
- Combines **Git (VCS)** with features like:
  - Pull requests
  - Issues
  - Actions (CI/CD)
  - Wikis
  - Project boards

---

## Personal Access Tokens (PATs)

- Used instead of passwords when pushing/pulling from GitHub.
- Acts as an authentication mechanism with **scopes/permissions**.
- Generated from:  
  `Settings → Developer Settings → Personal Access Tokens`

**Example:**

```bash
git clone https://<username>@github.com/<username>/<repo>.git
Username: <your-username>
Password: <your-PAT>
```

---

## Tracking Branches in Remote and Local

### `git fetch`

- Downloads **new data** from remote but doesn’t integrate into local.

```bash
git fetch origin
```

### `git pull`

- Fetch + Merge (or Rebase).
- Updates your branch with remote changes.

```bash
git pull origin main
```

### `git remote`

- Shows remote connections.

```bash
git remote -v
```

### `git clone`

- Clones a remote repo into your local system.

```bash
git clone https://github.com/user/repo.git
```

### `git branch -vv`

- Shows local branches with their upstream (tracking) branches.

```bash
git branch -vv
```

---

## Deleting Remote Branches

- Delete a branch from the remote repository.

```bash
git push origin --delete branch-name
```

OR

```bash
git push origin :branch-name
```
