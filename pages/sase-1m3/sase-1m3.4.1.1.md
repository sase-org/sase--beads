# Bead: sase-1m3.4.1.1 — Complete wire types and facet extension points

[Bead Pages](../README.md) / [sase-1m3.4.1](sase-1m3.4.1.md) / sase-1m3.4.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1m3.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1m3.4.md) · **Assignee:** `sase-1m3.4.1.1` · **Size:** medium
**Created:** 2026-10-16 22:16:01 EDT · **Closed:** 2026-10-16 23:31:40 EDT
**Plan:** [202610/project\_stats\_core\_engine.md](https://github.com/sase-org/sase--plans/blob/main/202610/project_stats_core_engine.md)

## Description

wire-seams: define the complete project_stats request and response contracts, internal history and directory types, validation, and empty facet seams without adding user-facing callers.

## Notes

[2026-10-17T03:31:01Z · sase-1m3.4.1.1--1] PROPOSED FOLLOW-UP: Core check remains blocked by the existing Clippy 1.95.0 nonminimal_bool deny in crates/sase_core/src/project_onboarding/classify.rs:500-502. The file is unchanged from core HEAD; check run 8158910f048075d741dbb079c68355ba exited 101 on that lint. Existing CI task sase-1an tracks the shared clean-base lint failure; prior exact reproduction is recorded at sase-1ko.2 note #1.

[2026-10-17T03:31:40Z · sase-1m3.4.1.1--1] Verified wire-seams implementation in linked sase-core. just fmt passed; just test -p sase_core project_stats passed 6/6. sase tool run check 8158910f048075d741dbb079c68355ba exited 101 on clippy::nonminimal_bool in unchanged crates/sase_core/src/project_onboarding/classify.rs:500-502, already tracked by sase-1an and recorded as a proposed follow-up. epic-symbols reports none.

## Dependencies

- **Blocks:** [sase-1m3.4.1.3](sase-1m3.4.1.3.md) ✓ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1m3.4.1.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1m3.4.1.1.md) | [sase-1m3.4.1.1](sase-1m3.4.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@b0cd62b`](https://github.com/sase-org/sase-core/commit/b0cd62b931d9d637a3fa9ede1e7d5b2cf9cf02eb) | feat(project-stats): add wire contracts and facet seams | [sase-1m3.4.1.1](sase-1m3.4.1.1.md) | 2026-10-16 23:32:49 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1m3.4.1.1--1][1] | Verify the recorded baseline follow-up note before phase closeout | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1m3.4.1.1.md

<!-- sase:referenced-by:end -->
