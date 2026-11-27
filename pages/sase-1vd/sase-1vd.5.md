# Bead: sase-1vd.5 — Conservative found-in-text detection

[Bead Pages](../README.md) / [sase-1vd](README.md) / sase-1vd.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1gp](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1gp.md) · **Assignee:** `sase-1vd.5` · **Size:** medium
**Created:** 2026-11-26 10:49:29 EST · **Closed:** 2026-11-26 18:17:48 EST
**Plan:** [202611/question\_copy\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202611/question_copy_panel.md)

## Description

found-in-text: add a pure sase-core detector for fenced code, filtered backtick spans, scheme URLs, and SASE artifact refs, and render its results as a dim FOUND IN TEXT section in the copy panel.

## Notes

[2026-11-26T23:02:56Z · sase-1vd.5--1] Clean-base comparison (monitor 6v6wnh0xprgf): the full nonvisual suite completed with 63,752 passed, 20 skipped, and 14 failed. It did not fail the delayed tool-admission child-start/start-stamp case reported by the modified-tree check. The clean-base failures were in stats goldens; generated memory and skill formatting; suite-gate scaled integration; agent publication and bead-link rendering; macro swarm helper; two finalization canaries; publication outcomes; and wait-summary formatting. These areas are outside this phase’s detector and copy-panel changes, so the reported child-start failure was not reproduced on the clean base.

[2026-11-26T23:17:48Z · sase-1vd.5--1] Implemented and verified the conservative found-in-text detector and copy-panel section. Targeted Rust/binding and visual checks passed; the clean-base full suite did not reproduce the admission child-start failure (comparison recorded above). Linked sase-core check passed after fixing the new test's Clippy warning. Epic-symbol audit is clear.

## Dependencies

- **Depends on:** [sase-1vd.4](sase-1vd.4.md) ✓ · ⧖ 2026-11-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vd.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1vd.5.md) | [sase-1vd.5](sase-1vd.5.md) | 3 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@8cb07c3`](https://github.com/sase-org/sase-core/commit/8cb07c3f4685c852c29c22869c56ede33299d00c) | feat(question-copy): add conservative text candidate detector | [sase-1vd.5](sase-1vd.5.md) | 2026-11-26 17:35:57 EST |
| sase | [`a29a587`](https://github.com/sase-org/sase/commit/a29a587104a1acfdc3c2e3bf0872b7841463af5f) | feat(questions): detect copyable items in question text | [sase-1vd.5](sase-1vd.5.md) | 2026-11-26 17:37:10 EST |
| sase-core | [`sase-core@464d2c8`](https://github.com/sase-org/sase-core/commit/464d2c87c007456dc212f9dd644d1c13e7b00fa7) | test(question-copy): remove useless format from detector test | [sase-1vd.5](sase-1vd.5.md) | 2026-11-26 18:19:01 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1vd.5--1][1] | Verify the phase close recorded before final declaration | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1vd.5.md

<!-- sase:referenced-by:end -->
