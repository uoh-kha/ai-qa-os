# AI Agent Implementations

**Version:** 0.1.0
**Status:** Approved
**Last Updated:** 2026-07-05
**Owner:** Human QA Lead

---

# Purpose

This directory contains implementations of AI roles for specific AI platforms.

AI-QA-OS distinguishes between a **Role** and an **Agent**.

A role defines **what** work should be performed.

An agent defines **how** a specific AI platform performs that work.

This separation allows the same organizational model to be implemented using different AI tools without changing the underlying engineering process.

---

# Roles vs Agents

## Role

A role is platform-independent.

It defines:

- mission;
- responsibilities;
- inputs;
- outputs;
- quality standards;
- collaboration rules;
- decision boundaries.

Roles are located in:

```
roles/
```

---

## Agent

An agent is a platform-specific implementation of a role.

It may include:

- system prompts;
- project instructions;
- configuration files;
- tool permissions;
- context-loading strategy;
- platform-specific limitations.

Agents are located in:

```
agents/<platform>/
```

---

# Supported Platforms

The architecture is intentionally platform-agnostic.

Examples include:

- Claude Code
- ChatGPT
- Gemini CLI
- Codex CLI
- Cursor
- GitHub Copilot

Additional platforms may be added without modifying role definitions.

---

# Design Principle

The relationship between roles and agents is:

```
Role Specification
        │
        ▼
Agent Implementation
        │
        ▼
AI Platform
```

Multiple agents may implement the same role.

Similarly, the same AI platform may implement multiple roles.

---

# Guiding Principles

- Roles remain platform-independent.
- Agents implement roles without changing their intent.
- Platform-specific behavior should never modify organizational responsibilities.
- Changes to agent implementations should not require changes to role specifications unless organizational responsibilities change.

---

# Example

```
roles/
    product-owner.md

agents/
    claude-code/
        product-owner.md

    chatgpt/
        product-owner.md

    gemini-cli/
        product-owner.md
```

Each implementation should fulfill the same role specification while adapting to the capabilities and limitations of the corresponding AI platform.

---

# Document History

| Version | Date | Author | Summary |
|----------|------|--------|---------|
| 0.1.0 | 2026-07-05 | Human QA Lead | Initial approved version. |