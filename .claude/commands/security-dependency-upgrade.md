---
name: security-dependency-upgrade
description: Workflow command scaffold for security-dependency-upgrade in qcortex.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /security-dependency-upgrade

Use this workflow when working on **security-dependency-upgrade** in `qcortex`.

## Goal

Upgrade dependencies to address security vulnerabilities, often triggered by automated tools like Snyk or Dependabot.

## Common Files

- `package.json`
- `extensions/zalo/package.json`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Detect vulnerability in a dependency (e.g., via Snyk/Dependabot).
- Update the affected dependency version in package.json or equivalent manifest.
- Commit the change with a message referencing the vulnerability or upgrade.
- Optionally, merge an automated pull request.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.