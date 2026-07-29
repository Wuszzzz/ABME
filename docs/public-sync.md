# ABME Public Engineering Sync

## Purpose

`Wuszzzz/ABME` is the public engineering mirror for reusable ABME assets. It makes the system inspectable without exposing personal data or raw operating traces.

## Required synchronization

When a reusable asset is added or changed, update this repository in the same work item:

1. Agent roles, public prompt structures, behavioral rules, and collaboration boundaries.
2. Reusable `SKILL.md` procedures and usage notes.
3. CLI and MCP connection patterns, setup assumptions, and safe examples.
4. Reusable templates, architecture diagrams, integration specifications, and structured decision notes.

The source of truth may remain in a private workspace or SiYuan while an asset is being developed. Once a reusable version is stable, synchronize its reviewed public form here before the work item is closed.

## Never synchronize

- API keys, tokens, passwords, cookies, SSH keys, or local credential files.
- Personal memory, user profiles, private SiYuan content, or raw conversation exports.
- Unreviewed logs, sensitive paths, private contact details, and machine-specific runtime state.
- Proprietary source material that is not cleared for publication.

## Working procedure

1. Decide whether the change is reusable and safe to publish.
2. Remove private context and replace local-only details with documented assumptions.
3. Update the matching directory: `agents/`, `skills/`, `integrations/`, `docs/`, or `diagrams/`.
4. Review `git diff` and run a secret scan before committing.
5. Commit with a clear message and push after the repository owner approves the public change.

## Completion rule

All ABME agents treat this as a completion condition: reusable changes to prompts, skills, agents, CLI, MCP, or integrations are incomplete until their public-safe representation is added here, or explicitly recorded as excluded with a reason.
