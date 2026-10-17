# Bead: sase-1m3.1 — Write-time model provenance and the commit-record projection fix

[Bead Pages](../README.md) / [sase-1m3](README.md) / sase-1m3.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.1s.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.1s.linker.w0.md) · **Assignee:** `sase-1m3.1` · **Size:** medium
**Created:** 2026-10-16 22:05:20 EDT
**Plan:** [202610/sase\_stats\_project.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_stats_project.md)

## Description

provenance: stamp `SASE_MODEL=<provider>/<model>` on agent commits and `proposed_with` on proposed plans (including the sase-core plan-schema change), and stop projecting PR URLs into commit records' `sha`.

## Notes

[2026-10-17T02:36:45Z · sase-1m3.1] PROPOSED FOLLOW-UP: Add a decisions-web record that Projects stats count facts at their durable source and stamp only underivable footers; epic decision stats_decision_record=false prohibited this memory edit.

[2026-10-17T02:36:59Z · sase-1m3.1] PROPOSED FOLLOW-UP: The core check still hits Clippy nonminimal_bool denies in untouched crates/sase_core/src/project_onboarding/classify.rs; existing CI bead sase-1an tracks the sase-core nonminimal_bool cleanup.

## Dependencies

- **Blocks:** [sase-1m3.12](sase-1m3.12.md) ◐ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1m3.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1m3.1/README.md) | [sase-1m3.1](sase-1m3.1.md) | 0 |
