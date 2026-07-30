# OpenClaw Agent Prompts

This directory contains the complete public-safe prompt files for every discovered OpenClaw agent workspace.

Included files:
- `AGENTS.md`: operating rules and workflow instructions.
- `SOUL.md`: role, persona, and behavioral posture.
- `IDENTITY.md`: agent identity metadata.

Excluded files:
- `TOOLS.md`: machine-specific tool notes and local runtime references.
- memory files, raw sessions, credentials, local configuration, and runtime state.

Sanitization:
- Absolute local paths are replaced with `<workspace-root>` or `<local-path>`.
- No rules, role instructions, or prompt sections are intentionally omitted.

The directories below are generated from the local OpenClaw workspace set. `attestations` has no prompt files and is recorded in the manifest only.

See [`manifest.md`](manifest.md) for the full inventory.
