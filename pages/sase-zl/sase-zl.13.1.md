# Bead: sase-zl.13.1 — Preserve local provenance and durable exact handoffs

[Bead Pages](../README.md) / [sase-zl.13](sase-zl.13.md) / sase-zl.13.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zl.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zl.land.md) · **Assignee:** `sase-zl.13.1` · **Size:** medium
**Created:** 2026-09-11 23:43:26 EDT · **Closed:** 2026-09-12 01:04:10 EDT
**Plan:** [202609/monitor\_continuation\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/monitor_continuation_landing_repairs.md)

## Description

capture: exclude injected ancestry from canonical local records, accept authored checkpoints, and publish immutable recoverable handoffs with exact parent references.

## Notes

[2026-09-12T05:04:10Z · sase-zl.13.1] Capture now excludes injected ancestry from canonical local deltas without Markdown delimiter parsing: complete_prompt_segments no longer dumps the expanded prompt as local_materialized, fork/fork_by_chat prompt_parts are marked injected_parent, and agent-delta records keep only local_authored/local_materialized segments while the full prompt remains a debug archive. Hostile headings/directives stay literal. Immutable content-addressed writes plus a recoverable publication journal persist blobs then records then pointers; same-content retries are idempotent and conflicting/incomplete pointer writes cannot publish success. Added -k/--checkpoint FILE (bounded YAML/JSON) with authored fields distinct from host facts, next action only on the intent, and fingerprint binding of checkpoint digest, resolved parent IDs, and starter run identity rather than a pathname. Exact parents are peeked at launch, starter delta is connected on handoff, monitor results hydrate from the starter artifacts dir, and essential capture failure sets needs_recovery so automatic follow-up dispatch is blocked except for stopped/lost. Verified with capture/journal/checkpoint/fingerprint/parser tests, monitor start/handoff/stop/cleanup, and just check (1143 scoped test files).

## Dependencies

- **Blocks:** [sase-zl.13.2](sase-zl.13.2.md) ◐ · ⧖ 2026-09-11
- **Blocks:** [sase-zl.13.3](sase-zl.13.3.md) ✓ · ⧖ 2026-09-11
- **Blocks:** [sase-zl.13.4](sase-zl.13.4.md) ◐ · ⧖ 2026-09-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zl.13.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zl.13.1/README.md) | [sase-zl.13.1](sase-zl.13.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e530d97`](https://github.com/sase-org/sase/commit/e530d978f0aa861e832ab14fb202cd44cbfa488b) | feat(continuation): persist local provenance and exact monitor handoffs | [sase-zl.13.1](sase-zl.13.1.md) | 2026-09-12 01:08:01 EDT |
