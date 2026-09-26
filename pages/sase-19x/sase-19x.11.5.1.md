# Bead: sase-19x.11.5.1 — Make the block scrollbar sync helper public

[Bead Pages](../README.md) / [sase-19x.11.5](sase-19x.11.5.md) / sase-19x.11.5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-19x.11.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19x.11.land.md) · **Assignee:** `sase-19x.11.5.1` · **Size:** small
**Created:** 2026-09-26 17:16:23 EDT · **Closed:** 2026-09-26 17:24:58 EDT
**Plan:** [202609/card\_block\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/card_block_landing_repairs.md)

## Description

publish-scrollbar-sync: rename _sync_scrollbar_position to the public sync_scrollbar_position so panel_transitions.py can import it, and leave the sase-1ab legacy private import untouched.

## Notes

[2026-09-26T21:24:41Z · sase-19x.11.5.1] PROPOSED FOLLOW-UP: 3 test-scoped failures reproduce identically on clean base tree (test_preferred_card_and_partial_empty_body, test_expanded_overflowing_header_claims_half_page_scroll, test_validate_proc_lifecycle_contract_passes_for_schema_v3_transitions) — pre-existing, out of scope for publish-scrollbar-sync

[2026-09-26T21:24:58Z · sase-19x.11.5.1] Renamed _sync_scrollbar_position to sync_scrollbar_position in main_view_blocks.py (def + in-file call in _scroll_main_to_top) and panel_transitions.py (import + call in _synced_block_scroll_to). Target pilot test passes. just symvision no longer reports _sync_scrollbar_position; only expected pre-existing _legacy_sase_shell_syntax_enabled (sase-1ab, out of scope) remains. 3 unrelated test-scoped failures reproduce on clean base tree, recorded as follow-up.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19x.11.5.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19x.11.5.1/README.md) | [sase-19x.11.5.1](sase-19x.11.5.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e952415`](https://github.com/sase-org/sase/commit/e95241543d74aa677f88be8bf38838e1f1a7a45e) | refactor(decks): publish scrollbar sync helper as sync\_scrollbar\_position | [sase-19x.11.5.1](sase-19x.11.5.1.md) | 2026-09-26 17:26:30 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-19x.11.5.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19x.11.5.1/README.md

<!-- sase:referenced-by:end -->
