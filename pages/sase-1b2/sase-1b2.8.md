# Bead: sase-1b2.8 — FINALIZING rows, ⊛ chips, header chip, and Reply receipts behind ace\_final\_deck

[Bead Pages](../README.md) / [sase-1b2](README.md) / sase-1b2.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0sr](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0sr.md) · **Assignee:** `sase-1b2.8` · **Size:** medium
**Created:** 2026-09-27 05:49:39 EDT · **Closed:** 2026-09-27 07:21:30 EDT
**Plan:** [202609/agents\_tab\_final\_deck.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_final_deck.md)

## Description

glance-surfaces: create the ace_final_deck beta flag and the shared finalizer view vocabulary. Add pure row-state helpers, the FINALIZING status word in the Running bucket, ⊛ row chips with the session supersede rule, the identity-header activity chip, and the ⊛ FINAL Reply receipt at every Reply assembly site including hint twins. Test with the flag on and off.

## Notes

[2026-09-27T11:20:53Z · sase-1b2.8] PROPOSED FOLLOW-UP: bench aggregator tests/ace/tui/bench_tui_jk.py fails collection on clean tree (missing test_bench_sticky_reply_flag_off_vs_on import); bench_tui_jk_agents clan/tribe benches fail identically on clean tree

[2026-09-27T11:21:30Z · sase-1b2.8] glance-surfaces done: ace_final_deck beta (bead sase-1b5) + schema regen; view_vocabulary (§3.2), finalizer_row_state (D10/D11 pure helpers), _agent_finalizer_receipt wired into session/legacy/lone-turn/hint-twin/monitor Reply sites; FINALIZING overlay stays in Running bucket, summary token in render key/signature, header activity override, hint-cache digest. Verified: 18 new on/off tests + 334 tests across touched suites green; ruff/ruff-format/mypy clean; toobig quiet for touched files. Pre-existing on clean tree (recorded as PROPOSED FOLLOW-UP): bench_tui_jk aggregator collection error + 2 clan/tribe bench failures.

## Dependencies

- **Blocks:** [sase-1b2.14](sase-1b2.14.md) ✓ · ⧖ 2026-09-27
- **Depends on:** [sase-1b2.4](sase-1b2.4.md) ✓ · ⧖ 2026-09-27
- **Depends on:** [sase-1b2.7](sase-1b2.7.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1b2.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1b2.8/README.md) | [sase-1b2.8](sase-1b2.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5dac334`](https://github.com/sase-org/sase/commit/5dac33451a4d36c224491fd1b42a78413f7fc845) | feat(ace-tui): FINALIZING rows, finalizer chips, header chip, and Reply receipts (sase-1b2.8) | [sase-1b2.8](sase-1b2.8.md) | 2026-09-27 07:23:34 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:1c][1] | Checking phase progress and notes for sase-1b2 value report | 2 |
| read-by | [agent:sase-1b2.8][2] | check notes and design detail | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.1c/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1b2.8/README.md

<!-- sase:referenced-by:end -->
