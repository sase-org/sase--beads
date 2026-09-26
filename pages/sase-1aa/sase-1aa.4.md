# Bead: sase-1aa.4 — Generate model tables and prove the maintainer workflow

[Bead Pages](../README.md) / [sase-1aa](README.md) / sase-1aa.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.1t](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.1t.md) · **Assignee:** `sase-1aa.4` · **Size:** medium
**Created:** 2026-09-25 22:26:21 EDT · **Closed:** 2026-09-26 07:32:53 EDT
**Plan:** [202609/model\_catalog\_maintenance.md](https://github.com/sase-org/sase--plans/blob/main/202609/model_catalog_maintenance.md)

## Description

generated_model_docs: render mirrored model tables from YAML, replace freshness prose with table links, and verify a catalog or pool update requires only one hand-edited file.

## Notes

[2026-09-26T11:32:53Z · sase-1aa.4] Phase 4 done: tools/render_model_docs now renders 11 generated blocks in docs/llms.md from models.yml (alias defaults, known-models catalog, short aliases, tier-default summary, 7 per-provider tier tables) with --check over every block; stale pool prose in ace.md and the Antigravity section replaced with table links; three-command maintainer workflow plus membership/tier/pool distinction documented. New just model-policy-check gate runs in just check/check-full and both CI workflows. All 5 epic-symbols resolved: PolicyViolation, format_policy_violations, validate_manifest_policy consumed by new sase doctor -C llm.model_policy check; dead check_shipped/validate_shipped wrappers deleted. Synthetic proof in /tmp: added synth-probe-1 plus a claude tier retune to a manifest copy, regenerated docs carry it in catalog/alias/tier tables, policy clean, second render no-op, only the manifest plus generated docs involved. Verified: sase tool run check gates green (fmt, generated docs, model policy, keep-sorted, ruff, mypy, flags, pyscripts, test-waits, changelog, patch/stitch, symvision with zero sase-1aa.4 leftovers), just validate and validate-committed-plans pass, just docs-check (mkdocs strict) passes, affected packages 1728 tests pass. test-scoped escalated to the full suite per the justfile/rename rule and could not finish in one turn (26% clean, no failures); CI backstops the remainder.

## Dependencies

- **Depends on:** [sase-1aa.3](sase-1aa.3.md) ✓ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1aa.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1aa.4/README.md) | [sase-1aa.4](sase-1aa.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`39acc57`](https://github.com/sase-org/sase/commit/39acc575475bf2d0391b24a655d2077c6a86b0e6) | feat(llm): generate model docs tables with policy gate and doctor check | [sase-1aa.4](sase-1aa.4.md) | 2026-09-26 07:35:32 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-19p.4.land][1] | Need follow-up bead status | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-19p.4.land/README.md

<!-- sase:referenced-by:end -->
