# Bead: sase-1o5.2 — Core question-round projection, binding, and Python read model

[Bead Pages](../README.md) / [sase-1o5](README.md) / sase-1o5.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.58.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.58.linker.w0.md) · **Size:** medium
**Created:** 2026-10-24 19:29:30 EDT · **Closed:** 2026-10-24 21:02:46 EDT
**Plan:** [202610/questions\_main\_deck.md](https://github.com/sase-org/sase--plans/blob/main/202610/questions_main_deck.md)

## Description

core-projection: add the pure sase_core question_round projection and its project_question_round binding in sase-core, then the sase facade, typed view dataclasses, and a cached single-bundle loader, committing both repos in one turn.

## Notes

[2026-10-25T01:02:37Z · sase-1o5.2--2] PROPOSED FOLLOW-UP: just check run 41528cc55981b7cce272b03fb6b15946 ends exit 1 on 2 KNOWN failures in files this phase never touched — tests/test_macro_terminology.py::test_macro_resources_avoid_xprompt_terms (witness 2903d5fa330abde9a2bf34f3fe6bdbf2) and tests/ace/tui/test_app_import_budget.py::test_tui_app_import_stays_under_startup_budget (witness 0807aefecc59861aee177979c8a6e2be); triage verdict no_new_failures, no owner on either witness

[2026-10-25T01:02:46Z · sase-1o5.2--2] Verified: sase-core check run 75c27a4a8b07c1c1d357149b58235ce4 exit 0; sase repo check run 41528cc55981b7cce272b03fb6b15946 verdict no_new_failures (2 KNOWN failures in untouched files, recorded as PROPOSED FOLLOW-UP); 26/26 targeted tests pass (question_round facade, question_gate_turn projection, validate_sase_core_rs runtime tool); sase bead epic-symbols clean. Nothing committed; host lands both repos.

## Dependencies

- **Blocks:** [sase-1o5.3](sase-1o5.3.md) ✓ · ⧖ 2026-10-24
- **Blocks:** [sase-1o5.4](sase-1o5.4.md) ✓ · ⧖ 2026-10-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1o5.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1o5.2.md) | [sase-1o5.2](sase-1o5.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@3156d11`](https://github.com/sase-org/sase-core/commit/3156d11f33d5a5277ff806a78b92a9490f78d6be) | feat(question-round): add pure question\_round projection and project binding | [sase-1o5.2](sase-1o5.2.md) | 2026-10-24 21:03:41 EDT |
| sase | [`5497b59`](https://github.com/sase-org/sase/commit/5497b59c5ddac82c20cf92bd0f63394a1f5e2d82) | feat(questions): add question-round facade, projection loader, and core binding validation | [sase-1o5.2](sase-1o5.2.md) | 2026-10-24 21:06:42 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1o5.2--2][1] | check notes before close | 3 |
| read-by | [agent:sase-1o5.4--1][2] | Need prior phase follow-up note for macro terminology witness | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1o5.2.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1o5.4.md

<!-- sase:referenced-by:end -->
