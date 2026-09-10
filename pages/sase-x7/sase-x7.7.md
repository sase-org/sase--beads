# Bead: sase-x7.7 — Deploy Telegram and retire the second store

[Bead Pages](../README.md) / [sase-x7](README.md) / sase-x7.7

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0gk](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0gk.md) · **Assignee:** `sase-x7.7` · **Size:** medium
**Created:** 2026-09-05 18:55:32 EDT
**Plan:** [202609/canonical\_only\_fleet\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/canonical_only_fleet_cutover.md)

## Description

telegram-cutover: Deploy the verified host/core/plugin cohort in mac, athena, apollo order, reconcile existing pending actions without losing approvals, restart every Telegram writer, and observe at least the 24-hour stale-action interval with no retired-store writes before archiving the old store.

## Notes

[2026-09-10T09:51:19Z · sase-x7.7] STATUS CHECK 2026-09-10: telegram-bridge (sase-x7.4) is fully landed and released as
sase-telegram 0.4.10 (host e0c575503 exposes the Rust-backed shared pending-action
transport API; Telegram repo release commit 006f015). Verified live fleet state
read-only, no production data mutated:

- athena (this host): uv-tool venv has sase (0.17.1), sase-core-rs 0.32.61, sase-telegram
  0.4.10. The live `sase axe lumberjack run telegram` worker (PID 2912404) started
  2026-09-09 18:07:23, i.e. 38s after the 0.4.10 dist-info install (18:06:45) -- confirms
  it is actually running the new merge-aware code, not just an upgraded-on-disk package.
  Legacy store ~/.sase/telegram/pending_actions.json last modified 2026-09-07 23:40 (13
  entries, all created 2026-09-07 08:52-20:46: 11 TaskTriage, 1 PlanApproval, 1
  CustomGate, 1 BeadStaleCleanup) -- no legacy writes since. Live read-time merge
  (`read_pending_action_store(include_legacy=True)`) sees 3,243 merged actions (2,978
  already_handled / 265 available); nothing is orphaned -- the shipped design merges the
  legacy store transparently on every read rather than doing a batch one-shot
  conversion, so existing legacy callbacks stay reachable/actionable without a separate
  migration write.
- apollo (SSH alias, reachable): uv-tool venv has sase-telegram 0.4.10 too; live
  `telegram` lumberjack worker (PID 862154) started 2026-09-09 18:04:33, package
  installed 2026-09-08 12:37:14 -- also confirmed restarted onto new code. Legacy store
  last modified 2026-09-05 20:51, no writes since. Merge view: 212 merged actions (108
  already_handled / 104 available).
- mac (SSH/Tailscale alias `kellys-macbook-pro`): OFFLINE -- `ssh mac` timed out and
  `tailscale status` confirms it, last seen ~18 min before this check. Cannot verify or
  restart its Telegram writer, and the phase's required deploy order is explicitly
  "mac, athena, apollo" (mac first). Its current package/process state is unknown.

Given mac is unreachable, the fleet-wide "restart every Telegram writer" and "no
retired-store writes for >=24h across all hosts" acceptance criteria cannot be certified
right now, and per this project's single-turn-agent rule this turn cannot sleep 24h to
observe the window even once mac is back. No deployment, restart, reconciliation write,
or store archival was performed this turn -- athena and apollo already appear correctly
deployed (likely from earlier x7.4 release-day updates), so the remaining concrete work
is: bring mac online, deploy/verify its cohort, restart its Telegram writer, then run the
>=24h no-legacy-write observation across all three hosts before archiving the old stores.
sase bead epic-symbols sase-x7.7 has no entries. Leaving phase in_progress; not closing.

## Dependencies

- **Depends on:** [sase-x7.4](sase-x7.4.md) ✓ · ⧖ 2026-09-05
- **Depends on:** [sase-x7.6](sase-x7.6.md) ✓ · ⧖ 2026-09-05
- **Blocks:** [sase-x7.8](sase-x7.8.md) ◐ · ⧖ 2026-09-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-x7.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-x7.7/README.md) | [sase-x7.7](sase-x7.7.md) | 0 |
