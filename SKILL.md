---
name: jira-to-spec
description: Turn an agreed conversation or feature request into a Jira-ready specification using a project profile and an explicit approval gate.
---

# Jira to Spec

## Workflow

1. Read [the Jira project profile contract](references/jira-profile-v1.md), load the project profile, and confirm its contract version.
2. Read the existing issue, source documents, repository context, and related work.
3. Draft the problem, user stories, solution, implementation decisions, testing decisions, and out-of-scope behavior.
4. Show the complete draft, source evidence, target project, issue type, labels, components, priority, and assignee.
5. Wait for explicit approval before creating or updating Jira.
6. Publish only the approved result through the configured Jira transport and report the key and URL.

If the profile or required Jira metadata is missing, remain in draft mode and ask for the missing information. Never store credentials in the skill or its artifacts.

## Transport and safety

Use dry-run or fixture transport unless the user explicitly approves the exact
Jira operation. The transport boundary covers create, update, transition,
assign, comment, link, and parent changes. Prefer a native Jira API or MCP
transport in live use and fall back to a CLI adapter only when needed.
