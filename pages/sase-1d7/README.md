# Bead: sase-1d7 — Make unread acks stick and keep the Agents TUI responsive

[Bead Pages](../README.md) / sase-1d7

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0uc](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0uc.md) · **Assignee:** `sase-1d7.land`
**Created:** 2026-09-30 07:18:05 EDT · **Closed:** 2026-09-30 20:33:15 EDT
**Plan:** [202609/unread\_ack\_reliability\_and\_tui\_responsiveness.md](https://github.com/sase-org/sase--plans/blob/main/202609/unread_ack_reliability_and_tui_responsiveness.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | [bead:sase-1ds][1] | Epic whose ack pipeline (_unread_ack_writer, ack_agent_completions) this dismiss path should reuse |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-1ds/README.md

<!-- sase:links:end -->

## Description

Unread acknowledgments (`,u`, `,j`/`,J`, row-select) are never reverted by another notification-store writer or by an older snapshot, and unread actions paint within budget: no UI-thread store reads, no full Agents rebuilds for unread-only changes, and no multi-second main-loop freezes from the 1 Hz runtime tick or fleet reprojection.

## Notes

[2026-09-30T20:30:34Z · sase-1d5.land] DISCOVERED ISSUE (sase-1d5.land, 2026-09-30, master 7885562f54 + sase-1d5 landing fix): just symvision reports 3 unused public symbols from 9f989395b5 (feat(agents): cheap unread jumps and footer probe, sase-1d7.9) in src/sase/ace/tui/actions/agents/_unread_set_generation.py: get_unread_set_generation, has_unread_probe_cache_key, note_unread_set_changed. They were hidden until now because symvision stops at its first error category and the sase-1d5 private-import error (fixed in the sase-1d5 landing) masked the unused-public stage. sase tool run check run 10ad13d1995cb9191a95794c3ae6a615 labels them NEW with no owner. Resolve (privatize, wire a real consumer, or re-key an --epic-symbol to a still-open 1d7 phase such as sase-1d7.12/13 if they are about to consume them) before this epic closes.

[2026-09-30T23:59:25Z · sase-1d7.land] LAND TRIAGE (sase-1d7.land, 2026-09-30, master 788a9311f8) of every child PROPOSED FOLLOW-UP: (1) validate_sase_core_rs prompt-prediction probe skew (1d7.2/.4/.5/.6/.7/.8/.11) DECLINED: resolved on master, just symvision's _setup (which runs the validator) passes at 788a9311f8. (2) symvision _kitty_graphics_support private import (1d7.3) DECLINED: resolved, absent from current symvision output. (3) terminology audit at_bearing_notes fixture (1d7.3) DECLINED: duplicate of closed/fixed sase-1cv. (4) get_roster_generation unused (1d7.5) DECLINED: now consumed by _agent_wait_cache and _fleet_projection. (5) tab-strip PNG goldens timeout (1d7.7) -> CREATED flake sase-1dt. (6) import budget 3493/3499 (1d7.9/.12) -> +1 sase-13p (3501 at HEAD; the epic's own 2 startup modules are deferred by this landing). (7) test_runtime_tick_skipped_in_rail (1d7.9/.12) NOT a follow-up: caused by this epic's change-only runtime tick (1d7.10); fixed as remaining epic work. (8) force_reuse launch-seam origin + artifact/config/completion contract nodes (1d7.9) DECLINED: tracked by sase-18s/sase-1cm and sase-1de. (9) symvision private imports from e1f10caa (1d7.9) DECLINED: fixed by the sase-1d5 landing 60b2d3dfdb. (10) full check over 10 min (1d7.10) DECLINED: environmental, lint_and_test.md already routes long checks via monitor. (11) feature-flags rule 7 sase-1dg (1d7.12) DECLINED: resolved, sase-1dg closed and no public_bead_attachments left in src. (12) test_agent_header_panel ImportError (1d7.12/.13) -> +1 sase-1dh (caused by c6b802a647, not this epic). (13) test_empty_panel_semicolon parallel flake (1d7.12) -> +1 sase-1al. (14) test_launch_query_wipe_failure_records_and_emits parallel flake (1d7.13) -> CREATED flake sase-1du. Land-agent findings not caused by the epic: explicit agent dismiss still does synchronous store write + full read on the UI thread (deliberately deferred by the 1d7.12 phase plan) -> CREATED bug sase-1ds; tool symvision symbols HandoffSubmitResult/StarterResolution/owner_ref -> +1 sase-1dn. Epic note #1 (3 unused public symbols in _unread_set_generation.py) is epic work, resolved in the remaining-work tale.

[2026-10-01T00:33:15Z · sase-1d7.land] sase-1d7 landing (remaining work): all 13 phases verified against the epic plan and code; follow-up triage recorded in LAND TRIAGE note; lean-index decision kept (read_unread_completion_index scoped to callers without snapshot + parity test). Fixes: (1) privatized get_unread_set_generation/has_unread_probe_cache_key, deleted note_unread_set_changed alias; symvision now shows only non-1d7 symbols (sase-1dn tool trio + next-word ghost). (2) rail runtime-tick test uses advancing local_now clock (change-only tick). (3) deferred _unread_bulk_scope/_unread_set_generation off TUI startup (3499 modules, neither in sys.modules). (4) fleet skip path rebuilds only rendered-changed panels via _refresh_affected_panel_widgets with header-only fast path + selected-diagnostic info/detail refresh; new skip_repaint tests 2/2 pass; idle bench fleet_refresh_unchanged p50 0.105ms (near 0.05ms baseline, 170x below forced 18.4ms). (5) retention docs 14d->3d in axe.md/notifications.md/default_config.yml. (6) off-tab ,u now closes perf sample (new test), removed legacy TypeError retry in ack writer, chrome_apply counts rebuilds only when run + patch_failed counter. (7) dead code removed (navigation early-return, bulk-undo dup, snapshot version, stale comments, jump predicate dedup, perf runbook filter). Focused suites green: 59 (rail/fleet/roster/tick/chrome/fence/undo) + 174 (unread/leader) + 62 (leader/chrome/pipeline/spans). Full just check runs as the final verification gate.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1d7.1](sase-1d7.1.md) | Remote-attention reconciler writes only the rows it changed | ✓ closed | small | 2026-09-30 | 1 | 1 |
| [sase-1d7.10](sase-1d7.10.md) | Cached wait-status maps and change-only runtime patching | ✓ closed | medium | 2026-09-30 | 1 | 1 |
| [sase-1d7.11](sase-1d7.11.md) | Cheap fleet reprojection signature computed before projection | ✓ closed | medium | 2026-09-30 | 1 | 1 |
| [sase-1d7.12](sase-1d7.12.md) | Rust ack API, lean unread index, and store generations | ✓ closed | large | 2026-09-30 | 1 | 2 |
| [sase-1d7.13](sase-1d7.13.md) | Notification store retention and wait-check payload diet | ✓ closed | large | 2026-09-30 | 1 | 2 |
| [sase-1d7.2](sase-1d7.2.md) | Atomic field-scoped reconcile write in sase-core | ✓ closed | medium | 2026-09-30 | 1 | 2 |
| [sase-1d7.3](sase-1d7.3.md) | Trace spans, leader-key perf capture, and unread/idle benches | ✓ closed | small | 2026-09-30 | 1 | 1 |
| [sase-1d7.4](sase-1d7.4.md) | Roster generation counter and cached projection index | ✓ closed | medium | 2026-09-30 | 1 | 1 |
| [sase-1d7.5](sase-1d7.5.md) | Sequence-fenced pending-ack overlay and monotonic snapshot cache | ✓ closed | medium | 2026-09-30 | 1 | 1 |
| [sase-1d7.6](sase-1d7.6.md) | One batched unread chrome helper with no full rebuilds | ✓ closed | medium | 2026-09-30 | 1 | 1 |
| [sase-1d7.7](sase-1d7.7.md) | Precise bulk-ack scope and a time-bound explicit undo | ✓ closed | small | 2026-09-30 | 1 | 1 |
| [sase-1d7.8](sase-1d7.8.md) | Read-free ack completion and a coalescing ack writer | ✓ closed | medium | 2026-09-30 | 1 | 1 |
| [sase-1d7.9](sase-1d7.9.md) | Cheap unread jumps and footer probe | ✓ closed | medium | 2026-09-30 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1d7: Make unread acks stick and keep the Agents TUI responsive [closed]"]
    n1["sase-1d7.1: Remote-attention reconciler writes only the rows it changed [closed]"]
    n2["sase-1d7.10: Cached wait-status maps and change-only runtime patching [closed]"]
    n3["sase-1d7.11: Cheap fleet reprojection signature computed before projection [closed]"]
    n4["sase-1d7.12: Rust ack API, lean unread index, and store generations [closed]"]
    n5["sase-1d7.13: Notification store retention and wait-check payload diet [closed]"]
    n6["sase-1d7.2: Atomic field-scoped reconcile write in sase-core [closed]"]
    n7["sase-1d7.3: Trace spans, leader-key perf capture, and unread/idle benches [closed]"]
    n8["sase-1d7.4: Roster generation counter and cached projection index [closed]"]
    n9["sase-1d7.5: Sequence-fenced pending-ack overlay and monotonic snapshot cache [closed]"]
    n10["sase-1d7.6: One batched unread chrome helper with no full rebuilds [closed]"]
    n11["sase-1d7.7: Precise bulk-ack scope and a time-bound explicit undo [closed]"]
    n12["sase-1d7.8: Read-free ack completion and a coalescing ack writer [closed]"]
    n13["sase-1d7.9: Cheap unread jumps and footer probe [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n0 --> n9
    n0 --> n10
    n0 --> n11
    n0 --> n12
    n0 --> n13
    n1 -.-> n6
    n4 -.-> n5
    n6 -.-> n4
    n6 -.-> n5
    n7 -.-> n2
    n7 -.-> n3
    n7 -.-> n8
    n8 -.-> n2
    n8 -.-> n3
    n8 -.-> n9
    n8 -.-> n13
    n9 -.-> n4
    n9 -.-> n10
    n9 -.-> n12
    n10 -.-> n11
    n10 -.-> n12
    n10 -.-> n13
    n11 -.-> n12
    n12 -.-> n4
    n12 -.-> n13
    n13 -.-> n4
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1d7.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1d7.1.md) | [sase-1d7.1](sase-1d7.1.md) | 1 |
| [bbugyi200.athena.sase-1d7.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1d7.10/README.md) | [sase-1d7.10](sase-1d7.10.md) | 1 |
| [bbugyi200.athena.sase-1d7.11](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1d7.11.md) | [sase-1d7.11](sase-1d7.11.md) | 1 |
| [bbugyi200.athena.sase-1d7.12](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1d7.12.md) | [sase-1d7.12](sase-1d7.12.md) | 2 |
| [bbugyi200.athena.sase-1d7.13](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1d7.13.md) | [sase-1d7.13](sase-1d7.13.md) | 2 |
| [bbugyi200.athena.sase-1d7.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1d7.2.md) | [sase-1d7.2](sase-1d7.2.md) | 2 |
| [bbugyi200.athena.sase-1d7.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1d7.3/README.md) | [sase-1d7.3](sase-1d7.3.md) | 1 |
| [bbugyi200.athena.sase-1d7.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1d7.4.md) | [sase-1d7.4](sase-1d7.4.md) | 1 |
| [bbugyi200.athena.sase-1d7.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1d7.5.md) | [sase-1d7.5](sase-1d7.5.md) | 1 |
| [bbugyi200.athena.sase-1d7.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1d7.6/README.md) | [sase-1d7.6](sase-1d7.6.md) | 1 |
| [bbugyi200.athena.sase-1d7.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1d7.7/README.md) | [sase-1d7.7](sase-1d7.7.md) | 1 |
| [bbugyi200.athena.sase-1d7.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1d7.8.md) | [sase-1d7.8](sase-1d7.8.md) | 1 |
| [bbugyi200.athena.sase-1d7.9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1d7.9.md) | [sase-1d7.9](sase-1d7.9.md) | 1 |
| [bbugyi200.athena.sase-1d7.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1d7.land.md) | [sase-1d7](README.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`279bc27`](https://github.com/sase-org/sase/commit/279bc272d17165ec8f2e44c24760a49c5954c852) | fix(dispatch): preserve concurrent dismissals in remote attention inbox reconcile | [sase-1d7.1](sase-1d7.1.md) | 2026-09-30 08:17:41 EDT |
| sase | [`d6f2b23`](https://github.com/sase-org/sase/commit/d6f2b237a6a48b5290d7356dfeb0c63f62b14a58) | feat(tui): instrument unread paths with tui\_trace spans and key-to-paint benches | [sase-1d7.3](sase-1d7.3.md) | 2026-09-30 08:27:08 EDT |
| sase-core | [`sase-core@413511f`](https://github.com/sase-org/sase-core/commit/413511fcc93a7a17dfc38957dcde983bea6ca8df) | feat(notifications): lock-held field-scoped reconcile write plus empty raw\_suffix matcher parity | [sase-1d7.2](sase-1d7.2.md) | 2026-09-30 09:47:54 EDT |
| sase | [`4ae3b32`](https://github.com/sase-org/sase/commit/4ae3b32f5cb7e43240c68a9537010055f455bcde) | feat(notifications): field-scoped reconcile write in sase-core with attention reconciler switch | [sase-1d7.2](sase-1d7.2.md) | 2026-09-30 10:04:00 EDT |
| sase | [`8a00076`](https://github.com/sase-org/sase/commit/8a00076f1ffa374e9d604ea9f66a4b1881906843) | feat(agents): add roster generation counter and cached projection index | [sase-1d7.4](sase-1d7.4.md) | 2026-09-30 10:12:01 EDT |
| sase | [`11ba54b`](https://github.com/sase-org/sase/commit/11ba54b3816412c082c2ca9ba93ad672247782a0) | feat(agents): cache wait-status maps and change-only runtime patching | [sase-1d7.10](sase-1d7.10.md) | 2026-09-30 11:08:32 EDT |
| sase | [`63c7eb5`](https://github.com/sase-org/sase/commit/63c7eb57e2aef04349519c39e8d5db37a7468a02) | feat(agents): sequence-fenced pending-ack overlay and monotonic snapshot cache | [sase-1d7.5](sase-1d7.5.md) | 2026-09-30 11:12:34 EDT |
| sase | [`2fade65`](https://github.com/sase-org/sase/commit/2fade653babb1adf2deeb637c6b66cec392c4786) | feat(agents): cheap fleet reprojection signature checked before projection | [sase-1d7.11](sase-1d7.11.md) | 2026-09-30 11:49:38 EDT |
| sase | [`30a04f9`](https://github.com/sase-org/sase/commit/30a04f9a31beb60da60f808611f680f045e1733e) | feat(agents): one batched unread chrome helper with no full rebuilds | [sase-1d7.6](sase-1d7.6.md) | 2026-09-30 11:59:48 EDT |
| sase | [`af0ac9d`](https://github.com/sase-org/sase/commit/af0ac9d6acf9852276c6af6ccae220cb61ec10c6) | feat(agents): precise bulk-ack scope and time-bound explicit undo (sase-1d7.7) | [sase-1d7.7](sase-1d7.7.md) | 2026-09-30 12:40:22 EDT |
| sase | [`f57024d`](https://github.com/sase-org/sase/commit/f57024dbdc98e0c481e6eabda3d01e217e21d314) | feat(agents): unread ack pipeline with coalescing writer and cached-snapshot completion | [sase-1d7.8](sase-1d7.8.md) | 2026-09-30 13:35:00 EDT |
| sase | [`9f98939`](https://github.com/sase-org/sase/commit/9f989395b5f158a1a0b11dddfde36c3a7dedca58) | feat(agents): cheap unread jumps and footer probe (sase-1d7.9) | [sase-1d7.9](sase-1d7.9.md) | 2026-09-30 14:54:35 EDT |
| sase-core | [`sase-core@28befcb`](https://github.com/sase-org/sase-core/commit/28befcb9e411d2e5f8a8fd2405186cd3b393631d) | feat(notifications): store generations, ack API, and lean unread index | [sase-1d7.12](sase-1d7.12.md) | 2026-09-30 17:01:15 EDT |
| sase | [`4d2fa14`](https://github.com/sase-org/sase/commit/4d2fa14af32cde79226b678f673863a805a5687c) | feat(notifications): Rust ack API, lean unread index, and store generations | [sase-1d7.12](sase-1d7.12.md) | 2026-09-30 17:04:53 EDT |
| sase-core | [`sase-core@5a59e78`](https://github.com/sase-org/sase-core/commit/5a59e7859ed39d41f59f0ae1d5eb902c65f0b410) | feat(notifications): 3-day archival retention and wait\_checks 32-entry plus-one cap | [sase-1d7.13](sase-1d7.13.md) | 2026-09-30 18:38:36 EDT |
| sase | [`788a931`](https://github.com/sase-org/sase/commit/788a9311f8e6bada7f030f28c47126322e75ad8e) | feat(notifications): shorten dismissed retention to 3 days and bound wait\_checks payloads | [sase-1d7.13](sase-1d7.13.md) | 2026-09-30 19:23:54 EDT |
| sase | [`517e2a6`](https://github.com/sase-org/sase/commit/517e2a629d87e90ecc8b4776d9c8b42745ff1268) | feat(agents): land unread-ack reliability and TUI responsiveness remaining steps | [sase-1d7](README.md) | 2026-09-30 21:43:35 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1d5.land][1] | Check whether this epic owns unmasked symvision unused-public symbols found while landing sase-1d5 | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1d5.land/README.md

<!-- sase:referenced-by:end -->
