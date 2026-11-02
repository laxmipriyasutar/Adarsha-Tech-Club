# ATC Team Guide

> **Adarsha Tech Club (ATC)**  
> A practical guide for how our student development team works, collaborates, reviews code, and maintains project quality.

---

## 1. Team Members

The ATC team works as a collaborative engineering team. Every member is expected to contribute to development, learning, documentation, and project quality.

| Team Member | Role | Main Responsibilities |
|---|---|---|
| **[Member Name]** | Team Lead | Coordinates the team, assigns tasks, tracks progress, and helps resolve blockers. |
| **[Member Name]** | Technical Lead | Guides technical decisions, architecture, coding standards, and implementation quality. |
| **[Member Name]** | Developer | Implements assigned features, fixes bugs, writes tests, and maintains documentation. |
| **[Member Name]** | Developer | Implements assigned features, fixes bugs, writes tests, and maintains documentation. |
| **[Member Name]** | QA / Tester | Tests features, identifies bugs, verifies fixes, and checks project requirements. |

### Adding a New Member

When a new student joins the team:

1. Add their name and role to this document.
2. Explain the project structure and Git workflow.
3. Assign a small starter task.
4. Pair them with an experienced member when possible.
5. Encourage questions before making major changes.

> **Note:** Replace the placeholder names above with the actual ATC team members.

---

# 2. Our Rotation System

ATC follows a **Driver / Reviewer / QA** rotation system.

The purpose of rotation is to make sure students do not work in isolation and everyone learns different parts of the software-development process.

## 2.1 Driver

The **Driver** is the person actively implementing the task.

### Responsibilities

- Understand the assigned issue or task.
- Create or switch to the correct feature branch.
- Write clean and understandable code.
- Test the implementation locally.
- Commit changes with meaningful commit messages.
- Create a Pull Request (PR).
- Explain the implementation to the Reviewer.

### Driver mindset

The Driver should think:

> "I am responsible for making this change work correctly and explaining what I changed."

---

## 2.2 Reviewer

The **Reviewer** checks the Driver's work before it is merged.

### Responsibilities

- Understand the purpose of the change.
- Review the code carefully.
- Check readability and maintainability.
- Look for bugs, edge cases, and unnecessary complexity.
- Check whether the implementation follows project conventions.
- Confirm that the PR description is understandable.
- Request changes when necessary.
- Approve the PR when it meets the team's standards.

### Reviewer mindset

The Reviewer should think:

> "I am not checking whether my teammate wrote the code exactly like I would. I am checking whether the solution is correct, maintainable, and safe to merge."

---

## 2.3 QA

The **QA** member verifies that the feature actually works as expected.

### Responsibilities

- Test the feature from a user's perspective.
- Check expected and unexpected inputs.
- Reproduce reported bugs.
- Verify bug fixes.
- Check for regressions in related functionality.
- Report problems clearly.
- Confirm that acceptance criteria are satisfied.

### QA mindset

The QA member should think:

> "If this feature reaches a real user, what could go wrong?"

---

## 2.4 Rotation

Roles should rotate between team members.

Example:

| Sprint / Task | Driver | Reviewer | QA |
|---|---|---|---|
| Task 1 | Student A | Student B | Student C |
| Task 2 | Student B | Student C | Student A |
| Task 3 | Student C | Student A | Student B |

This rotation helps students develop:

- Coding skills
- Code-review skills
- Testing skills
- Communication skills
- Git/GitHub skills
- Leadership and responsibility

> **Important:** The goal of rotation is not only productivity. It is also **learning through practice**.

---

# 3. Git Workflow We Follow

ATC uses Git and GitHub to manage project changes.

## 3.1 Main Branch

The `main` branch represents the stable version of the project.

Students should **not directly push changes to `main`** unless the team has explicitly agreed to do so for a specific reason.

---

## 3.2 Create a Feature Branch

Before starting work, update your local repository:

```bash
git switch main
git pull origin main
```

Create a branch for your task:

```bash
git switch -c feature/short-description
```

Examples:

```bash
git switch -c feature/login-page
git switch -c feature/student-dashboard
git switch -c fix/navbar-mobile
```

Use a branch name that clearly describes the work.

---

## 3.3 Make Changes

Work only on the assigned task.

Check your changes regularly:

```bash
git status
```

Review your changes:

```bash
git diff
```

---

## 3.4 Commit Your Work

Create small, meaningful commits.

```bash
git add .
git commit -m "feat: add student dashboard"
```

Good commit messages describe **what changed**.

### Recommended format

```text
type: short description
```

Common types:

| Type | Meaning |
|---|---|
| `feat` | New feature |
| `fix` | Bug fix |
| `docs` | Documentation |
| `refactor` | Code restructuring without changing behavior |
| `test` | Tests |
| `style` | Formatting or styling |
| `chore` | Maintenance tasks |

### Examples

```text
feat: add student registration form
fix: resolve mobile navbar issue
docs: update team guide
test: add login validation tests
refactor: simplify authentication service
```

Avoid commits such as:

```text
update
changes
final
final2
new code
asdf
```

---

## 3.5 Push the Branch

Push your branch to GitHub:

```bash
git push -u origin feature/login-page
```

---

## 3.6 Open a Pull Request

Create a Pull Request from your feature branch into `main`.

A good PR should explain:

### What changed?

Briefly describe the implementation.

### Why was it changed?

Explain the problem or requirement.

### How was it tested?

Mention the tests or manual verification performed.

### Example

```text
## What changed?
Added a student login page with form validation.

## Why?
Students need a secure login flow for the dashboard.

## Testing
- Tested valid login
- Tested invalid password
- Tested empty fields
- Tested mobile layout
```

---

## 3.7 Review → QA → Merge

The normal ATC flow is:

```text
Task
  ↓
Feature Branch
  ↓
Implementation
  ↓
Commit
  ↓
Push
  ↓
Pull Request
  ↓
Code Review
  ↓
QA Testing
  ↓
Fix Issues (if required)
  ↓
Approval
  ↓
Merge into main
```

Do not merge simply because the code "works on my machine."

---

# 4. Code Review Expectations

Code review is a learning process, not a competition.

The goal is to improve the project **and help the developer improve**.

## Reviewers should check

### Correctness

- Does the code solve the actual problem?
- Does it work for normal cases?
- Does it handle reasonable edge cases?

### Readability

- Are variable and function names understandable?
- Is the code easy for another student to understand?
- Are functions reasonably small and focused?

### Maintainability

- Can another developer modify this code later?
- Is unnecessary duplication present?
- Does the implementation follow existing project patterns?

### Security

Check for obvious problems such as:

- Hard-coded passwords or API keys
- Exposed secrets
- Unsafe user input handling
- Accidentally committed credentials
- Unnecessary sensitive information

**Never commit secrets to GitHub.**

---

## How to Give Review Feedback

Good review:

> "Could we move this validation into a separate function? It would make the login handler easier to read and test."

Poor review:

> "This code is bad."

Good feedback is:

- Specific
- Respectful
- Explainable
- Focused on the code
- Helpful for learning

---

## How to Receive Feedback

Developers should not treat review comments as personal criticism.

A review comment means:

> "Let's improve this part of the project."

If you disagree with a comment, discuss the technical reasoning respectfully.

The objective is to find the best solution, not to prove who is right.

---

# 5. Communication Guidelines

Good communication is an important part of engineering.

## 5.1 Ask Questions Early

Do not spend hours stuck silently.

If you are blocked, communicate:

```text
I am working on the login feature.

I have completed the UI, but I am blocked because
the authentication API is returning a 401 response.

I checked:
- API URL
- request payload
- authentication header

Can someone help me verify the API configuration?
```

This is much better than:

> "It doesn't work."

---

## 5.2 Give Context

When asking for help, include:

1. What you are trying to do.
2. What you expected.
3. What actually happened.
4. What you already tried.
5. The relevant error message.

This makes it easier for teammates to help quickly.

---

## 5.3 Keep Communication Professional

Use clear and respectful language.

### Do

- Ask questions.
- Share useful information.
- Give constructive feedback.
- Acknowledge helpful contributions.
- Inform the team when you are blocked.

### Avoid

- Personal attacks.
- Blaming teammates.
- Spamming messages.
- Ignoring review comments.
- Disappearing when assigned a task.
- Making major changes without informing the team.

---

## 5.4 Task Updates

For ongoing work, use a simple update format:

```text
Yesterday:
- Completed login UI.

Today:
- Implementing API integration.

Blocked:
- Waiting for authentication endpoint details.
```

For a student team, this keeps everyone aware of progress without requiring long meetings.

---

# 6. Definition of Done

A task should generally be considered complete when:

- [ ] The requirement is implemented.
- [ ] The code is tested.
- [ ] No obvious errors remain.
- [ ] The code is committed.
- [ ] The branch is pushed to GitHub.
- [ ] A Pull Request is created.
- [ ] Code review is completed.
- [ ] QA verification is completed.
- [ ] Review comments are addressed.
- [ ] Documentation is updated when necessary.
- [ ] The PR is approved and merged.

---

# 7. ATC Engineering Principles

We follow a few simple principles:

### 1. Learn by Building

Do not aim for perfect code on the first attempt. Build, test, review, learn, and improve.

### 2. Understand Before Copying

Using documentation, tutorials, AI tools, and search engines is encouraged.

However, every team member should understand the code they submit.

### 3. Small Changes Are Better

Prefer small, focused Pull Requests over huge changes that are difficult to review.

### 4. Main Should Stay Stable

The `main` branch should remain in a usable state.

### 5. Review Is Learning

Code review is not an exam. It is a way for the entire team to improve.

### 6. Ask, Don't Hide

Being stuck is normal.

Not communicating that you are stuck is what creates problems.

### 7. Team Success Over Individual Credit

We celebrate individual contributions, but the primary goal is to build a strong team and useful projects together.

---

# 8. Quick Reference

```text
1. Pick a task
      ↓
2. Update main
      ↓
3. Create feature branch
      ↓
4. Implement
      ↓
5. Test locally
      ↓
6. Commit
      ↓
7. Push branch
      ↓
8. Create Pull Request
      ↓
9. Reviewer checks code
      ↓
10. QA tests feature
      ↓
11. Fix review/QA issues
      ↓
12. Approval
      ↓
13. Merge into main
```

---

## Final Note

ATC is a student-led engineering environment.

You are not expected to know everything before starting.

You **are** expected to:

- Learn continuously.
- Communicate clearly.
- Take responsibility for your work.
- Respect your teammates.
- Review and test carefully.
- Ask for help when needed.
- Leave the codebase better than you found it.

> **Build. Review. Test. Learn. Repeat.**
