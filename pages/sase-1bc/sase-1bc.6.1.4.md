# Bead: sase-1bc.6.1.4 — Switch-then-reveal for every cross-tab jump

[Bead Pages](../README.md) / [sase-1bc.6.1](sase-1bc.6.1.md) / sase-1bc.6.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1bc.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bc.6.md) · **Assignee:** `sase-1bc.6.1.4` · **Size:** medium
**Created:** 2026-09-27 13:46:11 EDT · **Closed:** 2026-09-27 18:45:48 EDT
**Plan:** [202609/agent\_tabs\_scope.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_tabs_scope.md)

## Description

cross-tab-nav: add one switch-then-reveal helper and route every agent-revealing entry point through it (shared reveal, Node Finder with off-tab chips, ,j/,J from the query result, relation jumps, notification jumps, link follow and trail, the Procs monitor jump, the run-log jump, Files open agent, revive select); record the tab in jump-back anchors.

## Notes

[2026-09-27T22:45:27Z · sase-1bc.6.1.4--2] PROPOSED FOLLOW-UP: just check NEW failure tests/ace/tui/widgets/test_agent_header_panel.py::test_expanded_overflowing_header_claims_half_page_scroll (assert deck_scroll.scroll_y 2.0 == 0.0) reproduces identically on clean base tree via git stash -u; unrelated to cross-tab-nav (no header-panel files touched). KNOWN items in same run: symvision _segment_section_identity (witness 4c4fdc3b45e788fd234bc4adfcffd4db), timezone guard (witness 61a1b4485a09f23da6a8cca4f1d48ef4), deck_block_spread (witness 0975901716e461cfb24a4540ccf78054).

[2026-09-27T22:45:48Z · sase-1bc.6.1.4--2] switch-then-reveal helper + all entry points routed; verified: mypy clean (5117 files), phase tests 16/16 pass in tests/ace/tui/test_agent_tab_cross_nav.py; just check NEW header-scroll failure + 3 KNOWNs reproduce identically on clean base tree (recorded as PROPOSED FOLLOW-UP)

## Dependencies

- **Depends on:** [sase-1bc.6.1.3](sase-1bc.6.1.3.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bc.6.1.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bc.6.1.4.md) | [sase-1bc.6.1.4](sase-1bc.6.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`63fd6a5`](https://github.com/sase-org/sase/commit/63fd6a5dfd2826e411a2a63032de5f6ddc1a9274) | feat(agent-tabs): switch-then-reveal for every cross-tab jump (sase-1bc.6.1.4) | [sase-1bc.6.1.4](sase-1bc.6.1.4.md) | 2026-09-27 19:00:21 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1bc.6.1.5][1] | check status | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bc.6.1.5/README.md

<!-- sase:referenced-by:end -->
