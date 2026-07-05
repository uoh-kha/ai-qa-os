# Role Metadata Standard

**Version:** 0.1.0  
**Status:** Approved  
**Last Updated:** 2026-07-05  
**Owner:** Human QA Lead

---

# Purpose

This document defines the minimum metadata required for every AI role specification.

The purpose of role metadata is to provide a consistent and concise overview of a role before the detailed description begins.

Metadata helps readers quickly understand the role's identity, organizational context, and responsibilities.

---

# Required Metadata

Every role specification should include the following metadata.

| Field | Description |
|--------|-------------|
| Role ID | A unique identifier for the role. |
| Role Name | The official role name. |
| Category | The organizational area to which the role belongs (e.g., Product Management, Quality Assurance, Engineering, Governance). |
| Version | Current version of the role specification. |
| Status | Current document status (Draft, Approved, Deprecated). |
| Reports To | The role responsible for reviewing and approving this role's work. |
| Previous Roles | Roles that typically provide input to this role within the workflow. |
| Next Roles | Roles that typically consume this role's outputs. |
| Primary Inputs | The main artifacts or information required by the role. |
| Primary Outputs | The primary deliverables produced by the role. |

---

# Metadata Format

Role metadata should appear at the beginning of every role specification.

The project currently uses a simple Markdown table.

Example:

| Field | Value |
|--------|-------|
| Role ID | ROLE-001 |
| Role Name | Product Owner |
| Category | Product Management |
| Version | 0.1.0 |
| Status | Draft |
| Reports To | Human QA Lead |
| Previous Roles | Human QA Lead |
| Next Roles | Business Analyst |
| Primary Inputs | Product Vision, Task Definition |
| Primary Outputs | Requirements, User Stories, Acceptance Criteria |

---

# Guidelines

Role metadata should:

- be concise;
- contain factual information only;
- be kept up to date;
- avoid duplication with the main document;
- provide a quick overview of the role.

Detailed explanations belong in the body of the role specification.

---

# Future Improvements

Future versions may introduce machine-readable metadata if a clear engineering need arises.

Such changes should remain backward compatible with existing role specifications whenever possible.

---

# Document History

| Version | Date | Author | Summary |
|----------|------|--------|---------|
| 0.1.0 | 2026-07-05 | Human QA Lead | Initial approved version. |