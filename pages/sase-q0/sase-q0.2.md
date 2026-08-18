# Bead: sase-q0.2 — Atomic workspace allocation on every path

[Bead Pages](../README.md) / [sase-q0](README.md) / sase-q0.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.06g](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.06g.md) · **Assignee:** `sase-q0.2` · **Size:** medium
**Created:** 2026-08-18 13:44:19 EDT · **Closed:** 2026-08-18 14:27:59 EDT
**Plan:** [202608/workspace\_exclusivity.md](https://github.com/sase-org/sase--plans/blob/main/202608/workspace_exclusivity.md)

## Description

atomic: replace the deferred-workspace check-then-claim with the atomic allocate-and-claim helper, materialize the checkout only after the claim is held, and remove the remaining unchecked pinned-target claim.

## Notes

[2026-08-18T18:26:34Z · sase-q0.2] PROPOSED FOLLOW-UP: just check mypy fails on pre-existing src/sase/glossary/render.py:74 — Console(color_system=console.color_system) is str | None vs Literal color system

[2026-08-18T18:26:55Z · sase-q0.2] PROPOSED FOLLOW-UP: just check symvision still flags unused public project_accent and project_accent_map in src/sase/ace/tui/project_styles.py (sase-n4 leftover symbols)

[2026-08-18T18:27:12Z · sase-q0.2] PROPOSED FOLLOW-UP: get_claimed_workspaces/Rust list drops RUNNING rows whose artifacts timestamp is YYYYMMDD_HHMMSS (8_6); writer accepts it, reader only matches YYMMDD_HHMMSS or 14 digits

[2026-08-18T18:27:28Z · sase-q0.2] PROPOSED FOLLOW-UP: tests/completion/test_snapshot.py is out of sync with the argparse tree (xprompt list/show option key order); full-suite run reported 2 failures unrelated to workspace allocation

[2026-08-18T18:27:59Z · sase-q0.2] Deferred allocation now claims atomically via claim_next_axe_workspace before materializing, releases the slot if materialization fails, and fails a pinned occupied target in one shot with the occupant named. Remaining get_first_available_* callers are documented read-only previews; ACE/workflow check-then-claim sites now use claim_next_axe_workspace_dir. Verified with deferred-claim unit tests (skip already-claimed number, release on materialize failure, pinned live occupant) plus an escalated scoped full suite (33442 passed; 2 pre-existing completion-snapshot failures). just check is still red on unrelated mypy in glossary/render.py and leftover sase-n4 unused symbols. No --epic-symbol leftovers for this phase.

[2026-08-18T18:29:29Z · sase-q0.2] Deferred allocation now claims atomically via claim_next_axe_workspace before materializing, releases the slot if materialization fails, and fails a pinned occupied target in one shot with the occupant named. Remaining get_first_available_* callers are documented read-only previews; ACE/workflow check-then-claim sites now use claim_next_axe_workspace_dir. Verified with deferred-claim unit tests (skip already-claimed number, release on materialize failure, pinned live occupant) plus an escalated scoped full suite (33442 passed; 2 pre-existing completion-snapshot failures). just check is still red on unrelated mypy in glossary/render.py and leftover sase-n4 unused symbols. No --epic-symbol leftovers for this phase.

## Dependencies

- **Blocks:** [sase-q0.3](sase-q0.3.md) ✓ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-q0.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-q0.2/README.md) | [sase-q0.2](sase-q0.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`75e1db1`](https://github.com/sase-org/sase/commit/75e1db1ef0e593a0a84f3b5bd7e6e13f3b66b102) | fix(workspace): claim slots before materializing checkouts | [sase-q0.2](sase-q0.2.md) | 2026-08-18 14:33:03 EDT |
