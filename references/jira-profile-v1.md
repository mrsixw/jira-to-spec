# Jira Project Profile Contract v1

The profile is supplied by the local Jira adapter. It must identify the target project, supported issue types, labels, components, priority rules, assignment policy, readiness states, parent and dependency-link rules, approval requirements, and the available transport.

The profile must declare `contract_version: 1`. If any required field is absent or contradictory, remain in dry-run mode and ask for clarification.

The transport boundary exposes read operations for issue lookup, search, metadata, comments, and links, plus separately gated mutation operations for create, update, transition, assign, comment, link, and parent changes. Tests use fixture data and must never invoke mutation operations. Native Jira APIs or MCP should be preferred in live use, with a CLI adapter only when the native transport is unavailable. Credentials belong in the environment, never in this skill or its fixtures.
