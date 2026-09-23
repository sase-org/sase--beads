# Bead: sase-16y.1 — Jump-map sections, document carrier, and pure legend renderer

[Bead Pages](../README.md) / [sase-16y](README.md) / sase-16y.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0q0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0q0.md) · **Assignee:** `sase-16y.1` · **Size:** medium
**Created:** 2026-09-23 10:49:54 EDT · **Closed:** 2026-09-23 11:32:17 EDT
**Plan:** [202609/agent\_jump\_footer\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_jump_footer_panel.md)

## Description

legend: enrich MemberJumpMap with per-target labels and status buckets plus ordered roster sections, carry the exact published map on detached documents (not hint documents or cheap tribe paints) through a new AgentPromptPanel sink, and build the width-responsive collapsed/expanded/narrowed legend renderable with its uniqueness-preserving packer and unit tests; no visible change.

## Notes

[2026-09-23T15:31:39Z · sase-16y.1] PROPOSED FOLLOW-UP: just check is red on unrelated pre-existing gates (pyscripts tools/visual placement, symvision ExpandedLaunchSegments, ~13 scoped failures in bead CLI/prompt/query areas proven pre-existing via stash) — land agent to triage

[2026-09-23T15:32:17Z · sase-16y.1] legend phase done: MemberJumpSection/labels/buckets/sections + member_status_style in _member_roster; carrier slot + shared walker + find_member_jump_map/MemberJumpMapSink; detached builders attach the exact published map (no map for hint/cheap/empty/non-roster); AgentPromptPanel.attach_member_jump_map_sink called pre-digest; new JumpLegendRenderable + title/accent helpers with uniqueness-preserving packer; 50 new tests pass plus clan-order test updated for mandated status_bucket contract; symvision clean except pre-existing ExpandedLaunchSegments (4 new symbols whitelisted to sase-16y); no rendering path changed so PNG goldens untouched

## Dependencies

- **Blocks:** [sase-16y.3](sase-16y.3.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16y.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16y.1/README.md) | [sase-16y.1](sase-16y.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0513bf2`](https://github.com/sase-org/sase/commit/0513bf2ab3048cd8b6c07c1041fe9856b33e142b) | feat(agents): jump-map sections, document carrier, and pure legend renderer | [sase-16y.1](sase-16y.1.md) | 2026-09-23 11:34:27 EDT |
