# GitHub Deep Dive

## Types of Accounts

- **Personal Account**  
  Individual developer account used to manage personal repositories.

- **Team/Organisational Account**  
  Shared account where multiple collaborators can manage repositories under one organization.

- **Enterprise Account**  
  For large-scale enterprises with advanced features, security, and compliance support.

---

## Pushing Commits to a Public Repository

1. **Clone the repository**

   ```bash
   git clone https://github.com/username/repo.git
   cd repo
   ```

2. **Do changes locally**

   ```bash
   # Edit your files
   ```

3. **Stage and commit**

   ```bash
   git add .
   git commit -m "your commit message"
   ```

4. **Push changes**

   ```bash
   git push origin main
   ```

---

## Collaborating in Private Repos

- Private repos require **explicit access**.
- Owner can:

  - Add collaborators directly in repo settings.
  - Control permissions (Read, Write, Admin).

- Collaborators can:

  - Clone repo using HTTPS or SSH.
  - Push/pull based on access rights.

---

## Organisations

### Adding Collaborators

- Go to repository → **Settings** → **Collaborators & teams**.
- Enter username/email of collaborator.
- Assign role: _Read / Write / Admin / Maintain / Triage_.

### Adding Organisation Members

- Navigate to **Organisation settings**.
- Go to **People → Invite member**.
- Add user by GitHub username or email.
- Assign to **Teams** with specific roles.

---

## Teams

- Teams allow you to **organize members within an organization**.
- You can **group people** based on projects, roles, or departments.
- Teams can be given **specific repository permissions** (read, write, admin).
- Communication is easier since you can **@mention teams** in issues and pull requests.

---

## Forking

Forking is the process of creating a **copy of a repository** under your GitHub account.  
This is commonly used in **open-source collaboration**.

### Workflow of Forking

1. **Fork** a repository → Create a copy of someone else’s repo in your account.

2. **Clone** the fork →

   ```bash
   git clone https://github.com/your-username/forked-repo.git
   ```

3. **Do changes locally** → Edit, commit, and test your code.

   ```bash
   git add .
   git commit -m "Added new feature"
   git push origin main
   ```

4. **Deploy changes (optional)** → Test on staging/production.

5. **Pull Request (PR)** → Submit changes back to the **main/original repository**.
   - The repo owner reviews your PR.
   - If approved, your changes are **merged into the main project**.

---

## Issues

- Issues are used to track tasks, enhancements, bugs, and discussions in a repository.
- They act as a lightweight project management tool for developers.
- Features include:
  - Title and description
  - Labels for categorization
  - Milestones to track progress
  - Assignees to allocate responsibility
  - Comments and discussions for collaboration
- Issues can be closed when resolved, and reopened if needed.

## Projects

- GitHub Projects provide a kanban-style board to manage issues and pull requests.
- They help organize work in columns such as **To Do**, **In Progress**, and **Done**.
- Features include:
  - Adding issues or PRs as cards
  - Custom workflows
  - Automation for moving cards across columns
  - Progress tracking for teams and individuals
- Projects can be linked to repositories or organizations for broader visibility.
