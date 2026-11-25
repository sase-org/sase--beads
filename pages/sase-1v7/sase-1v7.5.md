# Bead: sase-1v7.5 — bob-cli's decisions web adopts the on-demand roster

[Bead Pages](../README.md) / [sase-1v7](README.md) / sase-1v7.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1g7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1g7.md) · **Assignee:** `sase-1v7.5` · **Size:** small
**Created:** 2026-11-25 15:44:41 EST · **Closed:** 2026-11-25 18:01:22 EST
**Plan:** [202611/on\_demand\_web\_rosters.md](https://github.com/sase-org/sase--plans/blob/main/202611/on_demand_web_rosters.md)

## Description

adopt-bob-cli: in the bob-cli checkout opened with `/sase_repo`, flip `sase/memory/decisions.md` to on-demand. Rewrite its preamble around planning-time reads and the governed domains, and add the policy record and the gotchas note as the memory decisions allow. Regenerate AGENTS.md/CLAUDE.md with a sase build that understands the new key, and verify the Codex bundle fits with no compaction.

## Notes

[2026-11-25T23:00:56Z · sase-1v7.5] PROPOSED FOLLOW-UP: bob-cli just check has 22 pre-existing failures identical on clean base (bob-obsidian lib: 4 incl three_component_marker_keeps_route_and_task_contexts, task_drawers resolve_for_merge, wispr_summary stable_words, september_shaped_vault_finishes_fast; cli integration: 18 incl inbox_route, note_pull, project_note_offer suites); needs triage as flake/ci task beads

[2026-11-25T23:01:22Z · sase-1v7.5] bob-cli decisions web loads roster on demand: decisions.md gains roster_loading/roster_read_when with planning-time triggers, new decision-rules-are-read-at-planning-time record, new core gotchas note with release-train rule; AGENTS.md/CLAUDE.md regenerated via workspace .venv sase build (installed sase is stale, lacks roster: support). Verified: pointer present with 78 decisions and zero roster entries, Codex bundle 30954B compacted (uncompacted 37500, over 32768 cap) -> 14031B with no compaction, decisions section 19095B -> 1775B, roster:decisions read works (78 entries), bare read refused with guard, -a bypass works, cargo fmt + clippy clean. bob-cli cargo test has 22 failures that reproduce identically on clean base (recorded as PROPOSED FOLLOW-UP); sase workspace untouched.

## Dependencies

- **Depends on:** [sase-1v7.1](sase-1v7.1.md) ✓ · ⧖ 2026-11-25
- **Depends on:** [sase-1v7.2](sase-1v7.2.md) ✓ · ⧖ 2026-11-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1v7.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1v7.5/README.md) | [sase-1v7.5](sase-1v7.5.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1v7.5][1] | need notes | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1v7.5/README.md

<!-- sase:referenced-by:end -->
