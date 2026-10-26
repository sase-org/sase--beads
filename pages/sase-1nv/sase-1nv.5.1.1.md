# Bead: sase-1nv.5.1.1 — Add exact-request selection to the Rust publication policy

[Bead Pages](../README.md) / [sase-1nv.5.1](sase-1nv.5.1.md) / sase-1nv.5.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1nv.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nv.5.md) · **Assignee:** `sase-1nv.5.1.1` · **Size:** medium
**Created:** 2026-10-26 18:05:04 EDT · **Closed:** 2026-10-26 18:30:52 EDT
**Plan:** [202610/finish\_publication\_recovery\_proof.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_publication_recovery_proof.md)

## Description

exact-selection: add an optional exact logical key to bounded drain selection, preserve existing default selection, and prove that missing or ineligible keys never fall through to unrelated work.

## Notes

[2026-10-26T22:30:52Z · sase-1nv.5.1.1] Exact-key drain selection landed in sase-core: PublicationDrainSelectionRequestWire gains optional exact_key (serde default, absence preserves default selection); simultaneous exact+preferred rejected as mutually exclusive; exact match constrains eligibility with no fill from other rows, missing/ineligible keys return empty, active exact resumes only itself. 9 new core tests (stopped-behind-active, missing, wrong error class, retired permission on/off, ambiguous, empty identity, dedup, active resumption, old-wire default) plus binding round-trip test all pass. sase tool run check in sase-core: exit zero, triage verdict pass. sase bead epic-symbols sase-1nv.5.1.1: no entries. No production queue calls.

## Dependencies

- **Blocks:** [sase-1nv.5.1.2](sase-1nv.5.1.2.md) ✓ · ⧖ 2026-10-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nv.5.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nv.5.1.1/README.md) | [sase-1nv.5.1.1](sase-1nv.5.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@ae38a60`](https://github.com/sase-org/sase-core/commit/ae38a60e8324214a60248df2286bd6963484676e) | feat(publication-recovery): add exact-key constraint to drain selection | [sase-1nv.5.1.1](sase-1nv.5.1.1.md) | 2026-10-26 18:31:53 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1nv.5.1.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nv.5.1.1/README.md

<!-- sase:referenced-by:end -->
