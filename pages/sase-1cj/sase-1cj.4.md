# Bead: sase-1cj.4 — PyO3 handles, Python facade, and pin for prompt prediction

[Bead Pages](../README.md) / [sase-1cj](README.md) / sase-1cj.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.2x` · **Assignee:** `sase-1cj.4` · **Size:** small
**Created:** 2026-09-29 07:14:29 EDT · **Closed:** 2026-09-29 10:16:32 EDT
**Plan:** [202609/prompt\_next\_word\_prediction.md](https://github.com/sase-org/sase--plans/blob/main/202609/prompt_next_word_prediction.md)

## Description

core-binding: expose frozen PromptPredictionCorpus and PromptPredictionModel pyclasses (compile releases the GIL), add the typed Python facade and wire mirror, the schema-version validator entry, a rust_backend.md section, and move the sase-core-revision pin.

## Notes

[2026-09-29T13:58:43Z · sase-1cj.4] PROPOSED FOLLOW-UP: move sase-core-revision.txt past the new prompt_prediction binding commit once the sibling sase-core checkout lands — the facade needs PromptPredictionCorpus/PromptPredictionModel which no pinned core exposes yet

[2026-09-29T14:16:14Z · sase-1cj.4--1] PROPOSED FOLLOW-UP: just check lint (feature flags) rule 8 fails on live flag bead sase-1be (key agent_tabs, no registry definition) — reproduces identically on clean base tree (verified via stash + tools/check_feature_flags), pre-existing and unrelated to core-binding phase

[2026-09-29T14:16:32Z · sase-1cj.4--1] core-binding done: PromptPredictionCorpus/Model facade + wire mirror + schema-version validator entry + rust_backend.md section + epic-symbols re-keyed to sase-1cj.5; 44 phase tests pass; just check otherwise green except pre-existing rule-8 flag failure on sase-1be (agent_tabs) which reproduces identically on clean base

## Dependencies

- **Depends on:** [sase-1cj.3](sase-1cj.3.md) ✓ · ⧖ 2026-09-29
- **Blocks:** [sase-1cj.5](sase-1cj.5.md) ◐ · ⧖ 2026-09-29
- **Blocks:** [sase-1cj.9](sase-1cj.9.md) ◐ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1cj.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1cj.4.md) | [sase-1cj.4](sase-1cj.4.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b1a371c`](https://github.com/sase-org/sase/commit/b1a371c9ac9d23d94acaabc5325ba8439cbc7a51) | feat(core-binding): add PromptPredictionCorpus/Model facade, wire mirror and validator | [sase-1cj.4](sase-1cj.4.md) | 2026-09-29 10:18:37 EDT |
| sase-core | [`sase-core@12e012d`](https://github.com/sase-org/sase-core/commit/12e012d5fa3eae2949e0c27906602a9858c07033) | feat(core-binding): add prompt\_prediction binding module with tests | [sase-1cj.4](sase-1cj.4.md) | 2026-09-29 10:22:32 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1cj.4--1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1cj.4.md

<!-- sase:referenced-by:end -->
