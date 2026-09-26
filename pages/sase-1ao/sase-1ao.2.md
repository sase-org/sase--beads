# Bead: sase-1ao.2 — Apply shared edits in the prompt widget

[Bead Pages](../README.md) / [sase-1ao](README.md) / sase-1ao.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.1x](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.1x.md) · **Assignee:** `sase-1ao.2` · **Size:** medium
**Created:** 2026-09-26 10:14:36 EDT · **Closed:** 2026-09-26 12:31:15 EDT
**Plan:** [202609/model\_shortcut\_replacement.md](https://github.com/sase-org/sase--plans/blob/main/202609/model_shortcut_replacement.md)

## Description

widget_adoption: adopt the core selection result in the Python widget, update the core revision pin, and verify cross-frontend parity.

## Notes

[2026-09-26T16:30:44Z · sase-1ao.2--1] PROPOSED FOLLOW-UP: just check has 30+ pre-existing failures reproducing identically on clean base (completion snapshot/kind-coverage, bgcmd dismiss, admin-center resume x8, proc-observer x5, procs-pane-store x7, config-schema receipt key, models-surface, agent-session terminology, getting-started providers wording); needs triage by owning agents

[2026-09-26T16:31:15Z · sase-1ao.2--1] Widget adopts shared multi-edit/caret result for = and == with sase-core pin e1179e6; 134 focused tests pass (parity, alias, explicit). Fixed misplaced parametrize on equals-alias test and 3 caret literals (15/15/24, end of inserted directive incl. trailing space, matching app-level test). Remaining just-check failures reproduce identically on clean base, recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-1ao.1](sase-1ao.1.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1ao.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1ao.2.md) | [sase-1ao.2](sase-1ao.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e922c42`](https://github.com/sase-org/sase/commit/e922c424e2e8bd22aac06fdb69c255ff15f33863) | feat(ace): adopt shared model-shortcut edits in prompt widget (sase-1ao.2) | [sase-1ao.2](sase-1ao.2.md) | 2026-09-26 12:33:10 EDT |
