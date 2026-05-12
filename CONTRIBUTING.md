# Contributing to Git and GitHub for Technical Writers

This series is a living document. If something is wrong, unclear, or missing, that is worth fixing. This guide explains how.

---

## What contributions are welcome

This is a documentation series written for non-developer audiences. It is not a software project. Contributions that improve accuracy, clarity, and accessibility are welcome.

**In scope:**

- Factual corrections: if something is technically inaccurate, raise it
- Clarity improvements: if an explanation is confusing or could be clearer
- Broken links: if a link in any article no longer works
- Typos and grammatical errors: small fixes are always appreciated
- Missing context: if a concept is introduced without enough background for the target audience

**Not in scope:**

- Requests to add advanced DevOps or engineering content. This series is written for non-developer audiences and intentionally keeps scope limited.
- Restructuring articles. The series follows a deliberate narrative arc that is not open for reorganisation.

---

## How to raise an issue

1. Go to the Issues tab at the top of this repository
2. Click New Issue
3. Use the following format in your issue title:

   `[Part X] Brief description of the issue`

   Example: `[Part 3] Explanation of branching is unclear for non-developers`

4. In the issue body, include:
   - The specific paragraph or section where the issue occurs
   - What is currently written
   - What you believe should be written or clarified
   - Any sources that support your correction, if applicable

---

## How to suggest a change via Pull Request

If you are comfortable with GitHub, you are welcome to suggest a direct edit.

> **Prefer not to use the terminal?** You can make small edits directly in your browser using the GitHub web editor. Navigate to the file you want to change, click the pencil icon at the top right, make your edit, and follow the Pull Request steps from there. No terminal required.

1. Fork this repository
2. Create a new branch named: `fix/part-X-brief-description`

   Example: `fix/part-3-branching-clarification`

3. Make your changes in the relevant `docs/` file
4. Commit with a clear message following the Conventional Commits format taught in Part 3

   Example: `fix: clarify branching explanation for non-developer readers`

5. Open a Pull Request against the `main` branch
6. In the PR description, explain what you changed and why

All Pull Requests will be reviewed before merging. Not all suggestions will be accepted, but all will be read and considered.

---

## Style guidelines

If you are suggesting new or revised text, follow these conventions:

- Write in plain English. Avoid jargon where possible.
- Address the reader directly using second person: you, your, you will.
- Use active voice.
- Keep sentences short. One idea per sentence where possible.
- Use British English spelling: organise, behaviour, colour.
- No em dashes. Use a comma, a full stop, or a colon instead.

---

## Questions

If you are unsure whether your suggestion is in scope, open an issue and ask before submitting a Pull Request. This avoids unnecessary work on both sides.

You can also reach me directly at [douglas@douglasebhoman.com](mailto:douglas@douglasebhoman.com) or on [LinkedIn](https://linkedin.com/in/douglas-ebhoman-757329289).

---

*This contributing guide follows the same principles the series teaches: clear context, direct action, verifiable outcome.*