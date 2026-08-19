# Bead: sase-qv.3 — Status pair plumbing and terminality

[Bead Pages](../README.md) / [sase-qv](README.md) / sase-qv.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.07k](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.07k.md) · **Assignee:** `sase-qv.3` · **Size:** medium
**Created:** 2026-08-19 09:14:32 EDT · **Closed:** 2026-08-19 11:30:28 EDT
**Plan:** [202608/monitor\_custom\_statuses.md](https://github.com/sase-org/sase--plans/blob/main/202608/monitor_custom_statuses.md)

## Description

model: carry monitor_stop_status alongside monitor_start_status through the scan-wire and filesystem loaders, the TUI Agent row, RunningAgentInfo, the integrations entry, and the mobile summary; fix settled monitors with custom stop labels being treated as non-terminal.

## Notes

[2026-08-19T15:30:02Z · sase-qv.3] PROPOSED FOLLOW-UP: ci — just check escalated to the full suite (rules: justfile, core-identity-changed after just install rebuilt sase-core from origin/master) and 817 tests / 20 errors failed with ProviderDisableStateError: unsupported provider-disable snapshot version 2. This sase tree still reads provider-disable v1. Unrelated to monitor status-pair plumbing; none of the new TESTED/loader/date-anchor tests failed. qv.2 already noted the matching first-writer probe; this tree now accepts v1/v2 probe envelopes so _setup can run.

[2026-08-19T15:30:28Z · sase-qv.3] Carried monitor_start_status/monitor_stop_status onto Agent (wire + filesystem loaders + done-only rows), RunningAgentInfo, AgentListEntry, and the mobile monitor dict (plus pair accent). date_anchor_time now keys monitor rows on monitor_state_is_terminal so a settled TESTED monitor anchors on stop_time. Verified: 74 targeted tests passed (loader/list/mobile/date-bucket/wire); just check lint gates all passed (fmt, ruff, mypy, symvision, toobig). Re-keyed stale closed-bead Justfile epic-symbols (sase-qt.4 → sase-qt, sase-qv.2 → sase-qv); this phase has none. just check scoped run escalated (justfile + core-identity) and failed 817 unrelated provider-disable v2 tests — recorded as PROPOSED FOLLOW-UP.

[2026-08-19T15:32:26Z · sase-qv.3] Carried monitor_start_status/monitor_stop_status onto Agent (wire + filesystem loaders + done-only rows), RunningAgentInfo, AgentListEntry, and the mobile monitor dict (plus pair accent). date_anchor_time now keys monitor rows on monitor_state_is_terminal so a settled TESTED monitor anchors on stop_time. Verified: 74 targeted tests passed (loader/list/mobile/date-bucket/wire); just check lint gates all passed (fmt, ruff, mypy, symvision, toobig). This phase has no leftover --epic-symbol entries. Stale closed-bead Justfile whitelist lines were re-keyed (sase-qt.4 -> sase-qt, sase-qv.2 -> sase-qv). just check scoped run escalated (justfile + core-identity) and failed 817 unrelated provider-disable v2 tests — recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-qv.1](sase-qv.1.md) ✓ · ⧖ 2026-08-19
- **Blocks:** [sase-qv.4](sase-qv.4.md) ✓ · ⧖ 2026-08-19
- **Blocks:** [sase-qv.5](sase-qv.5.md) ✓ · ⧖ 2026-08-19
- **Blocks:** [sase-qv.6](sase-qv.6.md) ✓ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qv.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qv.3/README.md) | [sase-qv.3](sase-qv.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ebe699d`](https://github.com/sase-org/sase/commit/ebe699d075e3442c802943e39f2f8d782af489d2) | feat(monitor): carry start/stop status pairs through listings | [sase-qv.3](sase-qv.3.md) | 2026-08-19 11:39:47 EDT |
