# Part 1: Git Basics for Technical Writers

This page is part of the Git and GitHub for Technical Writers series. If you have not read the introduction yet, start at [Introduction](introduction.md).

---

## A real scenario

Imagine you are updating a product guide while a developer is fixing bugs in the same repository.

Without Git, one of you could overwrite the other's work. There is no history of what changed, no way to recover an earlier version, and no structured process for reviewing updates before they go live.

With Git, both of you work in parallel on separate branches. Every change is recorded with a clear message. Nothing is published until it has been reviewed and approved. Your update and the developer's bug fixes happen simultaneously and neither blocks the other.

This is the problem Git solves.

---

## What is Git?

Git is a distributed version control system, a tool that records changes to files over time and allows multiple people to work on the same project without overwriting each other's work.

With Git, you can:

- See exactly what changed in a document, line by line
- Understand who made each change and when
- Restore any earlier version of a file at any point
- Experiment safely without affecting the published version
- Collaborate with developers using the same workflow they already use

Unlike cloud tools such as Google Docs, Git works locally on your computer. You control when changes are saved and when they are shared with the rest of the team.

---

## Why Git matters for technical writers

Git is not a developer-only tool. For technical writers, it enables:

- **Version history**: every edit is recorded and recoverable
- **Safe collaboration**: multiple contributors without file conflicts
- **Structured reviews**: changes are proposed and approved before publication
- **Docs-as-Code workflows**: documentation treated with the same rigour as software

Using Git turns documentation from a collection of files scattered across folders and drives into a managed, auditable system.

---

## Core concepts

### Repository

A repository, commonly called a repo, is a project folder tracked by Git. It contains your documentation files and a hidden `.git` directory that stores the complete change history.

Think of a repository as the permanent home of your documentation project. Everything related to that project, including files, history, branches, and contributors, lives inside it.

---

### Commit

A commit is a saved snapshot of your project at a specific point in time.

Each commit has a unique identifier, the name of the person who made the change, a timestamp, and a message describing what changed and why.

For technical writers, commits function as documented editing milestones. You can return to any commit and see exactly what the documentation looked like at that moment.

A good commit message answers one question: what does this change do?

```bash
# Too vague
git commit -m "Update"

# Clear and useful
git commit -m "Clarify authentication steps in API quickstart guide"
```

---

### Branch

A branch is an independent line of work within a repository. When you create a branch, you get a separate copy of the documentation to work on. Changes on your branch do not affect the main version until they are reviewed and approved.

Common branch names you will encounter:

| Branch | Purpose |
|--------|---------|
| `main` | The stable, published version of the documentation |
| `feature/update-api-guide` | Work in progress on a specific section |
| `fix/broken-links` | A targeted correction |

Branches allow you to work on multiple updates simultaneously without interference.

> **Note:** Some older repositories use `master` instead of `main` as the default branch name. Both serve the same purpose. If you encounter a repository using `master`, treat it the same way you would treat `main`.

---

### The three stages of Git

This is the concept most beginners find confusing. Git tracks changes across three distinct stages:

```
Working Directory → Staging Area → Repository
```

| Stage | What it is | What happens here |
|-------|-----------|-------------------|
| **Working Directory** | Your local files | You edit documentation here |
| **Staging Area** | A preparation zone | You select which changes to include in the next commit |
| **Repository** | The permanent record | Committed snapshots are stored here |

The staging area gives you deliberate control over what gets saved. You can edit ten files but commit only three. Staging lets you make that selection before anything is permanently recorded.

---

## Essential commands

> **Note:** These commands are run in your terminal. On Windows, open Command Prompt or PowerShell. On macOS and Linux, open the Terminal application.

**Initialise a repository**

```bash
git init
```

Creates a new Git repository in the current folder. Run this once when starting a new documentation project.

> **Note:** Make sure you are inside your project folder before running this command. It creates a hidden `.git` directory in whichever folder your terminal is currently in. Run `pwd` (macOS/Linux) or `cd` (Windows) to confirm your location first.

---

**Check status**

```bash
git status
```

Shows which files have been modified, which are staged, and which are untracked. This is the safest command to run at any point. It tells you exactly where you are without changing anything. Run it frequently, especially before committing.

---

**Stage files**

```bash
# Stage a specific file
git add filename.md

# Stage all changed files
git add .
```

Moves changes from your working directory into the staging area. Review what you are staging before using `git add .` to avoid committing unintended changes.

---

**Commit changes**

```bash
git commit -m "Add Git basics documentation for technical writers"
```

Creates a permanent snapshot of everything in the staging area. Make the message specific and descriptive.

---

**View history**

```bash
git log
```

Displays the full commit history of the project, including author, timestamp, and message for every commit.

---

**Push to a remote repository**

```bash
git push origin main
```

Uploads your committed changes to the remote repository on GitHub, making them visible to your team.

> **Note:** Before your first push, your local repository must be linked to a remote on GitHub. If you have not done this yet, run the following command first, replacing the URL with your own repository address:
> ```bash
> git remote add origin https://github.com/yourusername/your-repo-name.git
> ```
> The full setup process is covered in [Deploying to GitHub Pages](https://douglasebhoman.com/mkdocs-for-technical-writers/deploying-to-github-pages/) in the MkDocs for Technical Writers guide.

---

## Git vs GitHub

These two tools are frequently confused. They are not the same thing.

| | Git | GitHub |
|--|-----|--------|
| **What it is** | Version control system | Cloud hosting platform |
| **Where it runs** | Locally on your machine | In the cloud |
| **Primary function** | Tracks and records changes | Stores repos and enables collaboration |
| **Internet required** | No, works offline | Yes |
| **Who made it** | Linus Torvalds, 2005 | GitHub Inc., 2008 |

You use Git to manage changes to your documentation. You use GitHub to store those changes online and collaborate with others.

Git can exist without GitHub. GitHub cannot exist without Git.

---

## What to ignore for now

As a technical writer getting started with Git, you do not need to understand the following yet:

- **Rebasing**: reorganising commit history
- **Stashing**: temporarily shelving uncommitted changes
- **Cherry-picking**: applying individual commits across branches
- **Merge conflicts**: resolving competing changes between branches

Focus on repositories, commits, branches, and the basic workflow. Everything else builds on that foundation and will be introduced when it is relevant.

---

## Common mistakes and how to avoid them

| Mistake | Why it matters | How to avoid it |
|---------|---------------|-----------------|
| Vague commit messages | Future you and your team cannot understand what changed | Always describe what the change does, not just that it changed |
| Committing everything blindly | Unintended changes end up in the permanent record | Run `git status` before every commit |
| Working directly on `main` | Errors go live immediately without review | Always create a branch for new work |
| Large infrequent commits | Hard to review and hard to reverse | Commit small, logical units of work |

---

## Summary

Three things to take from this page:

- A **commit** is your documentation audit trail. Every change is recorded with who made it, when, and why.
- The **three stages** (Working Directory, Staging Area, Repository) give you deliberate control over what gets saved and when.
- **Git** manages changes locally. **GitHub** stores and shares them in the cloud. They are not the same tool.

---

Move to [Part 2: Git vs GitHub](part-2-git-vs-github.md) to continue.

---

*Written by Douglas Ebhoman, a technical writer based in Prague who builds documentation systems for DevTools and SaaS companies.*
*[douglasebhoman.com](https://douglasebhoman.com) · [LinkedIn](https://linkedin.com/in/douglas-ebhoman-757329289)*