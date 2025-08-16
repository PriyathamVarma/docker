# Git & GitHub

## What is Git? 🤔

![Git](https://github.com/PriyathamVarma/docker/blob/main/Images/Git.drawio.png)

- **[Git](https://git-scm.com/)** is an **open-source distributed version control system** created by **Linus Torvalds** in 2005 (yes, the creator of Linux 🐧).
- It allows developers to:
  - Track changes in source code 📜
  - Revert back to previous versions if needed 🔄
  - Work simultaneously with other developers without overwriting each other’s work 🤝
- **Distributed** means every developer’s machine has the **entire history of the project**, not just the latest version.  
  This makes it **faster** and allows work even **without internet**.

### Why do we need Git? 🚀
- Keeps **history of changes** → like a time machine ⏳ for your code.
- Provides **branching** → multiple versions of a project can be developed in parallel.
- Helps in **collaboration** → multiple developers can work without stepping on each other’s code.
- Allows **rollback** → mistakes can be undone safely.

### Example Workflow 🛠
1. You write code in your local machine.
2. You `git add` the files to **staging**.
3. You `git commit` them with a message describing the change.
4. You can then push changes to a **remote repo** (like GitHub) so others can access them.

---

## GitHub 🌐

- **GitHub** is the **largest cloud-based development platform** built around Git.
- Think of it as a **social network for code** + **cloud hosting service for Git repositories**.
- It provides:
  - **Remote hosting** of Git repositories (so your code is safe even if your laptop dies 💻🔥).
  - **Collaboration tools** (issues, pull requests, discussions, wikis).
  - **CI/CD pipelines (GitHub Actions)** → automate testing & deployment.
  - **Security features** like Dependabot, code scanning.
  - **Integration with cloud platforms** like AWS, Azure, GCP.

### Key Features of GitHub 🧰
- **Repositories (Repos)** → Storage place for code projects.
- **Branches** → Develop features separately without breaking main code.
- **Pull Requests (PRs)** → Propose changes and request reviews from team members.
- **Issues** → Track bugs, tasks, and feature requests.
- **Actions** → Automate workflows (build, test, deploy).
- **Forking** → Copy someone else’s project to experiment or contribute.

### Why GitHub + Git? ⚡
- Git (local) helps you **version control on your machine**.
- GitHub (remote) helps you **collaborate with the world**.

Example analogy:  
- **Git** = Your personal diary 📓 (you write and save versions locally).  
- **GitHub** = Publishing your diary online 🌍 so others can read, comment, and contribute.

---

## Common Git Commands 🖥️

| Command | Description |
|---------|-------------|
| `git init` | Initialize a new Git repository |
| `git clone <url>` | Clone (download) a repo from GitHub |
| `git status` | Show changes in working directory |
| `git add <file>` | Stage changes for commit |
| `git commit -m "message"` | Commit staged changes |
| `git push` | Upload commits to remote repo |
| `git pull` | Download and merge latest changes from remote |
| `git branch` | List, create, or delete branches |
| `git checkout <branch>` | Switch branches |
| `git merge <branch>` | Merge changes from another branch |

---

## GitHub Workflow Example 📝

1. **Clone repo**
   
   ```bash
   
   git clone https://github.com/username/repo.git

   git checkout -b feature-xyz

   git add .
   git commit -m "Added feature xyz"

   git push origin feature-xyz
   
```
