# Project and Repository Registry

This registry records the Git repositories that ABME directly uses, depends on,
or references. It is an architectural index, not a vendored source tree and not
a record of local machine state.

## Categories

- **Direct integration**: a repository whose CLI, service, library, or workflow
  is called by ABME.
- **Reference or upstream**: a repository used as a documented dependency,
  implementation reference, or upstream source.
- **Candidate**: a repository under evaluation. Candidates must not be treated
  as production dependencies.

## Registered Repositories

### wxhub

- **Category**: Direct integration
- **Public repository**: <https://github.com/Wuszzzz/wxhub>
- **Default branch**: `main`
- **Role**: Hosts the local `wxpub` CLI and Studio service used to validate,
  render, preview, and create or update WeChat Official Account drafts.
- **ABME contract**: ABME owns content judgment, review gates, and the decision
  to create or update a draft. `wxhub` performs the output-side compilation and
  connector operations. See [Wxpub CLI](../integrations/wxpub-cli.md).
- **Publication boundary**: Do not copy credentials, account configuration,
  authorized style resources, local paths, draft IDs, or runtime logs into this
  repository.

## Registration Template

Add one entry for every newly adopted repository. Keep entries specific enough
to reproduce the integration decision without disclosing private runtime data.

```markdown
### <repository name>

- **Category**: Direct integration | Reference or upstream | Candidate
- **Public repository**: <canonical repository URL, or "not public">
- **Default branch / version**: <branch, tag, or commit policy>
- **Role**: <what ABME uses it for>
- **ABME contract**: <inputs, outputs, responsibility boundary, and approval gate>
- **Publication boundary**: <what must remain private or excluded>
```

## Maintenance Rules

1. Register a repository before relying on it in a reusable ABME workflow.
2. Update the entry when the repository role, supported version, or integration
   boundary changes.
3. Do not vendor a repository here by default. Use a Git submodule or subtree
   only when ABME must develop and version-lock that source together with this
   repository.
4. Never record credentials, local absolute paths, personal content, draft IDs,
   private remotes, or raw runtime output.
