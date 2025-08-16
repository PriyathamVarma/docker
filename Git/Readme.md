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
   


---

## How Git Works ⚙️

Git is a **distributed version control system (VCS)**.  
That means it keeps track of all changes to your project over time and lets multiple developers collaborate without conflicts.

### How Version Control Works 📜
- Every time you **save (commit)** your code in Git, it takes a **snapshot** of your files.
- Each snapshot is stored with:
  - A unique ID (SHA hash) 🔑
  - The author’s name ✍️
  - Date and time of the change ⏰
  - Commit message 📝
- You can:
  - Go back to an earlier snapshot if something breaks.
  - See what changed between versions.
  - Work with teammates without overwriting their work.

Example Timeline:

```

Commit 1 → Initial project setup
Commit 2 → Added login feature
Commit 3 → Fixed login bug
Commit 4 → Added profile page

```

If Commit 4 introduces a bug, you can **rollback** to Commit 3 instantly.

---

### How Branches Work 🌿

Branches allow you to **work on new features** without disturbing the `main` branch (the stable code).  
- By default, Git creates a branch called `main` (or `master`).
- You can create another branch, like `feature-login`, and work there.
- Once the feature is complete → merge back into `main`.

Example:

```

(main) ----A----B----C------------

(feature-login)---D---E

````

- `A, B, C` are commits in the `main` branch.  
- `D, E` are commits in the `feature-login` branch.  
- After testing, `D & E` can be merged into `main`.

Common Commands:

```bash
git branch feature-login      # Create branch
git checkout feature-login    # Switch to branch
git checkout -b feature-login # Create + switch in one step
git merge feature-login       # Merge changes into current branch
````

---

## Installing Git 🖥️

### Installing Git on Windows 🪟

1. Go to [Git for Windows](https://git-scm.com/download/win).
2. Download the `.exe` file.
3. Run installer with these options:

   * Choose **Git Bash** (comes with Unix-like terminal).
   * Select **Use Git from Command Prompt**.
   * Choose **OpenSSL** for HTTPS transport.
4. Verify installation:

   ```bash
   git --version
   ```

> Tip: Use **Git Bash** on Windows for a Linux-like command line.

---

### Installing Git on macOS 🍏

1. Install Git via **Homebrew**:

   ```bash
   brew install git
   ```

   (If you don’t have Homebrew, install it first from [brew.sh](https://brew.sh))
2. Or install via Xcode Command Line Tools:

   ```bash
   xcode-select --install
   ```
3. Verify:

   ```bash
   git --version
   ```

---

## Installing Code Editor – VS Code 💻

Most developers use **Visual Studio Code (VS Code)** for Git integration.

1. Download from [VS Code website](https://code.visualstudio.com/).
2. Install and open the application.
3. Add Git integration:

   * Open **Extensions** (sidebar icon or `Ctrl+Shift+X`).
   * Search for **GitLens** → Install (gives extra Git insights).
   * Optional: Install **GitHub Pull Requests and Issues** extension.

Now you can:

* See changes (diffs) inside VS Code.
* Commit, push, and pull without leaving the editor.
* Manage GitHub PRs from inside VS Code.

---

✅ **Summary of This Section**

* Git tracks changes using commits (snapshots).
* Branches let you develop features without breaking main code.
* Install Git on Windows (Git Bash) or macOS (Homebrew/Xcode).
* Use VS Code as your main editor with Git integrations.





