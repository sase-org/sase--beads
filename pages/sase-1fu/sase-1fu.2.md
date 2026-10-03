# Bead: sase-1fu.2 — Drain provider JSONL promptly and preserve UTF-8

[Bead Pages](../README.md) / [sase-1fu](README.md) / sase-1fu.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vt](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vt.md) · **Assignee:** `sase-1fu.2` · **Size:** medium
**Created:** 2026-10-03 15:03:53 EDT · **Closed:** 2026-10-03 16:19:40 EDT
**Plan:** [202610/muse\_reply\_streaming.md](https://github.com/sase-org/sase--plans/blob/main/202610/muse_reply_streaming.md)

## Description

jsonl-reader: replace buffered text reads in the shared JSONL transport with bounded nonblocking byte reads and incremental decoding, preserving stderr, partial records, EOF, and completion-watchdog semantics across providers.

## Notes

[2026-10-03T20:19:20Z · sase-1fu.2] PROPOSED FOLLOW-UP: Fix the clean-base macro terminology check — test_macro_paths_avoid_xprompt_components finds the existing unallowlisted tests/xprompt/ directory; no matching bead was found.

[2026-10-03T20:19:40Z · sase-1fu.2] Replaced shared JSONL text-wrapper reads with bounded nonblocking descriptor reads and incremental UTF-8 decoding; added burst, backlog, Unicode, EOF, stderr fairness, empty-stream, and watchdog coverage. The affected provider tests passed (161 tests); just check passed all lint and 2,079 scoped tests, with only the clean-base macro terminology failure recorded as a proposed follow-up.

## Dependencies

- **Blocks:** [sase-1fu.4](sase-1fu.4.md) ◐ · ⧖ 2026-10-03

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1fu.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1fu.2/README.md) | [sase-1fu.2](sase-1fu.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3929830`](https://github.com/sase-org/sase/commit/392983091d82799747bc1222ac7c0f9151167c5a) | fix(llm-provider): drain JSONL streams incrementally | [sase-1fu.2](sase-1fu.2.md) | 2026-10-03 16:21:13 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1fu.2][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1fu.2/README.md

<!-- sase:referenced-by:end -->
