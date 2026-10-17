# vct-cribl

vct-cribl holds Cribl Edge and Stream packs for collecting developer telemetry,
operational metrics, and search integration data.

## Shared CI and releases

- Reuse workflows from `JacobPEvans/.github` and `JacobPEvans/.github-ai`.
  Reference both at `@v1`; never pin them to a commit SHA.
- Keep organization-managed CI and release steps in the reusable workflows.
  Local workflow files should call the shared implementation with repository
  specific inputs.
- Give each repository exactly one `release.yml` caller for its release
  workflow.
- Configure Renovate to extend only `github>JacobPEvans/.github`.
- Enterprise rulesets inject required checks. Do not add repository copies of
  shared checks.

## Domain conventions

- Version each pack independently with semantic versioning.
- For patch and minor releases, update `package.json` and the README release
  notes. Leave major version changes for a human decision.
- Build `.crbl` archives from `data`, `default`, `package.json`, and `README.md`.
  Name both versioned and stable archives after the pack.
- Keep repository-specific release timing and artifact handling in each pack's
  documentation.

## Repository map

| Repository | Purpose |
| --- | --- |
| `GoatSearchTest` | Search integration test suite |
| `cc-edge-claude-code-otel` | Assistant session telemetry pack |
| `cc-edge-gemini-antigravity-io` | IDE and agent session file collection |
| `cc-edge-copilot-otel` | Assistant OTLP telemetry pack |
| `cc-edge-vscode-io` | Editor and extension log collection |
| `cc-stream-github-copilot-rest-io` | Usage metrics API pack |
| `cc-stream-zscaler-incident-test` | Route-cloning scenario test matrix |
| `.github` | Organization profile |
