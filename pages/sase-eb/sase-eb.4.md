# Bead: sase-eb.4 — CLI wiring, help, and documentation

[Bead Pages](../README.md) / [sase-eb](README.md) / sase-eb.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.s3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.s3/README.md) · **Assignee:** `sase-eb.4` · **Size:** small
**Created:** 2026-08-02 15:50:26 UTC · **Closed:** 2026-08-02 18:05:33 UTC
**Plan:** [202608/xprompt\_show.md](https://github.com/sase-org/sase--plans/blob/main/202608/xprompt_show.md)

## Description

cli: register the `show` subparser with its flags and examples, dispatch it from the xprompt handler, document the command in the three docs surfaces, and retire the epic symvision whitelist entries.

## Notes

[2026-08-02T18:05:33Z · sase-eb.4] Verified parser/handler/show rendering tests, just _lint-symvision without sase-eb exemptions, manual xprompt show color/raw checks across project/config/built-in/skill/workflow entries, and full just check.

## Dependencies

- **Depends on:** [sase-eb.3](sase-eb.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-eb.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-eb.4/README.md) | [sase-eb.4](sase-eb.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`c8211ae`](https://github.com/sase-org/sase/commit/c8211ae5cf3e08f0c3d4402ee5b6bdfe6617a0e0) | feat(xprompt): add show CLI command | [sase-eb.4](sase-eb.4.md) | 2026-08-02 18:07:24 |
