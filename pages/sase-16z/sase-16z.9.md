# Bead: sase-16z.9 — Finish usage-window collection landing fixes and floor-aware header freshness

[Bead Pages](../README.md) / [sase-16z](README.md) / sase-16z.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-16z.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-16z.land.md) · **Assignee:** `sase-16z.9.land`
**Created:** 2026-09-23 16:32:18 EDT · **Closed:** 2026-09-23 17:59:05 EDT
**Plan:** [202609/usage\_collection\_landing\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202609/usage_collection_landing_fixes.md)

## Description

The usage-window collection work from epic sase-16z is actually complete. Its epic-introduced symvision failures are gone. agy and grok capability-cache entries hit in production. Rate-limit evidence on transport failures is classified. The stale chop test no longer spawns real provider CLIs. The TUI header usage indicator uses the same floor-aware freshness (`max(refresh_seconds, floor)`) as the CLI and Models panel, so a provider polled at its floor never shows as stale or unknown between probes.

## Notes

[2026-09-23T21:59:05Z · sase-16z.9.land] Verified all 3 phases against code: 4b9da7a33 (9.1) lands all 9 landing fixes (resolve_provider_cli_command(metadata) reused by _provider_cli_ready; capability-cache helpers privatized; executable_fingerprint resolves bare names via shutil.which; JsonLineTransportError carries stderr and codex/grok/muse/agy consult detect_rate_limit first; 429 regex rejects decimals; stale chop test removed; inline crash only records/releases live reservations; Models panel keeps pending set on failed reservation read; muse comments, test rename, axe.md .enabled:false). sase-core 1a2a752 (9.2) on origin/master adds serde-defaulted provider_min_intervals validated via shared validate_floor_map, freshness uses max(cadence,floor). ee6f7c064 (9.3) pins sase-core 1a2a752, peek cache captures usage_probe_floors off-thread and render path passes them; docs updated. Checks: just install ok, just symvision clean, 381 usage/probe/peek tests pass, no epic-symbol entries. Integration: post-start commits c44f69618 (top-bar priority chip) and 4fe7b21ec (alias test split) don't touch usage indicator/freshness; the only indicator-projection caller is peek.py, already floor-aware; nothing needs integrating. Follow-ups: 9.1 mark_all_message symvision proposal declined, already fixed by the sase-171 land (ba7532980, now _mark_all_message; symvision clean). 9.3's three pre-existing failures were duplicates, so I +1'd them: sase-175 (tribe prompts coalesce), sase-174 (ref-prefix dispatch), sase-13p (import budget 3302/3290; already 3297 before sase-16z).

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16z.9.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16z.9.land/README.md) | [sase-16z.9](sase-16z.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase--plans | [`sase--plans@17dd2fb`](https://github.com/sase-org/sase--plans/commit/17dd2fbfeabaca456a2cf2d6b7c1945f16ac0652) | chore(plans): mark sase-16z and sase-16z.9 usage-collection plans done | [sase-16z.9](sase-16z.9.md) | 2026-09-23 18:02:12 EDT |
