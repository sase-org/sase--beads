# Bead: sase-zs.8 — Surface transport degradation before it fails a run

[Bead Pages](../README.md) / [sase-zs](README.md) / sase-zs.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0k6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0k6.md) · **Assignee:** `sase-zs.8` · **Size:** small
**Created:** 2026-09-12 09:44:56 EDT · **Closed:** 2026-09-12 14:31:49 EDT
**Plan:** [202609/github\_network\_resilience.md](https://github.com/sase-org/sase--plans/blob/main/202609/github_network_resilience.md)

## Description

observability: record near-miss margin and retry outcomes on network git operations and add a doctor check that warns when durations trend toward the configured ceiling.

## Notes

[2026-09-12T18:31:49Z · sase-zs.8] Implemented SDD git transport observability: enriched git-op telemetry with duration margin, retry attempt/reference metadata, classifier verdicts, and added the vcs.git_transport_margin doctor check over local JSONL telemetry. Also removed stale sase-zs.5 symvision whitelist entries and updated the sase-core-rs floor/wire adapters needed for the classifier-capable core. Verified focused pytest suites and just check; just check escalated to the full governed test lane and passed.

## Dependencies

- **Depends on:** [sase-zs.3](sase-zs.3.md) ✓ · ⧖ 2026-09-12
- **Depends on:** [sase-zs.4](sase-zs.4.md) ✓ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zs.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zs.8/README.md) | [sase-zs.8](sase-zs.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b681d50`](https://github.com/sase-org/sase/commit/b681d5072ff06553a95402e36917b0e697ce0905) | feat(sdd): surface git transport degradation | [sase-zs.8](sase-zs.8.md) | 2026-09-12 15:31:13 EDT |
