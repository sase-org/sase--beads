# Bead: sase-14d.4 — Apply rules in the notification poll

[Bead Pages](../README.md) / [sase-14d](README.md) / sase-14d.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0o7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0o7.md) · **Assignee:** `sase-14d.4` · **Size:** medium
**Created:** 2026-09-20 13:11:34 EDT · **Closed:** 2026-09-20 15:35:51 EDT
**Plan:** [202609/notification\_delivery\_rules.md](https://github.com/sase-org/sase--plans/blob/main/202609/notification_delivery_rules.md)

## Description

tui-delivery: resolve each arriving notification's delivery on the existing worker hop, filter toast-suppressed rows out before batching, and play at most one resolved sound per poll tick in place of the unconditional tmux bell.

## Notes

[2026-09-20T19:34:02Z · sase-14d.4] PROPOSED FOLLOW-UP: symvision is red on clean HEAD (9a99238cdf) for 25+ unused public symbols left by the refactor(service)/refactor(sdd) splits (sdd/_store_clone_remote.py, sdd/_store_clone_admission.py, service/host_support.py, service/host_reporting.py, ace/tui/models/_agent_runner_slot_capacity.py, completion/runtime_cache_generation.py) — it stops `just check` before the toobig/validate/test lanes run, so agents must run those recipes by hand until it is fixed

[2026-09-20T19:34:32Z · sase-14d.4] PROPOSED FOLLOW-UP: 7 tests fail identically on clean HEAD, unrelated to notifications — tests/test_capacity_gate_to_admission.py (2), tests/ace/tui/test_epic_panel_arrival_frames.py (4), tests/ace/tui/test_lazy_tier2_reconcile_apply.py::test_changed_query_incomplete_load_after_reconcile_rearms

[2026-09-20T19:34:58Z · sase-14d.4] PROPOSED FOLLOW-UP: _announce_notification_sound_async awaits play_sound_file inside the poll tick (as the bell always did), so a multi-second chime delays that tick return, the follow-up Agents refresh, and the auto-refresh tick by the sound duration (30s timeout cap); the 0.3s bell hid this. Consider fire-and-forget playback on a tracked worker if a long sound file is ever configured

[2026-09-20T19:35:51Z · sase-14d.4] Poll now resolves each arrival's delivery on the existing asyncio.to_thread hop (one resolve_notification_deliveries call per tick, failure falls back to toast+bell), drops toast:false rows before format_batch_toasts, and plays one sound per tick (first non-none in batch order) via _announce_notification_sound_async (bell -> _ring_tmux_bell leaf, file -> play_sound_file). Removed the three consumed sase-14d.4 epic-symbol whitelist lines; play_sound_file now also expands $VAR as the plan/core contract says. Verified: 18 new tests in tests/test_notification_toast_polling_delivery.py plus all 124 delivery/poll/sound tests pass; ruff, mypy, fmt, flags, toobig, validate and committed-plans gates pass; just test-scoped escalated to the full lane: 44024 passed, 7 unrelated failures identical on clean HEAD. just check stops at symvision, which is red on clean HEAD for unrelated service/sdd symbols; none of mine reported. Follow-ups recorded as PROPOSED FOLLOW-UP notes.

## Dependencies

- **Depends on:** [sase-14d.1](sase-14d.1.md) ✓ · ⧖ 2026-09-20
- **Depends on:** [sase-14d.2](sase-14d.2.md) ✓ · ⧖ 2026-09-20
- **Depends on:** [sase-14d.3](sase-14d.3.md) ✓ · ⧖ 2026-09-20
- **Blocks:** [sase-14d.5](sase-14d.5.md) ◐ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-14d.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14d.4/README.md) | [sase-14d.4](sase-14d.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0f5a81d`](https://github.com/sase-org/sase/commit/0f5a81da70e3fa4360d0f4eab1e44efdcfcb8ca9) | feat(tui): apply notification delivery rules in the poll | [sase-14d.4](sase-14d.4.md) | 2026-09-20 15:38:12 EDT |
