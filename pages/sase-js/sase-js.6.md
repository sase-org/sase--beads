# Bead: sase-js.6 — Reference links and Referenced By write-back

[Bead Pages](../README.md) / [sase-js](README.md) / sase-js.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.y2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.y2/README.md) · **Assignee:** `sase-js.6` · **Size:** large
**Created:** 2026-08-11 13:22:54 EDT · **Closed:** 2026-08-12 09:00:17 EDT
**Plan:** [202608/artifact\_ref\_contract.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_ref_contract.md)

## Description

linking: rewrite published prompts to numbered `[@kind:arg][N]` reference links with revision-pinned destinations, and reconcile a managed `Referenced By` table plus structured index into each cited artifact repo through the publication outbox.

## Notes

[2026-08-12T12:58:16Z · sase-js.6] PROPOSED FOLLOW-UP: Provider-declared Referenced By columns — epic §3.8 wants columns from the provider spec, but the current phase-core spec wire has no column vocabulary and the released sase-research spec declares none. This phase uses the epic's default Agent | Project | Reference | Published | Uses column set; adopting provider-declared columns later needs a spec-wire change and coordinated provider release.

[2026-08-12T12:58:23Z · sase-js.6] PROPOSED FOLLOW-UP: Publish agents/<agent>/ref-uses.json — epic §3.7 names this store layout and core/artifact_ref_uses.py calls it a later publication step, but agents/<name>/ is owned by the v2 publication payload contract. Thread ref-use rows through that inventory/package/validation path and widen the expected-file contract separately; this phase reads the local manifest and stores the drain-ready data in referenced-by outbox rows.

[2026-08-12T13:00:17Z · sase-js.6] Implemented reference-style prompt artifact links and Referenced By write-back plumbing. Verification: just install passed; focused Python and Rust tests passed; just check passed including the escalated full-suite lane; just check-full passed through the full test-cost lane, then failed only the existing flake-baseline gate already corroborated on sase-jq/sase-iu and noted on sase-j7.

## Dependencies

- **Depends on:** [sase-js.4](sase-js.4.md) ✓ · ⧖ 2026-08-11
- **Depends on:** [sase-js.5](sase-js.5.md) ✓ · ⧖ 2026-08-11
- **Blocks:** [sase-js.9](sase-js.9.md) ✓ · ⧖ 2026-08-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-js.6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-js.6.md) | [sase-js.6](sase-js.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9907b1d`](https://github.com/sase-org/sase/commit/9907b1d1611bb397d21237367c95acd4b5578f00) | feat(agents-sync): write referenced-by links for prompt artifacts | [sase-js.6](sase-js.6.md) | 2026-08-12 09:05:20 EDT |
