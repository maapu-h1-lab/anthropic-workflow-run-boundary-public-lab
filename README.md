# GitHub Validation Skeleton

Use these files only in a private owned GitHub repository with no sensitive secrets.

Purpose:

- Validate A-004 safely.
- Learn how `workflow_run` metadata behaves before adding Claude Code Action or Anthropic credentials.
- Avoid running untrusted PR code with elevated permissions.

Files:

- `.github/workflows/ci.yml`: minimal CI workflow that can complete/fail on PRs.
- `.github/workflows/workflow_run_metadata.yml`: metadata-only `workflow_run` observer.

Setup:

1. Create a private owned test repo.
2. Copy this `.github/workflows/` directory into that repo.
3. Open a PR from an owned branch.
4. Inspect the `Workflow Run Metadata Check` logs.
5. Repeat from a fork/non-collaborator only if you control that identity.

Do not add:

- `ANTHROPIC_API_KEY`
- `CLAUDE_CODE_OAUTH_TOKEN`
- write permissions
- Claude Code Action

Add those only after the event boundary is understood and still looks worth validating.
