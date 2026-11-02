# Contributing Guide

Welcome to the project!

We are happy to have students, developers, and contributors participate in this project. This guide explains how to contribute using Git and GitHub in a clean, professional, and beginner-friendly way.

Our goal is to keep the codebase organized, maintain a meaningful Git history, and make collaboration easy for everyone.

---

## Table of Contents

1. [How to Fork and Clone the Repository](#how-to-fork-and-clone-the-repository)
2. [Create a Branch](#create-a-branch)
3. [Branch Naming Conventions](#branch-naming-conventions)
4. [Make and Review Your Changes](#make-and-review-your-changes)
5. [Commit Message Format](#commit-message-format)
6. [Push Your Changes](#push-your-changes)
7. [How to Open a Pull Request](#how-to-open-a-pull-request)
8. [Code Review Expectations](#code-review-expectations)
9. [Before Opening a Pull Request](#before-opening-a-pull-request)
10. [Contribution Workflow](#contribution-workflow)
11. [Useful Git Commands](#useful-git-commands)
12. [Contribution Principles](#contribution-principles)

---

# How to Fork and Clone the Repository

If you are contributing for the first time, start by creating your own copy of the repository.

## 1. Fork the Repository

A **fork** is your own copy of the project's repository on GitHub.

### Steps

1. Open the project repository on GitHub.
2. Click the **Fork** button.
3. Select your GitHub account.
4. GitHub will create a copy of the repository under your account.

You can now make changes to your fork without directly modifying the original repository.

---

## 2. Clone Your Fork

After forking the repository, copy the URL of your fork.

```bash
git clone https://github.com/YOUR-USERNAME/REPOSITORY-NAME.git
```

Example:

```bash
git clone https://github.com/your-username/project-name.git
```

Then move into the project directory:

```bash
cd project-name
```

### Why do we use `git clone`?

`git clone` downloads the repository from GitHub to your computer so you can work on it locally.

---

## 3. Check the Repository

```bash
git status
```

Check the remote repository:

```bash
git remote -v
```

You should see the URL of your fork.

---

# Create a Branch

Do not make changes directly on the `main` branch.

Create a separate branch for your work:

```bash
git switch -c docs/contributing-guide
```

Check your current branch:

```bash
git branch
```

The branch marked with `*` is your current branch.

Example:

```text
* docs/contributing-guide
  main
```

### Why use a separate branch?

Branches allow contributors to work independently without affecting the stable `main` branch.

```text
main
  |
  |------ feature/login
  |
  |------ fix/navbar
  |
  |------ docs/contributing-guide
```

---

# Branch Naming Conventions

Use clear and descriptive branch names.

| Prefix | Purpose | Example |
|---|---|---|
| `feature/` | Add a new feature | `feature/student-dashboard` |
| `fix/` | Fix a bug | `fix/login-error` |
| `docs/` | Documentation changes | `docs/contributing-guide` |
| `refactor/` | Improve code structure without changing behavior | `refactor/auth-service` |
| `test/` | Add or update tests | `test/login-api` |
| `chore/` | Maintenance or configuration work | `chore/update-dependencies` |
| `style/` | Code formatting changes | `style/format-auth-module` |

## Good Examples

```text
feature/student-dashboard
feature/user-profile
fix/login-error
fix/database-timeout
docs/api-documentation
docs/contributing-guide
refactor/auth-service
test/user-registration
chore/update-dependencies
style/format-auth-module
```

## Avoid Unclear Branch Names

```text
mybranch
new
test123
changes
final
final-final
my-work
```

A good branch name should describe the purpose of the work.

---

# Make and Review Your Changes

After creating your branch, make your changes.

Check what has changed:

```bash
git status
```

Review your changes:

```bash
git diff
```

If you only want to stage specific parts of a file:

```bash
git add -p
```

This lets you review changes one section at a time and choose which changes should be included in the next commit.

## Do Not Commit Secrets

Never commit sensitive information such as:

```text
.env files containing secrets
API keys
Passwords
Access tokens
Cloud credentials
Private SSH keys
Database credentials
```

If you accidentally expose a secret, immediately inform the project maintainers and rotate or revoke the affected credential.

---

# Commit Message Format

We use **Conventional Commits** to keep the Git history clean, consistent, and easy to understand.

The basic format is:

```text
type: short description
```

Example:

```text
feat: add student dashboard
```

## Common Commit Types

| Type | Meaning | Example |
|---|---|---|
| `feat` | Add a new feature | `feat: add student dashboard` |
| `fix` | Fix a bug | `fix: resolve login error` |
| `docs` | Documentation changes | `docs: update contributing guide` |
| `refactor` | Restructure code without changing behavior | `refactor: extract validation logic` |
| `test` | Add or modify tests | `test: add login test cases` |
| `style` | Code formatting changes | `style: fix indentation in auth module` |
| `chore` | Maintenance or configuration work | `chore: update dependencies` |

## Good Commit Messages

```text
feat: add student profile page
fix: resolve database timeout in auth service
docs: add API documentation
refactor: extract validation logic
test: add authentication test cases
style: fix indentation in auth module
chore: update project dependencies
```

## Avoid Vague Commit Messages

```text
update
changes
fixed stuff
final changes
working
new code
done
```

A good commit message should clearly explain what changed.

## Commit Your Changes

Stage your changes:

```bash
git add .
```

Create a commit:

```bash
git commit -m "docs: add contributing guide"
```

For larger changes, prefer multiple small, meaningful commits rather than one very large commit.

---

# Push Your Changes

For the first push:

```bash
git push -u origin your-branch-name
```

Example:

```bash
git push -u origin docs/contributing-guide
```

After the branch has been connected to the remote branch:

```bash
git push
```

---

# How to Open a Pull Request

A **Pull Request (PR)** is a request to merge your changes from your branch into the project's target branch, usually `main`.

```text
Your Fork
    |
    | Your Branch
    v
GitHub
    |
    | Pull Request
    v
Original Repository
    |
    | Code Review
    v
Approval
    |
    v
Merge
```

## Steps to Open a Pull Request

1. Push your branch to GitHub.
2. Open your fork on GitHub.
3. Find the branch you just pushed.
4. Click **Compare & pull request**.
5. Make sure the correct base repository is selected.
6. Select the appropriate base branch, usually `main`.
7. Add a clear Pull Request title.
8. Describe what you changed.
9. Explain why the change was needed.
10. Mention related issues if applicable.
11. Submit the Pull Request.

## Pull Request Title

Use a clear title that follows the Conventional Commit style when appropriate.

Example:

```text
docs: add contributing guide
```

Other examples:

```text
feat: add student dashboard
fix: resolve mobile navigation issue
refactor: simplify authentication service
test: add user registration tests
```

## Pull Request Description

A good Pull Request description should explain:

- What was changed?
- Why was it changed?
- How was it tested?
- Are there any important notes for reviewers?

Example:

```markdown
## What changed?

Added a CONTRIBUTING.md file to explain how students can contribute to the project.

## Includes

- Fork and clone instructions
- Branch naming conventions
- Conventional Commit format
- Pull Request workflow
- Code review expectations

## Testing

Documentation-only change.
```

---

# Code Review Expectations

Every Pull Request may be reviewed before it is merged.

Code review is a collaborative process used to improve code quality, identify problems, and help contributors learn.

## Contributors Should

- Keep Pull Requests focused on one task.
- Write clear and meaningful commit messages.
- Test their changes before opening a Pull Request.
- Review their own changes before requesting review.
- Explain important design decisions when necessary.
- Respond to review comments professionally.
- Make requested changes when appropriate.
- Keep documentation updated when necessary.
- Avoid unrelated changes in the same Pull Request.
- Never commit passwords, API keys, tokens, or other secrets.

## Reviewers Should

- Be respectful and constructive.
- Focus on the code, not the person.
- Explain why a change is recommended.
- Identify bugs and potential problems.
- Suggest improvements where appropriate.
- Avoid unnecessary or unrelated changes.
- Approve the Pull Request when the required checks are satisfied.

> Code review is not about finding fault with someone. It is about improving the project together.

Everyone is encouraged to ask questions, learn, and help other contributors.

---

# Before Opening a Pull Request

Before creating a Pull Request, make sure you have:

- [ ] Created a separate branch.
- [ ] Followed the branch naming convention.
- [ ] Made only relevant changes.
- [ ] Tested your changes.
- [ ] Checked `git status`.
- [ ] Reviewed your changes using `git diff`.
- [ ] Used meaningful commit messages.
- [ ] Removed debugging code.
- [ ] Removed unnecessary files.
- [ ] Did not commit secrets or sensitive information.
- [ ] Updated documentation when necessary.
- [ ] Pushed the correct branch.
- [ ] Added a clear Pull Request title.
- [ ] Added a useful Pull Request description.

---

# Contribution Workflow

```text
Fork
  |
  v
Clone
  |
  v
Create Branch
  |
  v
Make Changes
  |
  v
Test
  |
  v
Review Changes
  |
  v
git add
  |
  v
git commit
  |
  v
git push
  |
  v
Open Pull Request
  |
  v
Code Review
  |
  v
Make Changes if Required
  |
  v
Approval
  |
  v
Merge into main
```

---

# Useful Git Commands

## Check Repository Status

```bash
git status
```

Shows which files have been modified, staged, or are untracked.

## Create a New Branch

```bash
git switch -c feature/my-feature
```

Creates and switches to a new branch.

## View Local Branches

```bash
git branch
```

Shows your local branches.

## Review Unstaged Changes

```bash
git diff
```

Shows changes that have not yet been staged.

## Stage All Changes

```bash
git add .
```

Stages all changed and untracked files in the current directory.

## Stage Specific Parts of Changes

```bash
git add -p
```

Allows you to select individual sections of changes for staging.

## Commit Changes

```bash
git commit -m "feat: add my feature"
```

Creates a new commit containing the staged changes.

## Push a Branch

```bash
git push -u origin feature/my-feature
```

Uploads your branch and commits to the remote repository.

## View Commit History

```bash
git log --oneline --decorate
```

Shows a compact view of the project's commit history.

## Update Information from the Remote Repository

```bash
git fetch origin
```

Downloads information about new commits and branches from the remote repository without changing your working files.

---

# Contribution Principles

We encourage every contributor to follow these principles:

### 1. Learn

Do not be afraid to ask questions or contribute as a beginner.

### 2. Build

Try to make practical contributions that improve the project.

### 3. Communicate

Explain your changes clearly and communicate respectfully with other contributors.

### 4. Review

Review your own work before asking others to review it.

### 5. Improve

Use feedback as an opportunity to improve your technical and collaborative skills.

---

# Thank You for Contributing!

Thank you for taking the time to contribute to this project.

Whether you are fixing a documentation issue, adding a new feature, improving existing code, writing tests, or learning Git for the first time, every contribution is valuable.

Let's build a clean, collaborative, and welcoming open-source environment together.

**Learn. Build. Research. Grow.**