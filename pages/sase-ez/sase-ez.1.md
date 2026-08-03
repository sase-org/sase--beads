# Bead: sase-ez.1 — Revert the sase-repo bead re-prefix surface

[Bead Pages](../README.md) / [sase-ez](README.md) / sase-ez.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sy](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sy/README.md) · **Assignee:** `sase-ez.1` · **Size:** medium
**Created:** 2026-08-03 11:32:11 EDT · **Closed:** 2026-08-03 14:52:01 EDT
**Plan:** [202608/revert\_bead\_reprefix\_epic.md](https://github.com/sase-org/sase--plans/blob/main/202608/revert_bead_reprefix_epic.md)

## Description

sase-revert: revert the three sase-ei commits in the sase repo, keep the unrelated forward mint guard, resolve the three known conflict files, and prove the reverted tree still builds, lints, and passes the bead/agents_sync suites.

## Notes

[2026-08-03T19:33:51Z · sase-ez.1] PROPOSED FOLLOW-UP: Update config-center agent CLI PNG snapshots - just check now deterministically fails the two agent-CLI visual goldens because the actual UI includes the Update history panel while committed goldens are blank.

## Dependencies

- **Blocks:** [sase-ez.2](sase-ez.2.md) ✓
- **Blocks:** [sase-ez.3](sase-ez.3.md) ✓
- **Blocks:** [sase-ez.4](sase-ez.4.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ez.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ez.1/README.md) | [sase-ez.1](sase-ez.1.md) | 5 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f2cd75b`](https://github.com/sase-org/sase/commit/f2cd75bc55a1c6c786961572f4703605ae6d91a5) | revert(agent-names): remove historical identity migration | [sase-ez.1](sase-ez.1.md) | 2026-08-03 14:52:59 EDT |
| sase | [`850cb91`](https://github.com/sase-org/sase/commit/850cb910ee9f944e6c5871187581758cdba9c9d3) | revert(beads): remove historical reference rewriting | [sase-ez.1](sase-ez.1.md) | 2026-08-03 14:54:41 EDT |
| sase | [`e433d38`](https://github.com/sase-org/sase/commit/e433d388575fa71423dd6c15b3264e8a9572636b) | revert(beads): remove prefix migration facade | [sase-ez.1](sase-ez.1.md) | 2026-08-03 14:56:34 EDT |
| sase | [`234e817`](https://github.com/sase-org/sase/commit/234e8175cd28e7a3f040510f0c68a0f5fba1494b) | fix(lint): remove stale symvision state | [sase-ez.1](sase-ez.1.md) | 2026-08-03 15:03:28 EDT |
| sase | [`a35846f`](https://github.com/sase-org/sase/commit/a35846f4cf60ac0da274370698d16340a6c61791) | fix(beads): restore pre-alias resolution tests | [sase-ez.1](sase-ez.1.md) | 2026-08-03 15:15:18 EDT |
