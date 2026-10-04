# Bead: sase-1fu.4 — Verify the complete Muse streaming path and document its behavior

[Bead Pages](../README.md) / [sase-1fu](README.md) / sase-1fu.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vt](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vt.md) · **Assignee:** `sase-1fu.4` · **Size:** medium
**Created:** 2026-10-03 15:03:56 EDT · **Closed:** 2026-10-04 08:35:46 EDT
**Plan:** [202610/muse\_reply\_streaming.md](https://github.com/sase-org/sase--plans/blob/main/202610/muse_reply_streaming.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | [bead:sase-1fy][1] | Proposing phase: note #1 recorded the five xdist failures and the FrontmatterPanel.on_mount teardown errors |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-1fy/README.md

<!-- sase:links:end -->

## Description

streaming-validation: exercise a gated fake Muse through the mounted TUI, capture a real Muse reply with transport-to-paint timing and visual evidence, verify performance and targeted goldens, and document the supported behavior.

## Notes

[2026-10-04T12:34:04Z · sase-1fu.4--5] PROPOSED FOLLOW-UP: Fix prompt-tab focus test failures unrelated to Muse streaming — five cases in tests/ace/tui/widgets/test_prompt_tab_focus_steal.py failed with five FrontmatterPanel.on_mount NoMatches(#frontmatter-raw) teardown errors in guarded check run a02d6119e8519df3ad9af681b421ea69 (6,348 passed); identical 5 failed/5 errors reproduced on clean base HEAD 2307212bcd with pytest -n 4 --dist=worksteal -q tests/ace/tui/widgets/test_prompt_tab_focus_steal.py (18.95s).

[2026-10-04T12:35:04Z · sase-1fu.4--5] PROPOSED FOLLOW-UP: Repeat the real long Muse reply capture after quota reset — installed Muse release 1.4.2-R4684.1 returned API 429 subscription quota exhausted until 2026-10-05T00:00:00Z. The successful mounted capture and transport measurements used a synthetic JSONL fixture and do not substitute for live Muse cadence or provider-to-paint evidence.

[2026-10-04T12:35:46Z · sase-1fu.4--5] Verified the mounted fake Muse parser-to-Reply/widget regression (5 passed in prior run), targeted live-reply snapshot update (clean; four goldens byte-identical), formatting, and inspected all four snapshots plus the midstream mounted PNG. Synthetic mounted capture exercised 37 production-parser JSONL events, 36 deltas, artifact growth 760 to 26,740 bytes, partial paint at 375 ms, and terminal-to-paint at 724 ms; it is not live-provider evidence. Guarded check a02d6119e8519df3ad9af681b421ea69 completed with 6,348 passed, 5 failed, and 5 errors; the five prompt-tab failures reproduced on clean base HEAD 2307212bcd and are recorded as a proposed follow-up. Five unrelated Symvision findings were triaged KNOWN. Real Muse 1.4.2-R4684.1 capture was blocked by API 429 subscription quota through 2026-10-05T00:00:00Z and is recorded as a proposed follow-up. docs/llms.md is preserved; epic-symbol review found no leftovers.

## Dependencies

- **Depends on:** [sase-1fu.1](sase-1fu.1.md) ✓ · ⧖ 2026-10-03
- **Depends on:** [sase-1fu.2](sase-1fu.2.md) ✓ · ⧖ 2026-10-03
- **Depends on:** [sase-1fu.3](sase-1fu.3.md) ✓ · ⧖ 2026-10-03

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1fu.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1fu.4.md) | [sase-1fu.4](sase-1fu.4.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1fu.4--5][1] | Verify the clean-base check follow-up note before phase closure | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1fu.4.md

<!-- sase:referenced-by:end -->
