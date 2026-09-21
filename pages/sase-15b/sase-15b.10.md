# Bead: sase-15b.10 — Split crates/sase\_core/tests/notification\_store\_parity.rs

[Bead Pages](../README.md) / [sase-15b](README.md) / sase-15b.10

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0oh.r0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0oh.r0.md) · **Assignee:** `sase-15b.10` · **Size:** medium
**Created:** 2026-09-21 11:31:51 EDT · **Closed:** 2026-09-21 18:11:32 EDT
**Plan:** [202609/sase\_core\_next\_ten\_big\_file\_split.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_core_next_ten_big_file_split.md)

## Description

notification_store_parity: split the 2,825-line notification store integration test into a single-binary tests/notification_store_parity/ directory and close out the epic's file-size invariant.

## Notes

[2026-09-21T22:11:12Z · sase-15b.10] PROPOSED FOLLOW-UP: tests/bead_event_parity.rs (2,182 lines) and tests/agent_scan_parity.rs (2,139 lines) are the next integration-test files over the 1500-line invariant

[2026-09-21T22:11:32Z · sase-15b.10] Split tests/notification_store_parity.rs (2,825 lines) into tests/notification_store_parity/ (main.rs + support + 6 area files, largest 704 lines). Test count 63 before/after, cargo test ok, just check green, no warnings. All ten epic targets absent from >1500-line audit; remaining oversize files untargeted.

## Dependencies

- **Depends on:** [sase-15b.9](sase-15b.9.md) ✓ · ⧖ 2026-09-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-15b.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-15b.10/README.md) | [sase-15b.10](sase-15b.10.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@8886406`](https://github.com/sase-org/sase-core/commit/88864065127efa138b71c3e778b60916a5f81b17) | refactor(sase-core): split notification\_store\_parity test into behavior-area modules | [sase-15b.10](sase-15b.10.md) | 2026-09-21 18:12:37 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.24.cld][1] | research sase-core agent maintainability (split epic phase evidence) | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.24.cld/README.md

<!-- sase:referenced-by:end -->
