# Bead: sase-p3.4 — Required-plugin project config and graded enforcement

[Bead Pages](../README.md) / [sase-p3](README.md) / sase-p3.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.05c](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.05c.md) · **Assignee:** `sase-p3.4` · **Size:** medium
**Created:** 2026-08-17 18:50:04 EDT · **Closed:** 2026-08-17 22:10:02 EDT
**Plan:** [202608/task\_bead\_types.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_bead_types.md)

## Description

plugins-required: add the `plugins.required` project config section, resolve it against installed distributions, cross-check it against `<plugin>@` prefixes, and enforce it differently per surface.

## Notes

[2026-08-18T02:10:02Z · sase-p3.4] Added plugins.required (schema + default_config + sase/sase.yml), resolver/cross-check against inventory, fail-closed helper, doctor plugins.required ERROR check, and hard errors in sase memory init / sase validate before memory drift. Verified: resolver unit tests; doctor/memory-init blockers; sase doctor -C plugins.required OK with sase-github and sase-research-artifacts installed; sase init memory --check clean; just check green (full-suite escalation from Justfile/schema). Fail-closed API is --epic-symbol'd for sase-p3.11. just install/_setup now installs plugins.required so this project's validate can fail closed.

[2026-08-18T02:11:14Z · sase-p3.4] Verified plugins.required schema/config, resolver (missing/mismatch/undeclared-prefix), doctor ERROR check, memory-init and validate fail-closed before drift, just install/_setup required-plugin install; epic-symbols clean for this phase.

## Dependencies

- **Blocks:** [sase-p3.11](sase-p3.11.md) ◐ · ⧖ 2026-08-17
- **Depends on:** [sase-p3.3](sase-p3.3.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-p3.5](sase-p3.5.md) ◐ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p3.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p3.4/README.md) | [sase-p3.4](sase-p3.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1e59c50`](https://github.com/sase-org/sase/commit/1e59c50e777002c9f573c78da43f7f09cdccddd7) | feat(plugins): add plugins.required config and fail-closed enforcement | [sase-p3.4](sase-p3.4.md) | 2026-08-17 22:12:55 EDT |
