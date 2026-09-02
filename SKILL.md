---
name: jira-to-spec
description: Turn an agreed conversation or feature request into a Jira-ready specification using a project profile and an explicit approval gate.
---

# Jira to specification

Produce a Jira-ready specification whose claims can be traced to agreed source
material. Drafting and publishing are separate stages.

## Build the draft from evidence

1. Read [the Jira project profile contract], load
   the project profile, and confirm its contract version.
2. Read the existing issue, source documents, repository context, and related
   work. Separate source facts, user decisions, and working assumptions.
3. Draft the problem, affected users, user-visible behaviour, solution boundary,
   implementation decisions, test approach, acceptance criteria, risks, and
   explicit non-goals.
4. Identify every claim that still needs confirmation rather than filling gaps
   with plausible detail.

## Keep mutation explicit

Show the complete draft and an exact operation preview: source evidence, target
project, issue type, labels, components, priority, assignee, and whether the
operation creates or updates an issue. Wait for explicit approval of that
preview.

Use dry-run or fixture transport until approval. The mutation boundary includes
create, update, transition, assign, comment, link, and parent changes. Prefer the
configured native Jira transport and use the documented fallback only when it
is unavailable. Prefer a native Jira API or MCP transport, with a configured CLI
adapter as the fallback.

After publishing, read the issue back and report the key, URL, resulting
metadata, and any mismatch or partial failure. If the profile, metadata,
authority, or transport is missing, remain in draft mode and state the blocker.
Never store credentials in the skill or its artefacts.

---

[the Jira project profile contract]: references/jira-profile-v1.md
