# Bead: sase-yz.3 — Collector health in the usage CLI and doctor

[Bead Pages](../README.md) / [sase-yz](README.md) / sase-yz.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0hd.f1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0hd.f1.md) · **Assignee:** `sase-yz.3` · **Size:** small
**Created:** 2026-09-09 12:39:16 EDT · **Closed:** 2026-09-09 15:45:31 EDT
**Plan:** [202609/usage\_collector\_health\_and\_drift\_resilience.md](https://github.com/sase-org/sase--plans/blob/main/202609/usage_collector_health_and_drift_resilience.md)

## Description

health-cli: render collector health in sase usage list status cells and verbose records, pass it through --json, add shared pure health label/style helpers, and flag consistently failing collectors in sase doctor.

## Notes

[2026-09-09T19:45:31Z · sase-yz.3] Implemented CLI/doctor collector health presentation; verified focused pytest for usage presentation, usage command, and provider doctor checks; ran just _lint-symvision and just check successfully.

## Dependencies

- **Depends on:** [sase-yz.1](sase-yz.1.md) ✓ · ⧖ 2026-09-09
- **Blocks:** [sase-yz.4](sase-yz.4.md) ✓ · ⧖ 2026-09-09
- **Blocks:** [sase-yz.5](sase-yz.5.md) ✓ · ⧖ 2026-09-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-yz.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-yz.3/README.md) | [sase-yz.3](sase-yz.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0879bfe`](https://github.com/sase-org/sase/commit/0879bfe5fddb08db00fb7ce1b117979286909ee9) | feat(usage): show collector health in CLI and doctor | [sase-yz.3](sase-yz.3.md) | 2026-09-09 15:47:07 EDT |
