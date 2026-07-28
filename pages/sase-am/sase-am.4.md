# Bead: sase-am.4 — Derive the CI sidecar environment from configuration

[Bead Pages](../README.md) / [sase-am](README.md) / sase-am.4

**Status:** ◎ claimed · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-am.4` · **Size:** small
**Created:** 2026-07-28 22:06:02 UTC
**Plan:** [202607/ci\_flakiness\_redesign.md](https://github.com/sase-org/sase--plans/blob/main/202607/ci_flakiness_redesign.md)

## Description

config-driven-sidecars: replace the hand-written sidecar checkouts and sdd-store heredoc with a tools/ci_bootstrap_sidecars script generated from sase/sase.yml, with unit tests locking the store shape.

## Dependencies

- **Depends on:** [sase-am.3](sase-am.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-am.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-am.4/README.md) | [sase-am.4](sase-am.4.md) | 0 |
