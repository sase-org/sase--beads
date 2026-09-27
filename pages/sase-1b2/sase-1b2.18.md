# Bead: sase-1b2.18 — Live tails, following, and the 1 Hz tick for the selected agent

[Bead Pages](../README.md) / [sase-1b2](README.md) / sase-1b2.18

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0sr](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0sr.md) · **Assignee:** `sase-1b2.18` · **Size:** medium
**Created:** 2026-09-27 05:49:52 EDT
**Plan:** [202609/agents\_tab\_final\_deck.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_final_deck.md)

## Description

final-live: add the ace.agent_decks.final_tail_delay_seconds gate and a sanitized in-card live tail of at most 12 lines. The tail follows the newest run and attempt with the arrival marker, pauses on scroll-up, and runs a pump-free 1 Hz elapsed/tail refresh only while FINAL shows the selected agent's active finalization.

## Dependencies

- **Depends on:** [sase-1b2.17](sase-1b2.17.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1b2.19](sase-1b2.19.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1b2.18](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1b2.18/README.md) | [sase-1b2.18](sase-1b2.18.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:1c][1] | Mapping sase-1b2 phase dependency graph for value report | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.1c/README.md

<!-- sase:referenced-by:end -->
