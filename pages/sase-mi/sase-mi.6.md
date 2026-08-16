# Bead: sase-mi.6 — Bound post-push agent publication

[Bead Pages](../README.md) / [sase-mi](README.md) / sase-mi.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.02y](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.02y.md) · **Assignee:** `sase-mi.6` · **Size:** medium
**Created:** 2026-08-15 20:02:45 EDT · **Closed:** 2026-08-15 22:19:36 EDT
**Plan:** [202608/high\_impact\_task\_bead\_sweep.md](https://github.com/sase-org/sase--plans/blob/main/202608/high_impact_task_bead_sweep.md)

## Description

bound_post_push_publication: Fix sase-mh so a stalled agent-page render cannot indefinitely block commit finalization while durable publication retry remains intact.

## Notes

[2026-08-16T02:06:53Z · sase-mi.6] PROPOSED FOLLOW-UP: symvision lint fails on clean master (pre-existing, unrelated to this phase) — private symbols imported by non-test files in src/sase/ace/tui/modals/models_panel_provider_*.py, src/sase/vcs_log/fetch_cache.py, src/sase/bead/project.py, src/sase/prompt/search/dates.py (e.g. _ProviderRoutingModal, _now, _render_provider_row); make these public or restructure the imports.

[2026-08-16T02:10:19Z · sase-mi.6] PROPOSED FOLLOW-UP: no existing task bead for the pre-existing TUI top-bar regression in tests/ace/tui/test_top_bar_order.py::test_override_pills_keep_narrow_top_bar_in_bounds (fails identically on clean master at commit b681d1bc3, unrelated to this phase — default_indicator.render() renders "..." truncation instead of the expected " CODEX(o3)@xhigh ∞ " pill text at narrow width); file a task bead to investigate the truncation/rendering regression. (Note: sase-mk already tracks the pre-existing symvision private-import lint failure, so no follow-up needed for that.)

[2026-08-16T02:13:18Z · sase-mi.6] PROPOSED FOLLOW-UP: no existing task bead for the pre-existing TUI top-bar regression in tests/ace/tui/test_top_bar_order.py::test_override_pills_keep_narrow_top_bar_in_bounds (fails identically on clean master at commit b681d1bc3, unrelated to this phase - default_indicator.render() truncates to "..." instead of the expected " CODEX(o3)@xhigh " pill text at narrow width); file a task bead to investigate the truncation/rendering regression. (sase-mk already tracks the pre-existing symvision private-import lint failure, so no follow-up is needed for that one.)

[2026-08-16T02:13:38Z · sase-mi.6] PROPOSED FOLLOW-UP: no existing task bead for the pre-existing TUI top-bar regression in tests/ace/tui/test_top_bar_order.py::test_override_pills_keep_narrow_top_bar_in_bounds (fails identically on clean master at commit b681d1bc3, unrelated to this phase - default_indicator.render() truncates to "..." instead of the expected pill text at narrow width); file a task bead to investigate the truncation/rendering regression. (sase-mk already tracks the pre-existing symvision private-import lint failure, so no follow-up is needed for that one.)

[2026-08-16T02:14:00Z · sase-mi.6] PROPOSED FOLLOW-UP: no existing task bead for the pre-existing TUI top-bar regression in tests/ace/tui/test_top_bar_order.py::test_override_pills_keep_narrow_top_bar_in_bounds (fails identically on clean master at commit b681d1bc3, unrelated to this phase - default_indicator.render() truncates to "..." instead of the expected pill text at narrow width); file a task bead to investigate the truncation/rendering regression. (sase-mk already tracks the pre-existing symvision private-import lint failure, so no follow-up is needed for that one.)

[2026-08-16T02:14:15Z · sase-mi.6] PROPOSED FOLLOW-UP: no existing task bead for the pre-existing TUI top-bar regression in tests/ace/tui/test_top_bar_order.py::test_override_pills_keep_narrow_top_bar_in_bounds (fails identically on clean master at commit b681d1bc3, unrelated to this phase - default_indicator.render() truncates to "..." instead of the expected pill text at narrow width); file a task bead to investigate the truncation/rendering regression. (sase-mk already tracks the pre-existing symvision private-import lint failure, so no follow-up is needed for that one.)

[2026-08-16T02:14:38Z · sase-mi.6] PROPOSED FOLLOW-UP: no existing task bead for the pre-existing TUI top-bar regression in tests/ace/tui/test_top_bar_order.py::test_override_pills_keep_narrow_top_bar_in_bounds (fails identically on clean master at commit b681d1bc3, unrelated to this phase - default_indicator.render() truncates to "..." instead of the expected pill text at narrow width); file a task bead to investigate the truncation/rendering regression. (sase-mk already tracks the pre-existing symvision private-import lint failure, so no follow-up is needed for that one.)

[2026-08-16T02:14:54Z · sase-mi.6] PROPOSED FOLLOW-UP: no existing task bead for the pre-existing TUI top-bar regression in tests/ace/tui/test_top_bar_order.py::test_override_pills_keep_narrow_top_bar_in_bounds (fails identically on clean master at commit b681d1bc3, unrelated to this phase - default_indicator.render() truncates to "..." instead of the expected pill text at narrow width); file a task bead to investigate the truncation/rendering regression. (sase-mk already tracks the pre-existing symvision private-import lint failure, so no follow-up is needed for that one.)

[2026-08-16T02:15:10Z · sase-mi.6] PROPOSED FOLLOW-UP: no existing task bead for the pre-existing TUI top-bar regression in tests/ace/tui/test_top_bar_order.py::test_override_pills_keep_narrow_top_bar_in_bounds (fails identically on clean master at commit b681d1bc3, unrelated to this phase - default_indicator.render() truncates to "..." instead of the expected pill text at narrow width); file a task bead to investigate the truncation/rendering regression. (sase-mk already tracks the pre-existing symvision private-import lint failure, so no follow-up is needed for that one.)

[2026-08-16T02:15:24Z · sase-mi.6] PROPOSED FOLLOW-UP: no existing task bead for the pre-existing TUI top-bar regression in tests/ace/tui/test_top_bar_order.py::test_override_pills_keep_narrow_top_bar_in_bounds (fails identically on clean master at commit b681d1bc3, unrelated to this phase - default_indicator.render() truncates to "..." instead of the expected pill text at narrow width); file a task bead to investigate the truncation/rendering regression. (sase-mk already tracks the pre-existing symvision private-import lint failure, so no follow-up is needed for that one.)

[2026-08-16T02:18:04Z · sase-mi.6] PROPOSED FOLLOW-UP: no existing task bead for the pre-existing TUI top-bar regression in tests/ace/tui/test_top_bar_order.py::test_override_pills_keep_narrow_top_bar_in_bounds (fails identically on clean master at commit b681d1bc3, unrelated to this phase - default_indicator.render() truncates to "..." instead of the expected pill text at narrow width); file a task bead to investigate the truncation/rendering regression. (sase-mk already tracks the pre-existing symvision private-import lint failure, so no follow-up is needed for that one.)

[2026-08-16T02:19:36Z · sase-mi.6] bounded post-push agent-hood publication drain (SIGALRM timeout, default 120s, configurable via SASE_AGENTS_PUBLICATION_DRAIN_TIMEOUT); a stalled render now raises PublicationDrainTimedOut, releases sase-agents-sync.lock, and leaves the request queued for retry. Regression tests in tests/agents_sync/test_commit_publication_bounded_drain.py cover: blocked render is bounded and outcome reports queued+error, lock is released after timeout, request stays in the outbox with attempts=1, and a later successful drain clears it. Verified: just fmt, full tests/agents_sync suite (283 passed), large-backlog test from sase-mb, and just test-scoped (30622 passed, 1 pre-existing unrelated failure in test_top_bar_order.py verified to fail identically on clean master). just check's symvision gate also fails identically on clean master (unrelated private-import debt already tracked by sase-mk).

[2026-08-16T02:20:29Z · sase-mi.6] bounded post-push agent-hood publication drain (SIGALRM timeout, default 120s, configurable via SASE_AGENTS_PUBLICATION_DRAIN_TIMEOUT); a stalled render now raises PublicationDrainTimedOut, releases sase-agents-sync.lock, and leaves the request queued for retry. Regression tests in tests/agents_sync/test_commit_publication_bounded_drain.py cover: blocked render is bounded and outcome reports queued+error, lock is released after timeout, request stays in the outbox with attempts=1, and a later successful drain clears it. Verified: just fmt, full tests/agents_sync suite (283 passed), large-backlog test from sase-mb, and just test-scoped (30622 passed, 1 pre-existing unrelated failure in test_top_bar_order.py verified to fail identically on clean master). just check symvision gate also fails identically on clean master (unrelated private-import debt already tracked by sase-mk).

[2026-08-16T02:21:05Z · sase-mi.6] bounded post-push agent-hood publication drain (SIGALRM timeout, default 120s, configurable via SASE_AGENTS_PUBLICATION_DRAIN_TIMEOUT); a stalled render now raises PublicationDrainTimedOut, releases sase-agents-sync.lock, and leaves the request queued for retry. Regression tests in tests/agents_sync/test_commit_publication_bounded_drain.py cover: blocked render is bounded and outcome reports queued+error, lock is released after timeout, request stays in the outbox with attempts=1, and a later successful drain clears it. Verified: just fmt, full tests/agents_sync suite (283 passed), large-backlog test from sase-mb, and just test-scoped (30622 passed, 1 pre-existing unrelated failure in test_top_bar_order.py verified to fail identically on clean master). just check symvision gate also fails identically on clean master (unrelated private-import debt already tracked by sase-mk).

[2026-08-16T02:21:32Z · sase-mi.6] bounded post-push agent-hood publication drain (SIGALRM timeout, default 120s, configurable via SASE_AGENTS_PUBLICATION_DRAIN_TIMEOUT); a stalled render now raises PublicationDrainTimedOut, releases sase-agents-sync.lock, and leaves the request queued for retry. Regression tests in tests/agents_sync/test_commit_publication_bounded_drain.py cover: blocked render is bounded and outcome reports queued+error, lock is released after timeout, request stays in the outbox with attempts=1, and a later successful drain clears it. Verified: just fmt, full tests/agents_sync suite (283 passed), large-backlog test from sase-mb, and just test-scoped (30622 passed, 1 pre-existing unrelated failure in test_top_bar_order.py verified to fail identically on clean master). just check symvision gate also fails identically on clean master (unrelated private-import debt already tracked by sase-mk).

## Dependencies

- **Depends on:** [sase-mi.5](sase-mi.5.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-mi.7](sase-mi.7.md) ◐ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-mi.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mi.6/README.md) | [sase-mi.6](sase-mi.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`392dcc9`](https://github.com/sase-org/sase/commit/392dcc962982ebf1458f10d21997341519c4ad90) | fix(agents-sync): bound the post-push agent-hood publication drain | [sase-mi.6](sase-mi.6.md) | 2026-08-15 22:22:44 EDT |
