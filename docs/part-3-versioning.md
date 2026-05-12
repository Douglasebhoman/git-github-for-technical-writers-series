# Part 3: From Editing Files to Managing Versions

This page is part of the Git and GitHub for Technical Writers series. If you are joining mid-series, start at the [Home page](index.md).

---

Most writers think in files. Git thinks in changesets.

That shift, from file editing to version management, is foundational to working effectively in a Docs-as-Code environment. This page explains what that shift looks like in practice and why it matters for documentation that needs to stay accurate as a product evolves.

---

## Editing is linear. Versioning is structured.

**Traditional editing workflow:**

```
File → Modify → Save → Overwrite
```

**Version-controlled workflow:**

```
Edit → Stage → Commit → Compare → Review → Merge
```

In the traditional workflow, saving a file replaces its previous state. There is no history, no recovery point, no record of intent.

In the version-controlled workflow, you are not replacing content. You are creating a structured timeline of intentional states. Each commit is a checkpoint, a snapshot of the entire documentation system at a specific moment in time.

Git stores these checkpoints in a connected sequence where every commit references the one before it. Each commit represents:

- A snapshot of the complete documentation at that moment
- A recorded decision with a descriptive message
- A historical reference point
- A recoverable state

Documentation becomes temporal, structured in time and not just in folders. This is what makes it possible to trace every change, understand why it was made, and reverse it if necessary.

---

## What is a documentation state?

When you run `git log`, each entry represents more than a saved file. It represents the entire documentation system as it existed at that specific moment.

A documentation state is the complete, versioned snapshot of your documentation at a specific commit. Not a single file. Not a paragraph. The entire documentation system as it existed at that moment in history.

> **Note:** Even if you edit only one file, the commit records the state of every tracked file in the repository at that moment. This is what makes it possible to reconstruct the complete documentation system as it existed at any point in its history.

**View the history of documentation states:**

```bash
git log
```

Each entry in `git log` represents a distinct documentation state, a moment when someone made a deliberate, recorded change.

**Compare your current working state with the last commit:**

```bash
git diff
```

This command shows exactly how the current state differs from the previous one, line by line, addition by addition, deletion by deletion.

> **Note:** `git diff` without arguments shows the difference between your working directory and the staging area. If you have already staged your changes with `git add`, run `git diff --staged` instead to see the difference between the staging area and the last commit.

Thinking in states changes how you approach editing. Instead of asking "Did I update the file?" you begin asking "What new state am I creating?" That question aligns documentation work with how software releases are versioned and managed.

Branches take this further. Each branch is an independent line of states that exists in parallel with `main` until it is reviewed and merged. That is how multiple writers can work on different documentation updates simultaneously without interference. Part 1 introduced branches as a concept. Part 4 covers how they connect to the review process through Pull Requests.

---

## Atomic change: a workflow discipline

Atomic change means a single commit represents one logical unit of work.

Not one file. Not one page. One intention.

**Non-atomic commit (avoid this):**

```bash
git commit -m "update docs for release"
```

Inside that single commit might be a deprecated API parameter removed, formatting corrected throughout, a new onboarding section added, and a broken link fixed.

From a reviewer's perspective, this creates real problems. Which change relates to the feature? Which one introduced risk? Which change can be safely reverted without affecting the others?

**Atomic commits (use this pattern instead):**

```bash
git commit -m "docs: remove deprecated 'authToken' parameter from v2 API"
git commit -m "fix: resolve broken link in troubleshooting guide"
git commit -m "docs: add onboarding prerequisites section"
```

Each commit isolates a single decision. Each one can be reviewed, understood, and reversed independently.

---

### Conventional Commits

The examples above follow the Conventional Commits specification, a standard that uses consistent prefixes to make commit history both human-readable and machine-readable.

Common prefixes used in documentation:

| Prefix | When to use it |
|--------|---------------|
| `docs:` | Adding or updating documentation content |
| `fix:` | Correcting errors, broken links, or inaccurate information |
| `feat:` | Documenting a new feature |
| `chore:` | Maintenance tasks including formatting and file reorganisation |
| `refactor:` | Restructuring content without changing meaning |

Adopting this convention makes your commit history searchable, filterable, and immediately interpretable by any developer on your team.

---

### Why atomic commits matter operationally

Atomic commits produce:

- A cleaner `git log` that is meaningful at a glance
- Faster Pull Request review, reviewers evaluate one change at a time
- Precise rollback, a single commit can be reversed without affecting unrelated changes
- Fewer merge conflicts, as smaller focused changes are less likely to overlap
- A clear audit trail for documentation decisions

They transform documentation from a collection of edits into a sequence of controlled, attributable state transitions.

---

## Reversibility is structural

Version control makes changes reversible, not because it feels safe, but because of how it is built.

Git does not overwrite history. Every commit references the one before it. Every state is preserved.

**To reverse a specific documentation state:**

```bash
git revert <commit-hash>
```

> **Note:** To find the commit hash you want to revert, run `git log` and copy the hash from the relevant commit entry. Git will then open your default text editor asking you to confirm the revert commit message. Save and close the editor to complete the revert. If your terminal opens Vim and you are not sure how to exit, type `:wq` and press Enter to save and close.

`git revert` does not delete the original commit. It creates a new commit that applies the inverse of the specified change. The previous state remains in the history, intact and recoverable.

This guarantees:

- Mistakes are traceable, you can find exactly when and why a change was made
- Bad changes are reversible without destroying surrounding history
- History remains intact and no information is silently lost
- Rollbacks are targeted, meaning you reverse one decision, not everything since

Over time, this structural safety changes how writers approach documentation. Reversibility enables confident refactoring because every state is preserved and every decision is recoverable.

---

## A practical discipline to start today

To build version thinking into your daily workflow:

1. Make smaller commits, one logical change per commit
2. Separate unrelated changes and do not bundle formatting fixes with content updates
3. Write precise commit messages using Conventional Commits prefixes
4. Run `git diff` before committing to review exactly what you are about to record
5. Ask before every commit: what new documentation state am I creating?

If the answer to that question is unclear, the commit contains too many changes. Split it.

---

## Why this matters in fast-moving teams

In teams shipping weekly or daily, documentation drift is a real operational risk.

| Without version discipline | With version discipline |
|---------------------------|------------------------|
| Docs fall behind code changes | Every change is logged against a specific moment |
| Context disappears over time | Every state is recoverable |
| Reviews slow down | Atomic commits make reviews faster and more focused |
| History becomes noisy and unusable | Commit history becomes a meaningful audit trail |
| Unclear what version of docs matches what version of product | Every documentation state is traceable to a point in time |

Version discipline is what keeps documentation aligned with a fast-moving product, not through effort alone, but through structure.

---

## Summary

Three things to take from this page:

- Git thinks in changesets, not files. Every commit records what changed, why, when, and by whom. This is the foundational shift from file editing to version management.
- Atomic commits, one logical unit of work per commit, reduce review friction, enable precise rollback, and produce a meaningful audit trail. Conventional Commits prefixes make that history readable.
- `git revert` creates a new commit that reverses a previous one. It preserves history rather than deleting it, which means every decision is recoverable.

---

Move to [Part 4: Pull Requests](part-4-pull-requests.md) to continue.

---

*Written by Douglas Ebhoman, a technical writer based in Prague who builds documentation systems for DevTools and SaaS companies.*
*[douglasebhoman.com](https://douglasebhoman.com) · [LinkedIn](https://linkedin.com/in/douglas-ebhoman-757329289)*