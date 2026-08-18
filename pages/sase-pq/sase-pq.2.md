# Bead: sase-pq.2 — Frozen task-type presentation

[Bead Pages](../README.md) / [sase-pq](README.md) / sase-pq.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.060](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.060.md) · **Assignee:** `sase-pq.2` · **Size:** medium
**Created:** 2026-08-18 09:38:04 EDT · **Closed:** 2026-08-18 10:49:54 EDT
**Plan:** [202608/task\_type\_gate\_presentation.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_type_gate_presentation.md)

## Description

freeze: add the module that resolves one task type into a frozen glyph, human name, accent, and ordered required-field facts at gate-creation time, plus the strict parser, chip projection, note line, and Markdown fact every later phase renders from.

## Notes

[2026-08-18T14:49:54Z · sase-pq.2] Verified resolve_task_type_gate_display('flake', {...}) round-trips through payload→parse as identity; each builtin type freezes the same glyph/name/accent as task_type_presentation; untyped is None; unresolved slugs degrade to '?' + raw field names; facts follow required spec order, drop empty values, collapse newlines, truncate to 80 cells, and cap at three pairs; chip/note/markdown projections match the plan examples and share format_task_type_chip with the live chip; the parser accept/reject table holds; only the resolver reads the registry; the module does not import notification_gates. just check passed (scoped escalated to the full suite because the Justfile gained sase-pq.5 epic-symbols for the new public API).

[2026-08-18T14:51:01Z · sase-pq.2] Verified resolve_task_type_gate_display('flake', {...}) round-trips through payload→parse as identity; each builtin type freezes the same glyph/name/accent as task_type_presentation; untyped is None; unresolved slugs degrade to '?' + raw field names; facts follow required spec order, drop empty values, collapse newlines, truncate to 80 cells, and cap at three pairs; chip/note/markdown projections match the plan examples and share format_task_type_chip with the live chip; the parser accept/reject table holds; only the resolver reads the registry; the module does not import notification_gates. just check passed (scoped escalated to the full suite because the Justfile gained sase-pq.5 epic-symbols for the new public API).

## Dependencies

- **Depends on:** [sase-pq.1](sase-pq.1.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-pq.5](sase-pq.5.md) ✓ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-pq.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-pq.2/README.md) | [sase-pq.2](sase-pq.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`097a1a7`](https://github.com/sase-org/sase/commit/097a1a75145848c530bb68ea1d4588245f1a1b0c) | feat(task-types): freeze task-type presentation at gate-creation time | [sase-pq.2](sase-pq.2.md) | 2026-08-18 10:53:00 EDT |
