# Bead: sase-1q4.9 — Keyword-only macro inputs in sase

[Bead Pages](../README.md) / [sase-1q4](README.md) / sase-1q4.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5j.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5j.linker.w0.md) · **Assignee:** `sase-1q4.9` · **Size:** medium
**Created:** 2026-10-30 17:43:14 EDT · **Closed:** 2026-10-31 01:10:06 EDT
**Plan:** [202610/fork\_wait\_session\_turn\_target.md](https://github.com/sase-org/sase--plans/blob/main/202610/fork_wait_session_turn_target.md)

## Description

kwonly_python: mirror keyword_only in InputArg, loaders, binder, validators, serializers, schemas, macro show/explain, TUI arg assist, and docs.

## Notes

[2026-10-31T05:09:48Z · sase-1q4.9] PROPOSED FOLLOW-UP: just check symvision fails on stale --epic-symbol entries for closed bead sase-1q4.4 (plus sase-1pu.5.1 rows); reproduces identically on the clean base tree via the gate command

[2026-10-31T05:09:54Z · sase-1q4.9] PROPOSED FOLLOW-UP: test-scoped agents_sync test_repair_states_dispatches_and_reports_json fails identically on the clean base tree; already tracked by task bead sase-1q7

[2026-10-31T05:10:06Z · sase-1q4.9] Mirrored keyword_only across Python: InputArg field with repeatable-combo rejection, shortform/longform/workflow loaders (exactly-True), last-positional repeatable order, kwonly-skipping binder with preserved repeatable catch-all, frontmatter YAML and multi-prompt serialization round-trips, hint wires, JSON schemas regenerated (workflow+sase schema plus generated config docs), format_inputs = marker, ShowInput/structured/mobile/explain rendering, TUI assist hints/detection/skeletons, arguments.md docs (macros.md already covered by kwonly_core). Verified: ruff+mypy clean, 83 focused tests pass (repeatable/fork/serialization/mobile/assist/detection/skeletons), fork multi-parent regression found and fixed, epic-symbols clean; remaining check redness (stale sase-1q4.4 symbols, sase-1q7 cli_names) reproduces on base.

## Dependencies

- **Blocks:** [sase-1q4.11](sase-1q4.11.md) ◐ · ⧖ 2026-10-30
- **Depends on:** [sase-1q4.3](sase-1q4.3.md) ✓ · ⧖ 2026-10-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1q4.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1q4.9/README.md) | [sase-1q4.9](sase-1q4.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9e6e2b3`](https://github.com/sase-org/sase/commit/9e6e2b329fd94b3b3bd3840c43d787de5b8b9a04) | feat(macros): mirror keyword-only inputs across sase Python | [sase-1q4.9](sase-1q4.9.md) | 2026-10-31 01:11:51 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1q4.9][1] | check full description and notes | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1q4.9/README.md

<!-- sase:referenced-by:end -->
