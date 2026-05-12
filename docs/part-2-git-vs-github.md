# Part 2: Git vs GitHub

This page is part of the Git and GitHub for Technical Writers series. If you are joining mid-series, start at the [Home page](index.md).

---

You can write clean commits. You can create organised branches. You can maintain a complete local history.

But if your documentation never leaves your laptop, collaboration never begins.

This is where GitHub enters the picture. Understanding the difference between Git and GitHub is not about comparing tools. It is about understanding how documentation moves from private draft to shared production.

---

## Why local version control is not enough

Git gives you a complete, recoverable history of your documentation on your machine. That is powerful, but it is also private.

The moment you need a colleague to review a change, a developer to approve a technical claim, or a CI/CD pipeline to publish your work automatically, you need something beyond your local machine.

That something is GitHub.

---

## Git vs GitHub: the clear distinction

| Function | Git | GitHub |
|----------|-----|--------|
| Tracks file changes | Yes | |
| Records version history | Yes | |
| Works offline | Yes | |
| Stores repository online | | Yes |
| Enables team collaboration | | Yes |
| Manages Pull Requests | | Yes |
| Provides review tools | | Yes |

Git manages change history on your local machine. GitHub manages team workflow in the cloud.

Both are necessary in a professional documentation workflow. Git can exist without GitHub. GitHub cannot exist without Git.

> **Note:** Google Docs also tracks changes, so the distinction is worth making explicit. Git tracks changes atomically across an entire repository of files. Every change to every file is recorded in a named commit, with branching, offline capability, and a structured review process. Google Docs tracks edits to a single document in a linear history with no concept of a repository, branching, or structured approval. These are not the same kind of version control.

---

## The documentation workflow: from laptop to live

This is the practical sequence technical writers follow in Docs-as-Code environments. Each phase has a clear purpose and a defined boundary.

---

### Phase 1: Local drafting

You begin on your local machine.

```bash
git add filename.md
git commit -m "Add authentication section to API quickstart guide"
```

At this stage, your work is entirely private. No one else can see it. This is your structured drafting environment, version-controlled and recoverable at any point.

---

### Phase 2: Push to GitHub

When you are ready to share your work, push your branch to the remote repository:

```bash
git push origin branch-name
```

> **What `git push` does:** It uploads the commits from your local branch to the matching branch on GitHub, making your work visible to the rest of your team for the first time.

After pushing, your team can see your branch, your changes are backed up online, and collaboration becomes possible. Your documentation has moved from local draft to shared workspace.

---

### Phase 3: Pull Request and review

A Pull Request is a formal proposal to merge your branch into the `main` version of the documentation. This is where GitHub becomes essential to the workflow.

Inside a Pull Request, your team can view the Diff, leave comments on specific lines, suggest edits directly in the file, and approve the changes or request revisions.

> **What the Diff is:** When you open a Pull Request on GitHub, the Diff appears automatically under the Files changed tab. It shows a line-by-line comparison where additions appear in green and deletions in red.

The Diff is particularly powerful for documentation review. It isolates exactly what changed, which allows reviewers to focus on the delta rather than rereading the entire document.

For technical writers, this replaces the cycle of emailing documents back and forth. Discussion happens directly around the content, transparently, traceably, and permanently recorded in the repository history.

---

### Phase 4: Merge to main

Once a Pull Request is reviewed and approved, it is merged into the `main` branch.

At this point, your changes become part of the official documentation, the repository history updates permanently, and the team works from the new version going forward.

In many Docs-as-Code environments, merging to `main` automatically triggers a CI/CD pipeline that rebuilds and publishes the live documentation site. Merge often equals publish.

Documentation has now completed its full journey:

```
Draft → Reviewed → Approved → Production
```

---

## The end-to-end workflow

```
Edit → Commit → Push → Pull Request → Review → Merge
```

| Stage | Purpose |
|-------|---------|
| **Edit** | Create or update documentation content |
| **Commit** | Record intentional changes with a descriptive message |
| **Push** | Share your branch with the team on GitHub |
| **Pull Request** | Formally propose your changes for review |
| **Review** | Validate accuracy, clarity, and completeness |
| **Merge** | Publish approved content to the main version |

---

## Why this workflow matters

Before Git and GitHub, documentation commonly lived in shared drives, email threads, and Google Docs with unclear version history.

| Problem | How Git and GitHub solve it |
|---------|----------------------------|
| Conflicting versions | Every change is recorded on a named branch |
| Unclear approvals | Pull Requests require explicit review and approval |
| Lost edits | Every commit is permanent and recoverable |
| No source of truth | `main` is always the authoritative version |

The result is documentation that is controlled, traceable, and intentional at every stage.

---

## Essential commands for this workflow

**Pull the latest version**

```bash
git pull
```

Downloads the latest commits from the remote repository and merges them into your current local branch. Always run this before starting new work to ensure you are working from the most current version of the documentation.

---

**Create a new branch**

```bash
git checkout -b feature/update-api-guide
```

`git checkout` switches branches. The `-b` flag creates a new branch before switching to it. Use a descriptive name that identifies the work you are doing. Never commit directly to `main`.

---

**Push a branch to GitHub**

```bash
git push origin branch-name
```

Uploads your committed changes to GitHub. Replace `branch-name` with the name of your branch.

---

**Check what has changed**

```bash
git status
```

Run this before every `git add` and before every `git commit`. It tells you exactly what is modified, what is staged, and what is untracked, without changing anything.

---

## Common mistakes and how to avoid them

| Mistake | Consequence | How to avoid it |
|---------|-------------|-----------------|
| Not running `git pull` before starting work | You edit an outdated version and create conflicts | Run `git pull` at the start of every working session |
| Pushing directly to `main` | Unreviewed changes go live immediately | Always work on a named branch |
| Vague commit messages | Version history becomes meaningless | Describe what the change does, not just that it happened |
| Oversized Pull Requests | Hard to review, more likely to introduce errors | Keep each PR focused on one logical documentation unit |

---

## Summary

Three things to take from this page:

- **Git** manages version history locally. **GitHub** manages collaboration in the cloud. They are not the same tool and both are necessary.
- Documentation moves through four phases: Draft, Reviewed, Approved, Production. Pull Requests are where the review phase happens.
- Merging to `main` is the publication step. In many environments it triggers automatic deployment.

The commands from Part 1 — `git add`, `git commit`, and `git push` — are the tools that move your work through phases one and two. GitHub handles phases three and four. Together they form one complete workflow.

---

Move to [Part 3: Managing Versions](part-3-versioning.md) to continue.

---

*Written by Douglas Ebhoman, a technical writer based in Prague who builds documentation systems for DevTools and SaaS companies.*
*[douglasebhoman.com](https://douglasebhoman.com) · [LinkedIn](https://linkedin.com/in/douglas-ebhoman-757329289)*