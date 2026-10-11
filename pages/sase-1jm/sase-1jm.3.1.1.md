# Bead: sase-1jm.3.1.1 — Archive view state, flag, and selection ownership

[Bead Pages](../README.md) / [sase-1jm.3.1](sase-1jm.3.1.md) / sase-1jm.3.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jm.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.3.md) · **Assignee:** `sase-1jm.3.1.1` · **Size:** medium
**Created:** 2026-10-10 20:21:20 EDT · **Closed:** 2026-10-10 20:43:57 EDT
**Plan:** [202610/agents\_archive\_view\_phase.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_view_phase.md)

## Description

view-foundation: create the agents_archive_view beta flag through sase flag new. Add typed Archive presentation state, a view-aware selection API, read-only detail context, and centralized detail-ownership guards while leaving the Inbox collection and existing live selection semantics intact. Define the entry and selection seams for the remaining child phases and parent epic consumers. Test both flag states and refresh ownership.

## Notes

[2026-10-11T00:43:37Z · sase-1jm.3.1.1] View-foundation contracts for later phases: entry open_agents_archive_view (pure ,a toggle, consumed by 3.1.4), open_agents_archive_view_with_query(query, agent_name) (explicit arrival recording pending_exact_name, consumed by 3.1.4 and parent routing), close_agents_archive_view (parked-Inbox restore, 3.1.4); selection get_agents_tab_selection typed view/row_kind/agent/read_only/archive_key (3.1.5/3.1.6), archive_read_only_context outside bundle state (3.1.5 and Record phase); _get_selected_agent stays Inbox-only. Ownership: DetailOwnership(view+generation+selection_key), remember/scheduled_agents_detail_is_current, invalidate_agents_detail_ownership on every switch, agents_inbox_detail_allowed/archive_detail_owns_panel gates, cancel_inbox_detail_debounce for hidden Inbox refresh. State: AgentsArchiveViewState/ArchiveViewState/ParkedInboxState in models/agent_archive_view.py, only grouping persists, startup always Inbox via init_agents_archive_view_state wired in init_runtime_state. Flag agents_archive_view beta, bead sase-1ju.

[2026-10-11T00:43:43Z · sase-1jm.3.1.1] PROPOSED FOLLOW-UP: symvision reports 17 KNOWN unused-public items on the clean base tree (agent_archive_corpus_cache, update_failure_geometry possibly owned by sase-1js, auto_restart history) — just check reds identically without this phase change; land agent to triage

[2026-10-11T00:43:57Z · sase-1jm.3.1.1] view-foundation done: agents_archive_view beta flag registered (bead sase-1ju, schema synced); Archive/Inbox parked state, typed view-aware selection (Inbox-only _get_selected_agent preserved), read-only context, and DetailOwnership token guards in immediate/debounced/async-header/onboarding/summary/hydration paths plus cancel guards on hidden Inbox refresh. Verified: 14 new foundation tests pass (both flag states, no leakage, stale-token drop, return-to-Inbox repaint), 48 neighboring detail/refresh/selection tests pass, 153 feature-flag tests pass, sase tool run check green except 17 KNOWN pre-existing symvision items in untouched files (recorded as follow-up). No --epic-symbol entries remain for this phase; later-phase seams whitelisted under sase-1jm.3.1.

## Dependencies

- **Blocks:** [sase-1jm.3.1.2](sase-1jm.3.1.2.md) ◐ · ⧖ 2026-10-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.3.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.1/README.md) | [sase-1jm.3.1.1](sase-1jm.3.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`69f647d`](https://github.com/sase-org/sase/commit/69f647d9125f3014b7aa38629fc59963af098544) | feat(agents-archive): add Archive view state, flag, and selection ownership | [sase-1jm.3.1.1](sase-1jm.3.1.1.md) | 2026-10-10 20:46:00 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jm.3.1.1][1] | Need phase notes and remaining work check | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.1/README.md

<!-- sase:referenced-by:end -->
