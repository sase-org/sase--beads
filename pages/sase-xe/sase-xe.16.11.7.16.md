# Bead: sase-xe.16.11.7.16 — Fleet ghost rows — finish live acceptance, fix v1 read-compat, make broken feeds honest

[Bead Pages](../README.md) / [sase-xe.16.11.7](sase-xe.16.11.7.md) / sase-xe.16.11.7.16

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.01](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.01.md) · **Assignee:** `sase-xe.16.11.7.16.land`
**Created:** 2026-09-14 16:25:27 EDT
**Plan:** [202609/fleet\_ghost\_rows\_readcompat.md](https://github.com/sase-org/sase--plans/blob/main/202609/fleet_ghost_rows_readcompat.md)

## Description

Athena's ACE never silently renders stale ghost agents for a remote host: the sase-xe.16.11.7.15 live-acceptance phase is completed and closed on today's verified-live fleet view, capability-set validation honors the contract's claimed v1 read-compatibility so mixed-version hosts do not collapse to zero rows behind a hello-ok status, and a host whose feed is invalid or stale is rendered loudly (host-level error surfacing plus honest staleness chrome on every cached row) instead of masquerading as healthy.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-xe.16.11.7.16.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-xe.16.11.7.16.land/README.md) | [sase-xe.16.11.7.16](sase-xe.16.11.7.16.md) | 0 |
