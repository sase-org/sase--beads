# Bead: sase-qv.7 — Guidance, skill, and docs

[Bead Pages](../README.md) / [sase-qv](README.md) / sase-qv.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.07k](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.07k.md) · **Assignee:** `sase-qv.7` · **Size:** small
**Created:** 2026-08-19 09:14:34 EDT · **Closed:** 2026-08-19 13:56:58 EDT
**Plan:** [202608/monitor\_custom\_statuses.md](https://github.com/sase-org/sase--plans/blob/main/202608/monitor_custom_statuses.md)

## Description

guidance: teach TESTING/TESTED in the build-and-run memory note, make the sase_monitor skill and monitors/ACE/CLI docs state that both flags are required, and regenerate the derived instruction files.

## Notes

[2026-08-19T17:56:58Z · sase-qv.7] Taught TESTING/TESTED as the required just check / just check-full pair in build_and_run.md and regenerated AGENTS.md plus provider shims (sase memory init --check is clean on a second run). The sase_monitor skill, docs/monitors.md, and docs/ace.md now state both -s/--start-status and -S/--stop-status are required and document the pair display contract; docs/cli.md and docs/completion.md needed no change. just check passed (fmt, lint, scoped tests including generated-skills phrases). No --epic-symbol leftovers for this phase.

[2026-08-19T17:58:58Z · sase-qv.7] Taught TESTING/TESTED as the required just check / just check-full pair in build_and_run.md and regenerated AGENTS.md plus provider shims (sase memory init --check is clean). The sase_monitor skill, docs/monitors.md, and docs/ace.md now state both -s/--start-status and -S/--stop-status are required and document the pair display contract; docs/cli.md and docs/completion.md needed no change. just check passed (fmt, lint, scoped tests). No --epic-symbol leftovers for this phase.

## Dependencies

- **Depends on:** [sase-qv.2](sase-qv.2.md) ✓ · ⧖ 2026-08-19
- **Depends on:** [sase-qv.4](sase-qv.4.md) ✓ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qv.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qv.7/README.md) | [sase-qv.7](sase-qv.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`94e3a86`](https://github.com/sase-org/sase/commit/94e3a864efbec30de29ba54f1d65e086022de685) | docs(monitors): require start and stop status labels | [sase-qv.7](sase-qv.7.md) | 2026-08-19 14:00:18 EDT |
