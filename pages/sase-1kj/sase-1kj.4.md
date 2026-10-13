# Bead: sase-1kj.4 — Back off sase tool wait and join polling

[Bead Pages](../README.md) / [sase-1kj](README.md) / sase-1kj.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.102](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.102.md) · **Assignee:** `sase-1kj.4` · **Size:** small
**Created:** 2026-10-13 11:47:19 EDT · **Closed:** 2026-10-13 12:05:48 EDT
**Plan:** [202610/apollo\_tui\_startup.md](https://github.com/sase-org/sase--plans/blob/main/202610/apollo_tui_startup.md)

## Description

tool-wait-polling: carry poll backoff across follow slices, throttle the store-wide reconcile inside waiters, and skip re-ingesting unchanged event files.

## Notes

[2026-10-13T16:04:54Z · sase-1kj.4] PROPOSED FOLLOW-UP: sase-core touch_write_meta still commits on replayed appends and on empty reconciles — skip those no-op store writes

[2026-10-13T16:05:48Z · sase-1kj.4] Carried wait poll backoff across follow_run slices, throttled waiter reconcile to first poll then every 2s, and skipped re-ingest of unchanged events files. Fake-clock 3s follow: 2 reconciles and backed-off tool_run_show (model 17 polls/2 reconciles vs ~36/36 before; loadavg 10.4/13.0/13.8 on 64 CPUs). tests/tool/test_wait_polling.py plus lifecycle/liveness/join/bounded-wait 58 passed; just fmt/fix green; no --epic-symbol leftovers. Recorded sase-core touch_write_meta follow-up.

[2026-10-13T16:24:59Z · sase-1kj.4--1] Carried wait poll backoff across follow_run slices, throttled waiter reconcile to first poll then every 2s, and skipped re-ingest of unchanged events files. Removed unused _clear_event_ingest_stat_cache (tests isolate the memo via monkeypatch). Fake-clock 3s follow: 2 reconciles and backed-off tool_run_show. tests/tool/test_wait_polling.py plus liveness 15 passed; just fix and just _lint-symvision green; no --epic-symbol leftovers.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1kj.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1kj.4.md) | [sase-1kj.4](sase-1kj.4.md) | 0 |
