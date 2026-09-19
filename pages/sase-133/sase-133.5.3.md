# Bead: sase-133.5.3 — Distinguish capability and fleet data versions

[Bead Pages](../README.md) / [sase-133.5](sase-133.5.md) / sase-133.5.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-133.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-133.land.md) · **Assignee:** `sase-133.5.3` · **Size:** medium
**Created:** 2026-09-19 08:06:12 EDT · **Closed:** 2026-09-19 10:39:04 EDT
**Plan:** [202609/remote\_parity\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_parity_landing_repairs.md)

## Description

version-diagnostics: replace the false capability-versus-fleet comparison with explicit fleet contract evidence and preserve genuine version-skew diagnostics.

## Notes

[2026-09-19T14:39:04Z · sase-133.5.3--2] Hello advertises optional fleet_contract_schema_version independently of capability schema v1; MachineStatus compares fleet-data versions so same-build 0.34.63 capability v1/fleet v4 has no skew, old hellos report unknown, and real fleet schema mismatch still warns. Verified: sase-core cargo test + rustfmt (monitor 5ac1vpc597fd), focused pytest 27/27 on tests/dispatch/test_machine_service.py and tests/main/test_parser_machine.py, then sase-core clippy + just check (monitor 9zqjsym9wnvh exit 0). No leftover --epic-symbol entries.

## Dependencies

- **Blocks:** [sase-133.5.4](sase-133.5.4.md) ◐ · ⧖ 2026-09-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-133.5.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-133.5.3.md) | [sase-133.5.3](sase-133.5.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ad0670d`](https://github.com/sase-org/sase/commit/ad0670d959f0379f2ce948030a5e21ce1f6950e2) | fix(dispatch): compare fleet-data versions instead of capability schema | [sase-133.5.3](sase-133.5.3.md) | 2026-09-19 10:41:47 EDT |
