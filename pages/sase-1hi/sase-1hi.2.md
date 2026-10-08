# Bead: sase-1hi.2 — Durable human-authorship provenance for prompts and gate answers

[Bead Pages](../README.md) / [sase-1hi](README.md) / sase-1hi.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.5n](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.5n.md) · **Assignee:** `sase-1hi.2` · **Size:** medium
**Created:** 2026-10-07 18:48:24 EDT · **Closed:** 2026-10-07 19:28:24 EDT
**Plan:** [202610/plan\_decisions.md](https://github.com/sase-org/sase--plans/blob/main/202610/plan_decisions.md)

## Description

provenance: record `prompt_origin` on every agent launch and `caller` on every gate response, then add one gatherer that returns only human-written text from a planner's chain (typed root prompt, human feedback bullets, human free-text Q&A answers), failing closed everywhere.

## Notes

[2026-10-07T23:28:02Z · sase-1hi.2] PROPOSED FOLLOW-UP: symvision private-import failure for _runs in agents_sync/v2_snapshot_io.py and ace/tui/widgets/decks/final/overview_card.py reproduces identically on the clean base tree (triaged KNOWN, no owner); unrelated to provenance work

[2026-10-07T23:28:14Z · sase-1hi.2] PROPOSED FOLLOW-UP: plan_human_text only reaches each plan-turn links latest question bundle via question_response_path; earlier rounds in a multi-round chain need a bundle-to-member or prev-bundle link to stay quotable

[2026-10-07T23:28:24Z · sase-1hi.2] prompt_origin+prompt_source_surface in every agent_meta.json (launch funnels stamp env, spawn fills fail-closed, runner persists, preserved across extraction, followups generated); caller human|agent on every gate response.json via current_actor; new sdd/plan_human_text gatherer (root typed prompt, human-caller feedback, Q&A free text, selected labels excluded). Verified: 24 new tests pass, updated bead-work contract test passes, existing-suite failures match clean base tree exactly, pre-existing symvision failure reproduced on base and noted as follow-up, epic-symbols clean

## Dependencies

- **Blocks:** [sase-1hi.3](sase-1hi.3.md) ◐ · ⧖ 2026-10-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1hi.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1hi.2/README.md) | [sase-1hi.2](sase-1hi.2.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1hi.2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1hi.2/README.md

<!-- sase:referenced-by:end -->
