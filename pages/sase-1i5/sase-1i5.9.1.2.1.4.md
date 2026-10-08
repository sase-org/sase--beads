# Bead: sase-1i5.9.1.2.1.4 — Repair timezone-dependent and asynchronous TUI failures

[Bead Pages](../README.md) / [sase-1i5.9.1.2.1](sase-1i5.9.1.2.1.md) / sase-1i5.9.1.2.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1i5.9.1.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1i5.9.1.2.md) · **Assignee:** `sase-1i5.9.1.2.1.4` · **Size:** medium
**Created:** 2026-10-08 14:54:14 EDT · **Closed:** 2026-10-08 16:37:52 EDT
**Plan:** [202610/release\_master\_and\_full\_ci.md](https://github.com/sase-org/sase--plans/blob/main/202610/release_master_and_full_ci.md)

## Description

tui-functional: make wait-lane clocks timezone-stable and fix reproducible prompt, context-bar, archived-plan, and deck readiness failures from Full CI without longer waits or weaker assertions.

## Notes

[2026-10-08T20:37:14Z · sase-1i5.9.1.2.1.4--1] PROPOSED FOLLOW-UP: symvision unused-public red is base-reproduced and owned by phase sase-1i5.9.1.2.1.5 — just _lint-symvision fails identically on the clean base tree (test-only diff stashed; same unused-public list in src/sase); this phase touches only tests/ace/tui/test_agent_wait_epic_follow_tui.py so it cannot cause src/ findings.

[2026-10-08T20:37:38Z · sase-1i5.9.1.2.1.4--1] PROPOSED FOLLOW-UP: full check run adac7d51fa14bd93cb182fa9cd18dec2 timed out at the 1h monitor budget (exit -9, 49 KNOWN triaged; monitor yv5dm5xhntbh) — lint/fmt/SASE-validation stages passed except the symvision item above; timeout hit the test phase under host loadavg ~20-25; land agent should re-prove sase tool run check on the integrated tip.

[2026-10-08T20:37:52Z · sase-1i5.9.1.2.1.4--1] Timezone fix in tests/ace/tui/test_agent_wait_epic_follow_tui.py: tz-aware Eastern _SINCE plus call-time format_local expectation through the presentation contract (no hardcoded hour). Verified 109 focused TUI tests pass under TZ=UTC on Python 3.14 in one run (20 wait-lane + 53 prompt_next_word files + 36 readiness files); 20/20 wait-lane also under TZ=America/New_York, default TZ, and venv default Python. Step-2/3 named suites pass unmodified on this tree, so no source edits were needed. Full check adac7d51fa14bd93cb182fa9cd18dec2 timed out at 1h (exit -9, monitor yv5dm5xhntbh); only deterministic red is symvision unused-public, proven identical on the clean base tree and owned by phase .5; recorded as PROPOSED FOLLOW-UP. Epic-symbols clean.

## Dependencies

- **Blocks:** [sase-1i5.9.1.2.1.5](sase-1i5.9.1.2.1.5.md) ◐ · ⧖ 2026-10-08
- **Blocks:** [sase-1i5.9.1.2.1.7](sase-1i5.9.1.2.1.7.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1i5.9.1.2.1.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1i5.9.1.2.1.4.md) | [sase-1i5.9.1.2.1.4](sase-1i5.9.1.2.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`34829c0`](https://github.com/sase-org/sase/commit/34829c03609a0c577cb4bd4ada0b362f65f89f75) | test(ace-tui): fix timezone handling in agent wait epic follow test | [sase-1i5.9.1.2.1.4](sase-1i5.9.1.2.1.4.md) | 2026-10-08 16:40:17 EDT |
