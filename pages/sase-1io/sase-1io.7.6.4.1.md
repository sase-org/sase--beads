# Bead: sase-1io.7.6.4.1 — Stop a popped plugins pane from reloading its catalog

[Bead Pages](../README.md) / [sase-1io.7.6.4](sase-1io.7.6.4.md) / sase-1io.7.6.4.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1io.7.6.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1io.7.6.land.md) · **Assignee:** `sase-1io.7.6.4.1` · **Size:** small
**Created:** 2026-10-10 09:29:18 EDT · **Closed:** 2026-10-10 09:57:24 EDT
**Plan:** [202610/finish\_v0\_18\_0\_ship.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_v0_18_0_ship.md)

## Description

mount-race: stop the unchanged update-completion path from starting a catalog load when the plugins pane has already been popped, and note the fix on sase-1ja.

## Notes

[2026-10-10T13:57:12Z · sase-1io.7.6.4.1] PROPOSED FOLLOW-UP: lint (feature flags) rule 7 fails identically on the clean base tree (closed beads sase-wr, sase-rx, sase-qu, sase-105 still define flags) — owned by in-progress epic sase-1jc, not this phase

[2026-10-10T13:57:24Z · sase-1io.7.6.4.1] mount-race done: unchanged update-completion path now reloads only when the pane's screen is still presented (_is_still_presented gate on app.screen); invalidate stays unconditional. Noted root-cause fix on sase-1ja. New regression test_mutation_completion_while_covered_starts_no_catalog_load fails on old code, passes with fix; full cached-open file 11 passed. ruff+mypy clean. sase tool run check red only on pre-existing feature-flags rule 7 (identical on clean base, owned by sase-1jc, recorded as PROPOSED FOLLOW-UP). No epic-symbol entries.

## Dependencies

- **Blocks:** [sase-1io.7.6.4.2](sase-1io.7.6.4.2.md) ◐ · ⧖ 2026-10-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1io.7.6.4.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1io.7.6.4.1/README.md) | [sase-1io.7.6.4.1](sase-1io.7.6.4.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6846614`](https://github.com/sase-org/sase/commit/68466146bff9b1ff16b7145df344a90224b397d5) | fix(plugins-browser): skip unchanged-completion catalog reload once the pane is popped | [sase-1io.7.6.4.1](sase-1io.7.6.4.1.md) | 2026-10-10 09:58:52 EDT |
