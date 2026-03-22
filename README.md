# Git & GitHub for Technical Writers

A structured documentation series explaining Git and GitHub workflows for technical writers — written in plain language, without assuming a software development background.

This repository is the primary source for all articles in the series. Each article is maintained here as a Markdown file and mirrored on [Hashnode](https://git-and-github-for-technical-writers.hashnode.dev) for public readership.

📖 **Read the live documentation site →** https://douglasebhoman.github.io/git-github-for-technical-writers-series

---

## Who This Series Is For

This series is written for:

- Technical writers entering Docs-as-Code environments for the first time
- Writers transitioning from traditional publishing or content tools into Git-based workflows
- Anyone who has been told to "just use GitHub" without being shown how it works

No prior experience with Git, GitHub, or the command line is assumed.

---

## Series Overview

| Part | Title | Status |
|------|-------|--------|
| 0 | [Introduction](docs/introduction.md) | ✅ Published |
| 1 | [Git Basics for Technical Writers](docs/part-1-git-basics.md) | ✅ Published |
| 2 | [Git vs GitHub — Understanding the Documentation Workflow](docs/part-2-git-vs-github.md) | ✅ Published |
| 3 | [From Editing Files to Managing Versions](docs/part-3-versioning.md) | ✅ Published |
| 4 | [Pull Requests — Controlling Documentation State](docs/part-4-pull-requests.md) | ✅ Published |
| 5 | [CI/CD for Technical Writers — How Documentation Moves from Repository to Production](docs/part-5-cicd-pipelines.md) | ✅ Published |
| 6 | [Documentation Repository Architecture — Structuring Docs That Scale](docs/part-6-repo-architecture.md) | ✅ Published |

---

## Repository Structure
```
git-github-for-technical-writers-series/
├── README.md                        ← Series index (you are here)
├── CONTRIBUTING.md                  ← How to suggest corrections or improvements
├── mkdocs.yml                       ← MkDocs configuration for the live site
├── docs/
│   ├── images/
│   │   ├── cicd-pipeline-diagram.png      ← Part 5 — CI/CD Pipeline
│   │   └── diataxis-framework-diagram.svg ← Part 6 — Documentation Architecture
│   ├── introduction.md
│   ├── part-1-git-basics.md
│   ├── part-2-git-vs-github.md
│   ├── part-3-versioning.md
│   ├── part-4-pull-requests.md
│   ├── part-5-cicd-pipelines.md
│   └── part-6-repo-architecture.md
└── .github/
    └── workflows/
        └── deploy.yml               ← GitHub Actions workflow for automated deployment
```

---

## Publishing Workflow

This repository follows a Docs-as-Code publishing workflow:

1. Each article is drafted and revised in the `docs/` folder
2. Changes are committed to the `main` branch with descriptive commit messages
3. GitHub Actions automatically builds and deploys the site to GitHub Pages on every push
4. Once an article is ready for public readership, it is mirrored to [Hashnode](https://git-and-github-for-technical-writers.hashnode.dev)
5. Any post-publication corrections are made here first, then updated on Hashnode

This means the GitHub repository always reflects the most current, authoritative version of each article.

---

## Reading Order

If you are new to this series, start with the Introduction and read sequentially. Each article builds directly on the concepts introduced in the previous one.

The series follows a single thread:

> **Writing → Versioning → Validating → Building → Deploying → Scaling**

By the end of Part 6, you will understand the complete lifecycle of documentation in a professional Docs-as-Code environment.

---

## Live Reading

Prefer a polished reading experience? The full series is available as a live static site built with MkDocs and deployed via GitHub Pages:

📖 [douglasebhoman.github.io/git-github-for-technical-writers-series](https://douglasebhoman.github.io/git-github-for-technical-writers-series)

Also available on Hashnode:

✍️ [git-and-github-for-technical-writers.hashnode.dev](https://git-and-github-for-technical-writers.hashnode.dev)

---

## About the Author

**Douglas Ebhoman** — Technical Writer & Documentation Specialist

- 🔗 [LinkedIn](https://linkedin.com/in/douglas-ebhoman-757329289)
- ✍️ [Hashnode](https://git-and-github-for-technical-writers.hashnode.dev)
- 💼 [Portfolio](https://github.com/Douglasebhoman)

---

## Corrections & Feedback

Found an error? Have a suggestion? See [CONTRIBUTING.md](CONTRIBUTING.md) for how to raise it.
