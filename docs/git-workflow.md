# Git Workflow

**Version:** 0.1.1  
**Status:** Approved  
**Last Updated:** 2026-07-04  
**Owner:** Human QA Lead

---

# Purpose

This document defines the Git branching strategy used by AI-QA-OS.

The workflow is designed to:

- maintain a clear and readable Git history;
- isolate work at both sprint and task levels;
- support code reviews;
- simplify CI/CD automation;
- preserve traceability throughout the development lifecycle.

---

# Branch Strategy

The repository uses a three-level branching model.

```
main
│
└── sprint/sprint-XXX
        │
        ├── task/...
        ├── task/...
        └── task/...
```

## Main Branch

`main` always represents the latest stable version of the project.

Rules:

- Protected branch.
- Direct commits are not allowed.
- Direct rebases are not allowed.
- Changes are introduced only through Pull Requests.

---

## Sprint Branch

Each sprint starts by creating a dedicated sprint branch from `main`.

Example:

```
sprint/sprint-000
```

The sprint branch acts as the integration branch for all work completed during the sprint.

Rules:

- Created from `main`.
- Protected after creation.
- Rebasing is not allowed.
- Changes are accepted only through Pull Requests from task branches.

---

## Task Branch

Every task is implemented in its own task branch.

Example:

```
task/S0-001-repository

task/S0-002-vision

task/S0-003-constitution
```

Rules:

- Created from the current sprint branch.
- One branch per task.
- One Pull Request per task.
- The branch owner may rebase locally before opening a Pull Request.
- After a Pull Request is opened, history should remain stable.

---

# Merge Strategy

The project uses **Merge Commit** exclusively.

Squash Merge is not allowed.

Rebase Merge is not allowed.

The merge sequence is:

```
Task Branch
        │
        ▼
Sprint Branch
        │
        ▼
Main Branch
```

This preserves the complete engineering history of the project.

---

# Pull Request Workflow

Every task follows the same lifecycle.

```
Task Assigned
        │
        ▼
Create Task Branch
        │
        ▼
Implementation
        │
        ▼
Self Review
        │
        ▼
AI Review
        │
        ▼
Human Review
        │
        ▼
Merge into Sprint Branch
```

At the end of the sprint:

```
Sprint Review
        │
        ▼
Merge Sprint Branch
        │
        ▼
main
```

---

# Branch Naming

## Sprint Branches

```
sprint/sprint-000

sprint/sprint-001

sprint/sprint-002
```

---

## Task Branches

```
task/S0-001-repository

task/S0-002-readme

task/S0-003-vision

task/S0-004-constitution
```

Branch names should:

- be descriptive;
- remain concise;
- include the task identifier whenever available.

---

# Commit Guidelines

Each commit should represent one logical change.

Commit messages should be clear and descriptive.

Examples:

```
Add project vision

Approve AI Team Constitution

Define Git workflow

Create organization document
```

Avoid combining unrelated changes in a single commit.

---

# Conflict Resolution

Merge conflicts should be resolved within the task branch before merging into the sprint branch.

Conflicts should never be resolved directly on:

- `main`
- `sprint/*`

---

# Release Flow

The end of every sprint follows this sequence:

```
Complete Sprint Tasks
        │
        ▼
Merge Task Branches
        │
        ▼
Sprint Review
        │
        ▼
Merge Sprint Branch
        │
        ▼
Tag Release
```

---

# CI/CD Integration

The Git workflow is designed to support progressive validation.

## Task Branch

Typical validation:

- Markdown validation
- Formatting
- Link validation
- Document quality checks

---

## Pull Request

Typical validation:

- AI Review
- Quality Gates
- Policy Compliance

---

## Main Branch

Typical validation:

- Release creation
- Version tagging
- Changelog generation
- Documentation publishing

---

# Guiding Principles

The Git workflow follows these principles:

- Preserve history.
- Keep changes small.
- Review before merging.
- Protect shared branches.
- Maintain traceability.
- Prefer clarity over convenience.

---

# Responsibilities

## Human QA Lead

- Creates sprint branches.
- Approves Pull Requests.
- Merges sprint branches into `main`.
- Creates project releases.

## AI Contributors

- Work only within task branches.
- Never modify protected branches directly.
- Follow the review process before requesting a merge.

---

# Document History

| Version  | Date       | Author        | Summary 
|----------|------------|---------------|--------------------------
| 0.1.0    | 2026-07-04 | Human QA Lead | Initial approved version.
| 0.1.1    | 2026-07-04 | Human QA Lead | Responsibilities section added.