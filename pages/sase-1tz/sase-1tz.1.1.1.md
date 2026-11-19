# Bead: sase-1tz.1.1.1 — Coalesce identical +1s and stop rewriting the store for dismissed rows

[Bead Pages](../README.md) / [sase-1tz.1.1](sase-1tz.1.1.md) / sase-1tz.1.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.1.md) · **Assignee:** `sase-1tz.1.1.1` · **Size:** medium
**Created:** 2026-11-19 07:28:40 EST · **Closed:** 2026-11-19 08:52:50 EST
**Plan:** [202611/outage\_disk\_attribution\_and\_held\_workspaces.md](https://github.com/sase-org/sase--plans/blob/main/202611/outage_disk_attribution_and_held_workspaces.md)

## Description

store_guard: in sase-core, key-based +1s to dismissed rows become no-ops unless the caller opts in, and identical +1s within a window coalesce. Neither path rewrites the store or bumps its generation. Python adopts the new outcomes, and the pin moves.

## Notes

[2026-11-19T13:52:20Z · sase-1tz.1.1.1] PROPOSED FOLLOW-UP: Investigate full-suite flake in tests/ace/tui/test_prompt_bar_hot_spare.py — failed in the 14-worker just check run with Textual KeyError text-area--gutter, but passed targeted on both the edited tree and clean base.

[2026-11-19T13:52:50Z · sase-1tz.1.1.1] Implemented +1 coalescing and dismissed-row no-op/opt-in behavior across core and Python; added parity and caller tests and updated docs/completion snapshot. Linked core just check passed; primary just check ran 62,074 passed and exposed two completion snapshot failures fixed by regeneration plus one full-suite-only prompt-bar failure, which passed targeted on the edited tree and clean base. Focused notification/completion tests passed, diffs are clean, and the prompt-bar flake is recorded as a proposed follow-up.

## Dependencies

- **Blocks:** [sase-1tz.1.1.2](sase-1tz.1.1.2.md) ◐ · ⧖ 2026-11-19
- **Blocks:** [sase-1tz.1.1.6](sase-1tz.1.1.6.md) ◐ · ⧖ 2026-11-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.1.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.1.1.1/README.md) | [sase-1tz.1.1.1](sase-1tz.1.1.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@d8681db`](https://github.com/sase-org/sase-core/commit/d8681dbbff2b435cbb83d7052db7c118afcd9b67) | feat(notifications): coalesce plus-one updates | [sase-1tz.1.1.1](sase-1tz.1.1.1.md) | 2026-11-19 08:54:40 EST |
| sase | [`ed5cb12`](https://github.com/sase-org/sase/commit/ed5cb12ef9ccd656302dbacf045a856e9e77f6c2) | feat(notifications): coalesce repeated plus-ones | [sase-1tz.1.1.1](sase-1tz.1.1.1.md) | 2026-11-19 08:55:52 EST |
