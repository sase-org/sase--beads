# Bead: sase-1no.1 — Stranded-work reducer in sase-core

[Bead Pages](../README.md) / [sase-1no](README.md) / sase-1no.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.13e](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.13e.md) · **Assignee:** `sase-1no.1` · **Size:** medium
**Created:** 2026-10-23 14:22:48 EDT · **Closed:** 2026-10-23 15:02:27 EDT
**Plan:** [202610/stranded\_epic\_work.md](https://github.com/sase-org/sase--plans/blob/main/202610/stranded_epic_work.md)

## Description

core: add the pure Rust reducer that maps bead and session-member facts to owned/delegated/settling/stranded/blocked/unknown verdicts. It includes causes, ancestor propagation, wires, unit tests, and the `stranded_work_reduce` PyO3 binding.

## Notes

[2026-10-23T19:02:27Z · sase-1no.1] core: stranded_work reducer + stranded_work_reduce binding land in sase-core. Verified: 24 reducer unit tests + 2 binding round-trip/by-name tests pass; sase tool run check (full gate incl. clippy -D warnings, fmt, script tests) succeeded exit=0.

## Dependencies

- **Blocks:** [sase-1no.2](sase-1no.2.md) ◐ · ⧖ 2026-10-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1no.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1no.1/README.md) | [sase-1no.1](sase-1no.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@58aca5f`](https://github.com/sase-org/sase-core/commit/58aca5fe69158286092e3a33685687a52f8d2b8f) | feat(stranded-work): add pure facts-to-verdicts reducer with PyO3 binding | [sase-1no.1](sase-1no.1.md) | 2026-10-23 15:03:40 EDT |
