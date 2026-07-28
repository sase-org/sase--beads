# Bead: sase-a0.1 — Resolve the bead store from a plain checkout

[Bead Pages](../README.md) / [sase-a0](README.md) / sase-a0.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-a0.1` · **Size:** medium
**Created:** 2026-07-27 16:01:44 UTC · **Closed:** 2026-07-27 16:19:10 UTC
**Plan:** [202607/fix\_ci\_failures.md](https://github.com/sase-org/sase--plans/blob/main/202607/fix_ci_failures.md)

## Description

beadstore: teach bead-store location resolution to honor a checkout-local `.sase/sdd-store.json` sidecar record when no SASE workspace context resolves, so `sase bead show` works in CI and every `--epic-symbol` entry stops reporting a missing bead.

## Dependencies

- **Blocks:** [sase-a0.4](sase-a0.4.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-a0.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-a0.1/README.md) | [sase-a0.1](sase-a0.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`26ead3f`](https://github.com/sase-org/sase/commit/26ead3f39ac89b6969b71ce1872edab834760aee) | fix(bead): resolve sidecar store from plain checkouts (sase-a0.1) | [sase-a0.1](sase-a0.1.md) | 2026-07-27 16:20:31 |
