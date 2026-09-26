# Bead: sase-17d.10.1.4 — Finish the deck cutover's visual migration, coverage goldens and live checks

[Bead Pages](../README.md) / [sase-17d.10.1](sase-17d.10.1.md) / sase-17d.10.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17d.10.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-17d.10.1.land.md) · **Assignee:** `sase-17d.10.1.4.land`
**Created:** 2026-09-24 17:30:37 EDT · **Closed:** 2026-09-24 22:21:09 EDT
**Plan:** [202609/deck\_cutover\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/deck_cutover_landing_repairs.md)

## Description

Every ACE visual test that still drives the deleted legacy Agents detail UI is migrated to the deck API (or deleted when its subject is gone), its goldens are regenerated and inspected, the coverage goldens and live screenshot checks that the cutover-goldens phase skipped are done, and `just fix-tui-screenshots --check` is clean apart from failures that reproduce without the cutover.

## Notes

[2026-09-25T02:21:09Z · 0ru] Deck cutover landing repairs complete (finished by one tale agent per the user's request): remaining land-agent repairs and 17 legacy visual tests migrated to the deck API, deck chrome fixed (deterministic Main accent, true border-label budget, count-less subtitle tier, width-aware search help), 3 coverage goldens added, live screenshots inspected, full update inspected and full just fix-tui-screenshots --check clean except the unrelated command_line/top-bar nodes (tasks sase-18o, sase-18n). Also filed sase-18m (Files spread probe never completes) and sase-18p (90-column deck collapse).

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.0ru](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ru.md) | [sase-17d.10.1.4](sase-17d.10.1.4.md) | 1 |
| [bbugyi200.athena.sase-17d.10.1.4.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17d.10.1.4.land/README.md) | [sase-17d.10.1.4](sase-17d.10.1.4.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a674dc9`](https://github.com/sase-org/sase/commit/a674dc91f186c653399a681f97d456876edbcb19) | test(ace): finish the deck cutover's visual migration and chrome fixes (sase-17d.10.1.4) | [sase-17d.10.1.4](sase-17d.10.1.4.md) | 2026-09-24 22:50:42 EDT |
