# Bead: sase-x7.2.1.5 — Finish the migration kit's macOS rehearsal leg and publish its acceptance evidence

[Bead Pages](../README.md) / [sase-x7.2.1](sase-x7.2.1.md) / sase-x7.2.1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-x7.2.1.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-x7.2.1.land.md) · **Assignee:** `sase-x7.2.1.5.land`
**Created:** 2026-09-06 00:20:47 EDT · **Closed:** 2026-09-06 08:20:58 EDT
**Plan:** [202609/mac\_rehearsal\_leg.md](https://github.com/sase-org/sase--plans/blob/main/202609/mac_rehearsal_leg.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/mac_rehearsal_leg.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/mac_rehearsal_leg.md

<!-- sase:links:end -->

## Description

Complete the one outstanding leg of `kit-rehearsal` -- the macOS rehearsal and mac's deferred G3 probe -- then publish the per-host operation manifests for athena, mac, and apollo plus the rehearsal acceptance receipt as artifacts attached to `sase-x7.2.1.4`, so `sase-x7.2.1` can close on fleet-wide evidence instead of Linux-only evidence.

## Notes

[2026-09-06T12:20:58Z · sase-x7.2.1.5.land] LANDING VERIFIED 2026-09-06. Reviewed this epic, linked plan, both closed phase beads, and every child note. mac-leg acceptance is backed by the durable raw evidence, not only notes: STATUS outcome=ok at kit 16153bf56/core 0504155; isolated Darwin build exposed all nine migration bindings; pytest 71 passed/1 justified Darwin unshare skip; iCloud containment and live_untouched true; backup captured 316210 members/1542237643 bytes with four SQLite integrity checks ok and zero symlinks; import-purge planned 9894 artifacts/6501 chats/9924 bundles and applied+verified; procs/state were clean no-ops; lock-residue classified absent legacy code-swap.lock and refused current-writer code-swap-v2.lock apply as designed; restore dry-run/apply each verified all 316210 members with zero checksum/ownership failures and backup recheck found 0/255665 failures. Publish-evidence produced four exact, discoverable immutable artifacts attached to sase-x7.2.1.4: athena/mac/apollo manifests abd69e7c/7f8d1c21/d994f480 and receipt 4448c6ed; receipt has no DRAFT, covers Linux+Darwin, and each manifest names a secondary copy and disclaims rehearsal backups. There are no commits for this child epic/phases because both were operational evidence work. Reviewed every master commit since epic creation: d6705a16 test-only unrelated, 72fc7879/10d661c5 release metadata, and 1df2a780 migration driver module split. The split preserves the public driver surface and tests; current tree passes the 72-test kit lane, tools/check_sase_core_rs_bindings under the project runtime reports 419 bindings at 0.32.25, probe_core_floor is silent, and sase migrate list returns exactly four operations. No integration edits required. Follow-ups: (1) mac AXE DEGRADED/UNHEALTHY with live stale-heartbeat children and 0/3 runners became ready bug task sase-xd with evidence file:explicit:e3bb4b2a1e2da5cbc7fe3f99, related but not duplicate to sase-wd; (2) mac/apollo live core 0.32.23 is already a hard local-state-cutover precondition, recorded on active phase sase-x7.6, so no duplicate task; (3) mac completion stamps hard-code Linux /home/bryan targets in canonical chezmoi source, recorded on active canonical-producers phase sase-x7.3, so no standalone task. Root epic sase-x7 received the routing summary. sase bead epic-symbols is clean for the epic and both phases.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-x7.2.1.5.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-x7.2.1.5.land.md) | [sase-x7.2.1.5](sase-x7.2.1.5.md) | 0 |
