# Bead: sase-1rq.4.1.1 — Fix the eleven sigil-alias rewrite-lane tests that have never passed on CI

[Bead Pages](../README.md) / [sase-1rq.4.1](sase-1rq.4.1.md) / sase-1rq.4.1.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1rq.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.4.md) · **Assignee:** `sase-1rq.4.1.1` · **Size:** large
**Created:** 2026-11-07 08:03:37 EST
**Plan:** [202611/bob\_mac\_capture\_ci\_green.md](https://github.com/sase-org/sase--plans/blob/main/202611/bob_mac_capture_ci_green.md)

## Description

alias-lane: fix the 11 deterministic CaptureSeparatorToggleTests / CapturePanelModelTests sigil-alias failures (`.`, `;`, `,`, `\`, `/` aliases) that fail on every macOS 26 CI run. Find the shared root cause in the Swift rewrite lane or the test harness, fix it, and prove it with Scripts/macos-ci-check before landing.

## Notes

[2026-11-07T13:13:50Z · sase-1rq.4.1.1] Planning investigation at master 1e0a092441d0a2bc0a50fc5c42ec09fd7463ce89: no prior implementation or later fix is present. Run 42337582432/job 128297901212 confirms period/move/next-parent rewritten-text assertions pass; subsequent picker waits fail. Direct fake-bob calls reproduce missing parse needs/spans for @file^, both short move-bullet drafts, @cash+goog-exit +, and lowercase Call bank @ca/@cash. Hash task-type tests omit FAKE_BOB_TASK_TYPE_CHOOSER=1. Routed comma completion is shadowed by an earlier legacy fake branch; comma tests also lack native apply wiring, assert asynchronous output synchronously, and inspect inline completion rather than the parent picker. Prepared a validated medium tale plan covering faithful fixture responses, editor wiring, picker assertions, compilation, and unfiltered snapshot plus exact-SHA master verification. No implementation files changed; bead remains in progress for the approved coder.

## Dependencies

- **Blocks:** [sase-1rq.4.1.3](sase-1rq.4.1.3.md) ◐ · ⧖ 2026-11-07
- **Blocks:** [sase-1rq.4.1.4](sase-1rq.4.1.4.md) ◐ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.4.1.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.4.1.1.md) | [sase-1rq.4.1.1](sase-1rq.4.1.1.md) | 0 |
