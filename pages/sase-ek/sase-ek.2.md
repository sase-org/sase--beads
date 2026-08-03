# Bead: sase-ek.2 — The host labels each repository and proves both surfaces agree

[Bead Pages](../README.md) / [sase-ek](README.md) / sase-ek.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.si](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.si/README.md) · **Assignee:** `sase-ek.2` · **Size:** small
**Created:** 2026-08-03 10:33:38 UTC · **Closed:** 2026-08-03 11:08:00 UTC
**Plan:** [202608/commit\_completion\_excludes\_sidecars.md](https://github.com/sase-org/sase--plans/blob/main/202608/commit_completion_excludes_sidecars.md)

## Description

host_repo_kind: carry `RepoRecord.kind` into `ArtifactRefRepository` and its wire form in `artifact_ref_context()`, extend the prompt-bar/LSP parity test with a sidecar repository, assert sidecar resolution still succeeds, and correct the two documentation sentences that promise commits from every local checkout.

## Notes

[2026-08-03T11:08:00Z · sase-ek.2] Carried RepoRecord.kind into ArtifactRefRepository/to_wire() and artifact_ref_context(); extended tests/artifact_refs/test_context.py to assert kind propagation; extended the prompt-bar/LSP parity test in tests/ace/tui/widgets/test_artifact_ref_completion_catalog.py with a kind=sidecar fixture holding the newest commit, verifying it is excluded from both surfaces, truncated_payloads is unaffected, and @commit:<sidecar>@<sha> still resolves via _resolve_for_launch (D4 invariant). Corrected the two local-git-checkout sentences in docs/editor.md and docs/getting_started.md to note sidecar exclusion and full-reference resolution. Verified with just check (fmt, lint, test) — all green.

## Dependencies

- **Depends on:** [sase-ek.1](sase-ek.1.md) ✓
- **Blocks:** [sase-ek.3](sase-ek.3.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ek.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ek.2/README.md) | [sase-ek.2](sase-ek.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`70410a0`](https://github.com/sase-org/sase/commit/70410a05b1a6250bbe6adb86c41a65cbef827e9b) | feat(artifact-refs): propagate repository kind into wire form and parity test | [sase-ek.2](sase-ek.2.md) | 2026-08-03 11:08:56 |
