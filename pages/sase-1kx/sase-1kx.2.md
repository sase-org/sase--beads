# Bead: sase-1kx.2 — Make the Full CI visual lane pass and stay clean

[Bead Pages](../README.md) / [sase-1kx](README.md) / sase-1kx.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.10b](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.10b.md) · **Assignee:** `sase-1kx.2` · **Size:** medium
**Created:** 2026-10-14 07:18:03 EDT
**Plan:** [202610/v0\_18\_0\_release.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_0_release.md)

## Description

visual-lane: fix the three deterministic visual failure classes (fast-startup stub vs real loader, remote rows seeded through the local loader, stale Commits description wait), regenerate only the goldens those fixes change, then prove a clean TZ=UTC full check.

## Notes

[2026-10-14T12:07:16Z · sase-1kx.2--1] PROPOSED FOLLOW-UP: Full TZ=UTC visual --check drifted 3 goldens outside Class A/B/C; 2 reproduce identically on clean HEAD 8e00f6d211 (agents_session_panel_turns_gate_90x40 14707px footer "(/) blocks" reflow — sase-1jz.3 gate-footer wait; link_rail_agents_single_link_60x30 1282px "$0 +1 more" vs "$$ implemented-by"); plan_gate_tale_decisions_maxcopy_120x40 truncation is intermittent (full run only, not targeted dirty or clean HEAD).

## Dependencies

- **Blocks:** [sase-1kx.4](sase-1kx.4.md) ◐ · ⧖ 2026-10-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1kx.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1kx.2.md) | [sase-1kx.2](sase-1kx.2.md) | 0 |
