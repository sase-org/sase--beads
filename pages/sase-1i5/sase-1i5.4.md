# Bead: sase-1i5.4 — Isolate tests from the live bead store and long basetemps (sase-14o, sase-18v)

[Bead Pages](../README.md) / [sase-1i5](README.md) / sase-1i5.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0y8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0y8.md) · **Assignee:** `sase-1i5.4` · **Size:** small
**Created:** 2026-10-08 09:47:19 EDT · **Closed:** 2026-10-08 10:18:43 EDT
**Plan:** [202610/close\_top\_ten\_impact\_task\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202610/close_top_ten_impact_task_beads.md)

## Description

test-host-leaks: isolate the bead and plan resolvers in the absent-store and plan-candidate tests, make the three Rich path assertions basetemp-independent, and close sase-14o and sase-18v.

## Notes

[2026-10-08T14:17:47Z · sase-1i5.4] PROPOSED FOLLOW-UP: just check symvision gate fails identically on clean base (byte-identical output, exit 1) — unused-public-symbols findings in scope_sweep, instructions, amd, etc., untouched by this phase; needs triage as its own task bead -r recording pre-existing check failure found during phase verification

[2026-10-08T14:18:43Z · sase-1i5.4] test-host-leaks done. sase-14o: patched the resolvers themselves (_find_existing_beads_dir and catalog_sdd._resolve_beads_dir to None; fake .git root bounds the plan-candidate repo walk). sase-18v: path-sized test consoles for the snippet rich tables, wrap-normalized full-path assertion for restart. Verified: all 6 nodes pass raw pytest on live-store host, pass under 210-char basetemp, 68 passed across the 6 containing files; sase tool run check fmt/ruff/mypy pass, symvision fails byte-identically on clean base (pre-existing, filed as PROPOSED FOLLOW-UP). Closed sase-14o and sase-18v done; epic-symbols clean.

## Dependencies

- **Blocks:** [sase-1i5.9](sase-1i5.9.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1i5.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1i5.4/README.md) | [sase-1i5.4](sase-1i5.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bb8673e`](https://github.com/sase-org/sase/commit/bb8673ea7c29686a747861a2c2f6c19f5939459a) | test(fix): isolate store resolution and basetemp-independent rich assertions | [sase-1i5.4](sase-1i5.4.md) | 2026-10-08 10:20:29 EDT |
