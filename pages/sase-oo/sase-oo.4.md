# Bead: sase-oo.4 — Render the corrected core counters and disclose XPrompt truncation

[Bead Pages](../README.md) / [sase-oo](README.md) / sase-oo.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.04y](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04y.md) · **Assignee:** `sase-oo.4` · **Size:** medium
**Created:** 2026-08-17 12:01:59 EDT · **Closed:** 2026-08-17 13:16:19 EDT
**Plan:** [202608/statistics\_tab\_accuracy\_round\_two.md](https://github.com/sase-org/sase--plans/blob/main/202608/statistics_tab_accuracy_round_two.md)

## Description

consume-core: read the new wire fields so the Overview commits tile stops labelling runs as agents, correct the Projects malformed-file footnote and the stale Specs column, disclose the XPrompts breakdown truncation, split the XPrompts Share legend by denominator, and refresh the affected PNG goldens.

## Notes

[2026-08-17T17:16:19Z · sase-oo.4] Verified consume-core F3/F6/F7/F8 in this repo: Overview/Runs views read committing_runs; Commits tile renders '{agents} agents · {runs} runs' with a Commits legend; Projects footnote says unreadable project spec files and the Specs column/legend is now Patches; XPromptRow consumes models/projects/partners_truncated and drilldowns show '+N more not shown'; XPrompts Share legend splits xprompt vs child denominators. just check passed (scoped escalated to full suite: core-identity-changed). just test-visual: 700 passed, 1 skipped. epic-symbols: none remaining.

[2026-08-17T17:17:42Z · sase-oo.4] Verified consume-core F3/F6/F7/F8: Overview/Runs read committing_runs; Commits tile is '{agents} agents · {runs} runs' with a Commits legend; Projects footnote is unreadable project spec files and Specs is now Patches; XPromptRow consumes models/projects/partners_truncated and drilldowns show '+N more not shown'; XPrompts Share legend splits xprompt vs child denominators. just check passed (scoped escalated to full suite: core-identity-changed). just test-visual: 700 passed, 1 skipped. epic-symbols: none remaining.

## Dependencies

- **Depends on:** [sase-oo.1](sase-oo.1.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-oo.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-oo.4/README.md) | [sase-oo.4](sase-oo.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7391a74`](https://github.com/sase-org/sase/commit/7391a745bc42971a1f7460a4f27721756959858a) | fix(stats): render schema-6 commits, patches, and xprompt truncation | [sase-oo.4](sase-oo.4.md) | 2026-08-17 13:18:36 EDT |
