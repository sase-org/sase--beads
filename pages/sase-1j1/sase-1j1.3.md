# Bead: sase-1j1.3 — Federation worker keeps host state and backs off slow hosts

[Bead Pages](../README.md) / [sase-1j1](README.md) / sase-1j1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0yx](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0yx.md) · **Assignee:** `sase-1j1.3` · **Size:** medium
**Created:** 2026-10-09 09:31:12 EDT · **Closed:** 2026-10-09 10:15:34 EDT
**Plan:** [202610/apollo\_gateway\_snapshot\_stampede.md](https://github.com/sase-org/sase--plans/blob/main/202610/apollo_gateway_snapshot_stampede.md)

## Description

worker-host-backoff: in the sase-core federation worker, reuse unchanged RemoteHost instances across replace_config. That keeps the HTTP client, hello verification, per-host permits and back-off state alive across TUI refreshes. Add exponential per-host back-off that serves cached data instead of calling a host that just timed out or failed.

## Notes

[2026-10-09T14:15:21Z · sase-1j1.3] PROPOSED FOLLOW-UP: full sase-core check hit sudo_runner ETXTBSY flake (command_literal_chdir_flag_after_boundary_is_allowed, Text file busy under parallel load); passes alone with this phase compiled in; already tracked by sase-15h

[2026-10-09T14:15:34Z · sase-1j1.3] Federation worker reuses unchanged RemoteHost across replace_config and backs off slow hosts. Verified: just test -p sase_gateway federation 20/20 pass incl 4 new tests (host reuse pointer-equality, backoff schedule, retryable classification, end-to-end backoff serving stale cache with no HTTP request, window expiry, success reset, catalog short-circuit, launch/mutate bypass); just fast clean; sase tool run check clippy clean, full suite 234 pass with 1 unrelated sudo_runner ETXTBSY load flake that passes alone and is tracked by sase-15h.

## Dependencies

- **Blocks:** [sase-1j1.6](sase-1j1.6.md) ◐ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1j1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1j1.3/README.md) | [sase-1j1.3](sase-1j1.3.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1j1.3][1] | check prior notes and full scope | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1j1.3/README.md

<!-- sase:referenced-by:end -->
