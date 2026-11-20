# Bead: sase-1tz.3.1.10 — Gate provider bundle sizes in sase doctor and just check

[Bead Pages](../README.md) / [sase-1tz.3.1](sase-1tz.3.1.md) / sase-1tz.3.1.10

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.3.md) · **Assignee:** `sase-1tz.3.1.10` · **Size:** medium
**Created:** 2026-11-20 09:19:08 EST
**Plan:** [202611/defects\_wire\_swap\_telegram\_bundles\_triage.md](https://github.com/sase-org/sase--plans/blob/main/202611/defects_wire_swap_telegram_bundles_triage.md)

## Description

bundle_gate: a sase doctor check renders every enabled project's root bundle for each provider that declares max_bytes. It errors over the cap and warns when compaction was needed. A just-check test keeps sase's own bundles under every cap without compaction. Update the instruction-bundle and Codex provider docs.

## Notes

[2026-11-20T16:40:44Z · sase-1tz.3.1.10] MEASUREMENT (bundle_gate, read-only, 2026-11-20). BEFORE: Codex oversize instruction-fallback notifications (dedup_key instructions:fallback:<host>:codex:oversize:<day>, notifications.jsonl + archive, days 2026-11-13..2026-11-20): athena 8 notifications / 212 events (1 + plus_ones; daily 53,5,21,39,9,76,4,5); apollo 8 notifications / 230 events (daily 22,30,22,26,43,60,24,3). Live doctor run in this workspace: instructions.bundle_size WARN, bob-cli/codex 30,392/32,768 bytes after superseded_summaries (uncompacted 36,425); all 10 enabled projects x codex/grok fit; check took ~1.2 s warm, ~4.5 s cold. REPEAT AFTER INSTALL (each host): run a read-only script that keeps notifications whose dedup_key matches instructions:fallback:<host>:codex:oversize:<day> with day >= install day and prints 1+len(plus_ones) per key -- expect no new keys after the install day (the install-day key may carry pre-install +1s only); plus `sase doctor -D -C instructions.bundle_size` (expect WARN for bob-cli/codex superseded_summaries, no ERROR).

## Dependencies

- **Depends on:** [sase-1tz.3.1.9](sase-1tz.3.1.9.md) ✓ · ⧖ 2026-11-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.3.1.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.10/README.md) | [sase-1tz.3.1.10](sase-1tz.3.1.10.md) | 0 |
