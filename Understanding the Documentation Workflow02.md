
## Series Context

> This is Part 2 of the **Git & GitHub for Technical Writers** series.

In Part 1, we covered Git fundamentals — how it tracks changes, records commits, and allows you to work safely on your local machine.

In this article, we move from local version control to collaborative workflow.

## Overview

You’ll learn how documentation moves from private draft to shared production using Git and GitHub together — and why both are essential in modern Docs-as-Code environments.

## The Problem: Version Control Without Collaboration

You can write clean commits.  
You can create organized branches.  
You can maintain a perfect local history.

Yet if your documentation never leaves your laptop, collaboration never begins.

This is where GitHub enters the picture.

Understanding the difference between Git and GitHub is not about comparing tools. It is about understanding how documentation moves from private draft to shared production.

* * *

## Git vs GitHub: The Clear Distinction

Let’s remove confusion immediately.

### Git

*   Installed on your computer
    
*   Tracks file changes
    
*   Records version history
    
*   Allows branching and merging
    
*   Works offline
    

Git manages change history.

### GitHub

*   Cloud-based platform
    
*   Hosts repositories online
    
*   Enables team collaboration
    
*   Provides review tools
    
*   Manages Pull Requests
    

GitHub manages team workflow.

### Here is the simplest way to think about it:

<table style="min-width: 75px;"><colgroup><col style="min-width: 25px;"><col style="min-width: 25px;"><col style="min-width: 25px;"></colgroup><tbody><tr><th colspan="1" rowspan="1"><p>Function</p></th><th colspan="1" rowspan="1"><p>Git</p></th><th colspan="1" rowspan="1"><p>GitHub</p></th></tr><tr><td colspan="1" rowspan="1"><p>Tracks changes</p></td><td colspan="1" rowspan="1"><p>✔</p></td><td colspan="1" rowspan="1"><p></p></td></tr><tr><td colspan="1" rowspan="1"><p>Works offline</p></td><td colspan="1" rowspan="1"><p>✔</p></td><td colspan="1" rowspan="1"><p></p></td></tr><tr><td colspan="1" rowspan="1"><p>Stores project online</p></td><td colspan="1" rowspan="1"><p></p></td><td colspan="1" rowspan="1"><p>✔</p></td></tr><tr><td colspan="1" rowspan="1"><p>Enables team review</p></td><td colspan="1" rowspan="1"><p></p></td><td colspan="1" rowspan="1"><p>✔</p></td></tr><tr><td colspan="1" rowspan="1"><p>Supports Pull Requests</p></td><td colspan="1" rowspan="1"><p></p></td><td colspan="1" rowspan="1"><p>✔</p></td></tr></tbody></table>

Git controls your local edits.  
GitHub controls collaborative publication.

Both are necessary in a modern documentation workflow.

* * *

## The Documentation Workflow: From Laptop to Live

Now let’s walk through how documentation actually moves between Git and GitHub.

This is the practical rhythm technical writers follow in Docs-as-Code environments.

### Step 1: Work Locally (Private Drafting Phase)

You begin on your local machine.

You:

*   Edit your Markdown files
    
*   Stage changes with `git add`
    
*   Record a commit with `git commit`
    

At this stage, your work is private. No one else sees it.

This is your drafting environment — structured and version-controlled.

* * *

### Step 2: Push to GitHub (Visibility Phase)

When you are ready to share your work, you run:

`git push`

This sends your commits to the remote repository on GitHub.

Now:

*   Your team can see your branch
    
*   Your changes are backed up online
    
*   Collaboration becomes possible
    

Your documentation has moved from local draft to shared workspace.

* * *

### Step 3: Open a Pull Request (Review Phase)

This is where GitHub becomes essential.

A Pull Request (PR) is a formal request to merge your changes into the main version of the documentation.

Inside a Pull Request, your team can:

*   See the Diff — a line-by-line comparison where additions appear in green and deletions in red
    
*   Leave comments on specific lines
    
*   Suggest edits
    
*   Approve or request revisions
    

The Diff is especially powerful. It isolates exactly what changed, which allows reviewers to focus on the delta — not reread the entire document.

For technical writers, this becomes a structured editorial review stage.

Instead of emailing documents back and forth, discussion happens directly around the content — transparently, traceably, and permanently recorded in the repository history.

* * *

### Step 4: Merge into Main (Publication Phase)

Once your Pull Request is reviewed and approved, it is merged into the `main` branch.

At this point:

*   Your changes become part of the official documentation
    
*   The repository history updates
    
*   The team works from the new version moving forward
    

In many Docs-as-Code environments, merging to `main` automatically triggers a CI/CD pipeline (for example, via GitHub Pages or Netlify) that rebuilds and publishes the live documentation site.

In other words, merge often equals publish.

Documentation has now moved from:

Draft → Reviewed → Approved → Production

* * *

## The End-to-End Workflow at a Glance

`Edit → Commit → Push → Pull Request → Review → Merge`

Each stage has a clear purpose:

*   **Edit**: Create or update content
    
*   **Commit**: Record intentional changes
    
*   **Push**: Share your work
    
*   **Pull Request**: Request review
    
*   **Review**: Validate accuracy and clarity
    
*   **Merge**: Publish approved content
    

Once this rhythm becomes habit, collaboration feels structured instead of chaotic.

* * *

## Why This Matters for Technical Writers

Before Git and GitHub workflows, documentation often lived in:

*   Shared drives
    
*   Email threads
    
*   Google Docs with unclear version history
    

This led to:

*   Conflicting versions
    
*   Unclear approvals
    
*   Lost edits
    
*   Confusion about what was “final”
    

With Git and GitHub:

*   Every change is recorded
    
*   Every update is reviewed
    
*   Every publication is intentional
    
*   Every version is traceable
    

The result is clarity — both technically and operationally.

And that clarity becomes increasingly important as documentation grows alongside complex software products.

* * *

## Common Beginner Mistakes (And How to Avoid Them)

### 1\. Forgetting to Pull Before You Start

Always begin your day with:

`git pull`

This ensures you are working from the latest version of the documentation.

### 2\. Pushing Directly to Main

Avoid committing directly to `main`. Instead:

`git checkout -b feature-branch-name`

This protects the stability of production documentation.

### 3\. Writing Vague Commit Messages

Avoid:

`git commit -m "updated docs"`

Instead, use:

`git commit -m "Clarified OAuth authentication flow for v2 API"`

Clear commit messages make your version history meaningful and searchable.

### 4\. Creating Overly Large Pull Requests

Small, focused Pull Requests are easier to review and less likely to introduce confusion.

Treat each PR as a logical documentation unit.

* * *

## A Simple Daily Workflow for Technical Writers

Before writing:

`git pull`

During writing:

*   Commit logical sections as you complete them
    

When finished:

*   Push your branch
    
*   Open a Pull Request
    
*   Request review
    

This structure keeps documentation organized and collaborative.

* * *

## Where This Leads Next

Now that you understand how documentation moves between your laptop and your team, the next shift is deeper.

Git does more than track changes.

It changes how technical writers think about managing documentation itself.

In the next article, we’ll explore how version control transforms documentation from editable files into structured, manageable systems.

Because once you understand the workflow, you are ready to think beyond files — and start thinking in versions.
