# Bead: sase-14n.15 — Finish the sase-14n landing leftovers

[Bead Pages](../README.md) / [sase-14n](README.md) / sase-14n.15

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-14n.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-14n.land.md) · **Assignee:** `sase-14n.15.land`
**Created:** 2026-09-21 15:11:22 EDT · **Closed:** 2026-09-21 20:33:53 EDT
**Plan:** [202609/finish\_sase\_14n\_landing\_leftovers.md](https://github.com/sase-org/sase--plans/blob/main/202609/finish_sase_14n_landing_leftovers.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/finish_sase_14n_landing_leftovers.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/finish_sase_14n_landing_leftovers.md

<!-- sase:links:end -->

## Description

`just check` is green on master again: symvision is clean and the TUI app import count is strictly under its unchanged 3290 cap. Both defects behind sase-14g are closed end to end: a dismissed notification can be found and restored from the ACE notification modal, and a shell-block custom gate always registers its gate-shell row through the real creation path.

## Notes

[2026-09-22T00:33:53Z · sase-14n.15.land] Verified all 3 phases against their commits. check_green (dd22887a1): symvision is clean (footer helpers are private) and the sase.ace.tui.app closure is 3246 modules, remeasured after just install, strictly under the unchanged 3290 cap; sase-13p is closed. dismissed_view (a8bd795be): T toggles a dismissed view that reloads through the provider with include_dismissed=True, u restores rows, the footer carries T/u in all 3 variants, docs are updated, and the production-path tests pass. gate_row (c6807d24c): validate_gate_spec raises missing_gate_shell_row for a shell-block custom spec that did not come through the transaction (shell_row_managed marker), and an e2e test through create_gate_shell proves mode, row, and list visibility. A 47-node focused batch passes.

Integration: the 13 non-epic commits since 87c604833 touch no gate or notification code, and every create_gate caller was re-checked. The import count stayed under the cap after the later update and agy commits. Epic-caused leftover fixed here: tests/test_notification_modal_question_pane.py::test_question_highlight_uses_answer_focused_footer had been broken by sase-14n.8's set_variant footer (a MagicMock double auto-created set_variant). It now uses a real NotificationHintFooter at full-tier width, with no assertion loosened. sase tool run check is green.

Follow-ups: sase-14n.15.2 shard drift was +1'd on sase-14r. sase-14n.15.2 question-footer MagicMock was fixed here. sase-14n.15.3 built-in-kind shell-row guard was filed as sase-161 (feature, medium). Discovered failures not caused by this epic: clan-member cleanup e2e bisected to 04d35849d, filed as sase-162; session reporter on_output TypeError recorded as a DISCOVERED ISSUE on sase-158.6; agy probe failure from pinned core lacking provider_usage_normalize_agy_usage +1'd on sase-15v; usage_config +1'd on sase-14u; bead free-text/bead-hooks +1'd on sase-15z. No epic-symbol entries.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-14n.15.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14n.15.land/README.md) | [sase-14n.15](sase-14n.15.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bd65fd1`](https://github.com/sase-org/sase/commit/bd65fd1dd4d1ef7d4bcbc6aefeb266a5fa8b60a8) | test(notifications): drive the question footer test through a real NotificationHintFooter | [sase-14n.15](sase-14n.15.md) | 2026-09-21 20:41:33 EDT |
| sase--plans | [`sase--plans@6e7f4a9`](https://github.com/sase-org/sase--plans/commit/6e7f4a981a0444b0997a8ed523fdb667381ae860) | chore(plans): mark sase-14n and sase-14n.15 plans done | [sase-14n.15](sase-14n.15.md) | 2026-09-21 20:45:19 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-14n.15.land][1] | Need the epic scope, children, and linked plan file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14n.15.land/README.md

<!-- sase:referenced-by:end -->
