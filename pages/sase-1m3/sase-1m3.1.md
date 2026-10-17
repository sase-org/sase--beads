# Bead: sase-1m3.1 — Write-time model provenance and the commit-record projection fix

[Bead Pages](../README.md) / [sase-1m3](README.md) / sase-1m3.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.1s.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.1s.linker.w0.md) · **Assignee:** `sase-1m3.1` · **Size:** medium
**Created:** 2026-10-16 22:05:20 EDT · **Closed:** 2026-10-16 23:07:20 EDT
**Plan:** [202610/sase\_stats\_project.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_stats_project.md)

## Description

provenance: stamp `SASE_MODEL=<provider>/<model>` on agent commits and `proposed_with` on proposed plans (including the sase-core plan-schema change), and stop projecting PR URLs into commit records' `sha`.

## Notes

[2026-10-17T02:36:45Z · sase-1m3.1] PROPOSED FOLLOW-UP: Add a decisions-web record that Projects stats count facts at their durable source and stamp only underivable footers; epic decision stats_decision_record=false prohibited this memory edit.

[2026-10-17T02:36:59Z · sase-1m3.1] PROPOSED FOLLOW-UP: The core check still hits Clippy nonminimal_bool denies in untouched crates/sase_core/src/project_onboarding/classify.rs; existing CI bead sase-1an tracks the sase-core nonminimal_bool cleanup.

[2026-10-17T03:06:57Z · sase-1m3.1] PROPOSED FOLLOW-UP: Regenerate the 18 docs/reference/cli/*.md usage blocks for current argparse output; tools/render_docs --sase-only --check reproduces this clean-base drift, and no existing bead matches it.

[2026-10-17T03:07:20Z · sase-1m3.1] Implemented model provenance for agent commits and proposed plans, added the Rust plan-schema field, and stopped PR URLs from becoming commit SHAs. Verified focused Python tests (188 passed), the targeted Rust schema test (1 passed), and git diff --check in both repos. The primary check remains red on clean-base generated CLI docs drift; the linked-core check remains red on untouched nonminimal_bool Clippy denies tracked by sase-1an. epic-symbols reported no leftovers; follow-ups recorded.

## Dependencies

- **Blocks:** [sase-1m3.12](sase-1m3.12.md) ◐ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1m3.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1m3.1/README.md) | [sase-1m3.1](sase-1m3.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@305b7b8`](https://github.com/sase-org/sase-core/commit/305b7b808ae17e325cc1aa45299514f6c265202e) | feat(plan): validate proposed\_with provenance | [sase-1m3.1](sase-1m3.1.md) | 2026-10-16 23:08:30 EDT |
| sase | [`7545e85`](https://github.com/sase-org/sase/commit/7545e85abf213f9db7ca60a517ac82c8ab26383e) | feat(provenance): stamp model attribution and fix commit metadata | [sase-1m3.1](sase-1m3.1.md) | 2026-10-16 23:13:47 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1m3.1][1] | Need the phase scope and design file | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1m3.1/README.md

<!-- sase:referenced-by:end -->
