# Bead: sase-19x.11.2 — Verify the legacy followup Reply block heading visually

[Bead Pages](../README.md) / [sase-19x.11](sase-19x.11.md) / sase-19x.11.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-19x.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19x.land.md) · **Assignee:** `sase-19x.11.2` · **Size:** small
**Created:** 2026-09-26 14:47:59 EDT · **Closed:** 2026-09-26 16:40:31 EDT
**Plan:** [202609/card\_block\_landing\_gaps.md](https://github.com/sase-org/sase--plans/blob/main/202609/card_block_landing_gaps.md)

## Description

legacy-reply-visual: inspect the still-reachable legacy followup_agents Reply heading and per-phase blocks in a targeted visual capture.

## Notes

[2026-09-26T20:40:01Z · sase-19x.11.2] PROPOSED FOLLOW-UP: just check symvision fails identically on clean base tree (NEW _legacy_sase_shell_syntax_enabled in src/sase/agent/legacy_sase_shell_syntax.py; KNOWN _sync_scrollbar_position in main_view_blocks.py, witness 2dd118b1fc7030a17d77fc0d9a8e9c8b) — needs owner/triage outside this phase

[2026-09-26T20:40:12Z · sase-19x.11.2] PROPOSED FOLLOW-UP: AcePage visual harness times out in this sandbox on clean tree (test_agents_deck_blocks_spread_landing timed out 15s waiting for Reply card after ctrl+j); legacy Reply visual verified at document render level instead, no PNG golden added

[2026-09-26T20:40:31Z · sase-19x.11.2] Legacy followup Reply verified: deterministic non-session root (plain+monitor+gate) renders AGENT REPLY · 4 heading plus 4 per-phase dividers in both non-hint and hint paths via real render mixins; fixed hint-mode monitor/gate flatten losing the inter-phase newline (gate divider ran onto monitor output line in spread mode) in gate_phase_text/monitor_phase_text with regression test test_legacy_reply_hint_mode_keeps_monitor_gate_boundary (fails pre-fix, passes post-fix); 8/8 legacy + 7/7 gate + related widget tests pass (51 total); no goldens changed — the 7 session block PNGs are unaffected and the legacy path had no prior visual coverage; just-check symvision NEW+KNOWN findings reproduce identically on clean tree (recorded as follow-ups)

## Dependencies

- **Depends on:** [sase-19x.11.1](sase-19x.11.1.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19x.11.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19x.11.2/README.md) | [sase-19x.11.2](sase-19x.11.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`37c8b79`](https://github.com/sase-org/sase/commit/37c8b79fe4a9b8ded5ab1f91bfa0f203c88c1e3d) | fix(ace-tui): keep legacy followup Reply phase boundary in hint mode | [sase-19x.11.2](sase-19x.11.2.md) | 2026-09-26 16:42:30 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-19x.11.2][1] | full description and notes for legacy-reply-visual phase | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19x.11.2/README.md

<!-- sase:referenced-by:end -->
