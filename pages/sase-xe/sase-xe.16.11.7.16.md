# Bead: sase-xe.16.11.7.16 — Fleet ghost rows — finish live acceptance, fix v1 read-compat, make broken feeds honest

[Bead Pages](../README.md) / [sase-xe.16.11.7](sase-xe.16.11.7.md) / sase-xe.16.11.7.16

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.01](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.01.md) · **Assignee:** `sase-xe.16.11.7.16.land`
**Created:** 2026-09-14 16:25:27 EDT · **Closed:** 2026-09-15 17:23:46 EDT
**Plan:** [202609/fleet\_ghost\_rows\_readcompat.md](https://github.com/sase-org/sase--plans/blob/main/202609/fleet_ghost_rows_readcompat.md)

## Description

Athena's ACE never silently renders stale ghost agents for a remote host: the sase-xe.16.11.7.15 live-acceptance phase is completed and closed on today's verified-live fleet view, capability-set validation honors the contract's claimed v1 read-compatibility so mixed-version hosts do not collapse to zero rows behind a hello-ok status, and a host whose feed is invalid or stale is rendered loudly (host-level error surfacing plus honest staleness chrome on every cached row) instead of masquerading as healthy.

## Notes

[2026-09-15T21:23:46Z · sase-xe.16.11.7.16.5.5.land] Rechecked all four phases, their notes, linked plan, and closed repair child sase-xe.16.11.7.16.5. Phase .2 is present in core commit 4426269 with content-normalization validation that accepts readable v1/v2 capability schemas; phase .3 is present in 0b1a480 with invalid/stale feed surfacing; phase .4's initial service_versions implementation in 801e985 was correctly strengthened by child commits bdb6772/d0975c7 to publish and consume the real optional gateway_version contract. The child also added owner-side terminal family-member suppression and logical display fallback, and durable live artifact file:explicit:18f0b0d3403c5270751a6179 proves the formerly failing Athena-to-Apollo acceptance; .1 and target phase sase-xe.16.11.7.15.7 are now normally closed. Reviewed post-child drift: machine-init candidate persistence and remote-dispatch docs are orthogonal, the public ace-to-tui rename is reflected by the current installed build used for acceptance, settlement/update TUI changes do not touch fleet projection, and later sudo machine-model changes precede and are integrated beneath d0975c7. Current focused verification passed (72 Python tests plus Rust presentation/contract/gateway suites). No direct-phase PROPOSED FOLLOW-UP entries remain; child follow-ups were dispositioned when closing .16.5. No epic-symbol entries remain.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-xe.16.11.7.16.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-xe.16.11.7.16.land.md) | [sase-xe.16.11.7.16](sase-xe.16.11.7.16.md) | 0 |
