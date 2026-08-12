# Bead: sase-jx.5.1 — Repair the classifier's timestamp and per-run contract

[Bead Pages](../README.md) / [sase-jx.5](sase-jx.5.md) / sase-jx.5.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-jx.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-jx.land/README.md) · **Assignee:** `sase-jx.5.1` · **Size:** medium
**Created:** 2026-08-12 12:14:23 EDT
**Plan:** [202608/land\_axe\_chop\_overrun.md](https://github.com/sase-org/sase--plans/blob/main/202608/land_axe_chop_overrun.md)

## Description

repair_core_contract: in sase-core, reject every run whose started_at is unparsable and extend the versioned verdict so Python can associate an overrun ratio with each raw cached run, then verify and publish the corrected binding without hand-editing release-plz-owned versions.

## Dependencies

- **Blocks:** [sase-jx.5.2](sase-jx.5.2.md) ◐ · ⧖ 2026-08-12
- **Blocks:** [sase-jx.5.3](sase-jx.5.3.md) ◐ · ⧖ 2026-08-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-jx.5.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-jx.5.1/README.md) | [sase-jx.5.1](sase-jx.5.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@46ce1fe`](https://github.com/sase-org/sase-core/commit/46ce1fe9f1696f869007107114502b1b27f24bf6) | fix(axe\_overrun): validate started\_at unconditionally and align per-run ratios | [sase-jx.5.1](sase-jx.5.1.md) | 2026-08-12 12:29:09 EDT |
