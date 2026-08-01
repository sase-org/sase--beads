# Bead: sase-dh.7 — Documentation, sidecar READMEs, and discoverability

[Bead Pages](../README.md) / [sase-dh](README.md) / sase-dh.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.rh](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.rh/README.md) · **Assignee:** `sase-dh.7` · **Size:** small
**Created:** 2026-08-01 15:08:33 UTC · **Closed:** 2026-08-01 19:54:04 UTC
**Plan:** [202608/artifact\_persistence\_sidecars.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_persistence_sidecars.md)

## Description

docs: refresh sidecar README templates, user docs, and command help so the new artifact and prompt layout is discoverable.

## Notes

[2026-08-01T19:28:50Z · sase-dh.7] PROPOSED FOLLOW-UP: Regenerate plans sidecar directory-map PNG — src/sase/sdd/assets/plans-directory-map.png still labels prompts as living in the plans sidecar even after the canonical prompt archive moved to the agents sidecar.

[2026-08-01T19:47:11Z · sase-dh.7] PROPOSED FOLLOW-UP: Complete canonical prompt archive migration and plan-link repair — `sase validate` still reports 5765 existing plans-sidecar prompt/link errors after docs refresh, while `sase agent prompts validate` passes.

[2026-08-01T19:53:03Z · sase-dh.7] PROPOSED FOLLOW-UP: Fix unrelated default-suite failures observed during docs verification — `just test` still fails in TUI test helpers/imports, bead CLI golden snapshots, bead mutation contention, and an agents_sync import-boundary check after this docs phase-specific assertions were updated.

[2026-08-01T19:54:04Z · sase-dh.7] Updated docs/templates/help/skill text for the agents-sidecar prompt and artifact archive; verified just fmt-py-check, just lint, docs-check, validate-committed-plans, focused tests, init repo --check, and agent prompts validate. just check still stops at init skills deployment guard and existing plan links validation debt; unrelated default-test failures and follow-ups recorded.

[2026-08-01T19:55:19Z · sase-dh.7] Verified docs/help updates with focused tests, docs check, committed-plan validation, repo init check, agent prompts validate, and reran just check through known validation blockers

## Dependencies

- **Depends on:** [sase-dh.6](sase-dh.6.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-dh.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-dh.7/README.md) | [sase-dh.7](sase-dh.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`527e645`](https://github.com/sase-org/sase/commit/527e6458225baeb0e45feb6e63e2b24900eeb3a2) | docs: document agents-sidecar prompt archives | [sase-dh.7](sase-dh.7.md) | 2026-08-01 19:56:27 |
