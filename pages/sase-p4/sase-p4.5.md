# Bead: sase-p4.5 — User-facing documentation

[Bead Pages](../README.md) / [sase-p4](README.md) / sase-p4.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.05e](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.05e.md) · **Assignee:** `sase-p4.5` · **Size:** small
**Created:** 2026-08-17 18:53:41 EDT · **Closed:** 2026-08-18 01:12:10 EDT
**Plan:** [202608/epic\_resume\_gate.md](https://github.com/sase-org/sase--plans/blob/main/202608/epic_resume_gate.md)

## Description

docs: document the gate, the chop, the feature flag, and the config knobs across the notification, AXE, bead, and configuration docs.

## Notes

[2026-08-18T05:12:10Z · sase-p4.5] Documented the EpicResume gate, epic_resume chop, epic_resume_gate feature flag, and bead.epic_resume.settle_seconds config knob across docs/notifications.md (Panel row, priority actions, privileged-action rejection list, sender/event table, new Stalled Epic Notification section, action field table, kind/action/producer table), docs/axe.md (checks-lumberjack table row + prose subsection), docs/beads.md (cross-reference from the epic-work stall paragraph), and docs/configuration.md (bead.epic_resume.settle_seconds field + how to enable the epic_resume_gate beta). just install and just check (fmt python, fmt markdown after just fmt, keep-sorted, ruff, mypy, feature flags, pyscripts, test waits, changelog, patch/stitch terminology, symvision, toobig) all pass; the one just check failure (SASE validation doctor config.file_hooks, an unrelated pre-existing user-config plugin issue) was confirmed via git stash to already fail identically on master before this change. sase bead epic-symbols sase-p4.5 reports no leftover --epic-symbol entries.

[2026-08-18T05:12:52Z · sase-p4.5] Documented the EpicResume gate, epic_resume chop, epic_resume_gate feature flag, and bead.epic_resume.settle_seconds config knob across docs/notifications.md, docs/axe.md, docs/beads.md, and docs/configuration.md. just install and just check pass (the one failure, doctor config.file_hooks, is a pre-existing unrelated issue confirmed on master via git stash). sase bead epic-symbols sase-p4.5 reports no leftover entries.

## Dependencies

- **Depends on:** [sase-p4.4](sase-p4.4.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p4.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p4.5/README.md) | [sase-p4.5](sase-p4.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d23a269`](https://github.com/sase-org/sase/commit/d23a269e0dad75cdd8d4c154d5744e079b651986) | docs: document the EpicResume gate, epic\_resume chop, and its config | [sase-p4.5](sase-p4.5.md) | 2026-08-18 01:13:30 EDT |
