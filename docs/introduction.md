# Introduction: Why Git and GitHub Matter for Technical Writers

This is the introduction to Git and GitHub for Technical Writers, a six-part Docs-as-Code series. If you are new here, start at the [Home page](index.md).

---

If you do not understand the system that documentation moves through in a software development environment, you cannot contribute to it effectively. You cannot review a Pull Request, interpret a pipeline error, or understand why your changes are not live yet.

Most technical writers learn their craft in tools built around documents. Microsoft Word, Google Docs, Confluence, Notion. These tools are designed around a simple model: one file, one author, one version at a time.

That model breaks down the moment you enter a software team.

In a software team, documentation does not live in a shared Google Doc. It lives in a repository, the same place the code lives. It is edited in plain text. It is reviewed through a structured approval process. It is deployed automatically to a live website.

This series exists to close that gap.

---

## What Git and GitHub are

**Git** is a version control system. It records every change made to a set of files, who made it, when, and why. It allows multiple people to work on the same document simultaneously without overwriting each other. It allows you to return to any previous state of a file at any point. It is the foundation of almost every professional documentation workflow in software.

**GitHub** is the cloud platform where Git repositories are stored and where collaboration happens. It adds a visual interface, a review process, and automation tools on top of Git. It is where technical writers and developers work together on the same documentation.

Git is the engine. GitHub is the workspace.

---

## What this series does not assume

You do not need to know how to code.

You do not need prior experience with the command line.

You do not need to have used Git or GitHub before.

Each part introduces concepts in plain language before showing how they work in practice. Technical terms are explained when they first appear and collected in a glossary at the end of each part.

---

## Key terms introduced in this series

These terms appear throughout the series. This is not a deep explanation of each — that happens in the parts themselves. This is enough to orient you before you begin.

| Term | What it means at this stage |
|------|-----------------------------|
| **Repository** | A folder that Git tracks. Contains your files and their full change history. |
| **Commit** | A saved snapshot of your changes, with a message describing what changed. |
| **Branch** | A separate working copy of the repository. Changes here do not affect the main version. |
| **Pull Request** | A proposal to merge your changes into the main version, subject to review. |
| **Merge** | Combining an approved branch into the main version. |
| **Pipeline** | An automated process that builds and publishes documentation after changes are merged. |

You will encounter each of these in detail across Parts 1 through 6.

---

## What to read next

This introduction frames the why. The series begins the how in Part 1.

Move to [Part 1: Git Basics for Technical Writers](part-1-git-basics.md) to begin.

---

*Written by Douglas Ebhoman, a technical writer based in Prague who builds documentation systems for DevTools and SaaS companies.*
*[douglasebhoman.com](https://douglasebhoman.com) · [LinkedIn](https://linkedin.com/in/douglas-ebhoman-757329289)*