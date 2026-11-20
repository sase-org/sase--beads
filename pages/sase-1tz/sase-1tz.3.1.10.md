# Bead: sase-1tz.3.1.10 — Gate provider bundle sizes in sase doctor and just check

[Bead Pages](../README.md) / [sase-1tz.3.1](sase-1tz.3.1.md) / sase-1tz.3.1.10

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.3.md) · **Assignee:** `sase-1tz.3.1.10` · **Size:** medium
**Created:** 2026-11-20 09:19:08 EST · **Closed:** 2026-11-20 13:18:44 EST
**Plan:** [202611/defects\_wire\_swap\_telegram\_bundles\_triage.md](https://github.com/sase-org/sase--plans/blob/main/202611/defects_wire_swap_telegram_bundles_triage.md)

## Description

bundle_gate: a sase doctor check renders every enabled project's root bundle for each provider that declares max_bytes. It errors over the cap and warns when compaction was needed. A just-check test keeps sase's own bundles under every cap without compaction. Update the instruction-bundle and Codex provider docs.

## Notes

[2026-11-20T16:40:44Z · sase-1tz.3.1.10] MEASUREMENT (bundle_gate, read-only, 2026-11-20). BEFORE: Codex oversize instruction-fallback notifications (dedup_key instructions:fallback:<host>:codex:oversize:<day>, notifications.jsonl + archive, days 2026-11-13..2026-11-20): athena 8 notifications / 212 events (1 + plus_ones; daily 53,5,21,39,9,76,4,5); apollo 8 notifications / 230 events (daily 22,30,22,26,43,60,24,3). Live doctor run in this workspace: instructions.bundle_size WARN, bob-cli/codex 30,392/32,768 bytes after superseded_summaries (uncompacted 36,425); all 10 enabled projects x codex/grok fit; check took ~1.2 s warm, ~4.5 s cold. REPEAT AFTER INSTALL (each host): run a read-only script that keeps notifications whose dedup_key matches instructions:fallback:<host>:codex:oversize:<day> with day >= install day and prints 1+len(plus_ones) per key -- expect no new keys after the install day (the install-day key may carry pre-install +1s only); plus `sase doctor -D -C instructions.bundle_size` (expect WARN for bob-cli/codex superseded_summaries, no ERROR).

[2026-11-20T18:18:38Z · sase-1tz.3.1.10] PROPOSED FOLLOW-UP: trim bob-cli always-inlined memory so its Codex root bundle fits without compaction — the new instructions.bundle_size doctor check WARNs on bob-cli/codex (30,392/32,768 delivered bytes after superseded_summaries; uncompacted 36,425, ~3.7 KB over the cap, mostly the 75-entry decisions roster with 31 superseded); it fits today only via compaction, so any further growth there risks list_rosters or oversize fallback. This is bob-cli project memory, outside this epic.

[2026-11-20T18:18:44Z · sase-1tz.3.1.10] bundle_gate landed: new deep doctor check instructions.bundle_size (src/sase/doctor/checks_instructions_bundle_size.py, registered in checks_instructions.py) compiles every enabled project root bundle (primary checkout + real home, via list_project_records workspace_dir, labeled by display name) for each provider in capped_root_providers() (new helper; flag gating unchanged) with compile_bundle(max_bytes=cap): ERROR when delivered bytes > cap after compaction, WARN when compaction was needed (step + uncompacted size) or render failed, OK with sizes, SKIP without caps/checkouts; deep=True (~4.5 s cold / ~1.2 s warm for 10 projects x codex/grok). Re-publicized compaction.delivered_bytes per the bundle_trim handoff. Contract test tests/instructions/test_sase_bundle_size_gate.py asserts sase own root bundle fits every capped provider without compaction (empty home, all *_explicit_instructions flags on) and names the largest sections on failure; admitted to the contract set (memory-only edits seed no import graph) with manifest refreshed and budget 89->90 (0.92 s marginal). 9 focused doctor tests (OK, WARN step a, ERROR oversize, per-provider caps, render failure, SKIPs, enumeration by display name, flag gating) + registry id lists. Docs: instruction-bundles.md Provider size limits, internals Size caps and compaction (+ cache key, oversize-after-compaction), codex.md cap text, agent-clis.md check listing. Verified: sase tool run check 3affb70e7008 succeeded exit 0 (all lint gates incl. symvision/docs; test lane escalated to full suite and passed). Live: doctor WARN bob-cli/codex 30,392/32,768 after superseded_summaries; before-measurement notes recorded.

## Dependencies

- **Depends on:** [sase-1tz.3.1.9](sase-1tz.3.1.9.md) ✓ · ⧖ 2026-11-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.3.1.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.10/README.md) | [sase-1tz.3.1.10](sase-1tz.3.1.10.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f6b4344`](https://github.com/sase-org/sase/commit/f6b4344d878ca883edf496d87b115f606dd91d6e) | feat(doctor): gate provider root bundle sizes in sase doctor and just check | [sase-1tz.3.1.10](sase-1tz.3.1.10.md) | 2026-11-20 13:20:04 EST |
