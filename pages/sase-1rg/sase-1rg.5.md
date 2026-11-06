# Bead: sase-1rg.5 — Release leaked and dead claims in stale-running cleanup

[Bead Pages](../README.md) / [sase-1rg](README.md) / sase-1rg.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.cp--5` · **Assignee:** `sase-1rg.5` · **Size:** medium
**Created:** 2026-11-06 05:46:50 EST · **Closed:** 2026-11-06 08:14:59 EST
**Plan:** [202611/agent\_health\_watch\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_health_watch_fixes.md)

## Description

stale-claims: re-settle already-leaked epic-launch monitor claims with the corrected scope after publishing their stray decision sheets, and apply the held-claim TTL to dead gate claims stuck in a non-terminal state.

## Notes

[2026-11-06T13:14:59Z · sase-1rg.5] Implemented stale-claims repair in cleanup_stale_running_entries: leaked epic-launch monitor claims publish stray decision sheets via the SDD plans-store commit API then re-settle with corrected scope (release when clean, retain with working notification otherwise); dead non-terminal gate claims release past held_claim_ttl_days with the gate record untouched. Verified: 4 new tests (leaked publish+release, real-dirt retain+plus-one notification, gate TTL release with untouched record, TTL-disabled keep) plus updated gate keep test; focused suites 36+26+33 pass; sase tool run check exit=0 (all lints incl. symvision, 235 scoped files).

## Dependencies

- **Depends on:** [sase-1rg.3](sase-1rg.3.md) ✓ · ⧖ 2026-11-06
- **Depends on:** [sase-1rg.4](sase-1rg.4.md) ✓ · ⧖ 2026-11-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rg.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rg.5/README.md) | [sase-1rg.5](sase-1rg.5.md) | 0 |
