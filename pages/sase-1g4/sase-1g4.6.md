# Bead: sase-1g4.6 — Model arguments use the %model menu and model picker in the TUI

[Bead Pages](../README.md) / [sase-1g4](README.md) / sase-1g4.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0wj](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0wj.md) · **Assignee:** `sase-1g4.6` · **Size:** medium
**Created:** 2026-10-04 18:19:37 EDT · **Closed:** 2026-10-05 18:28:55 EDT
**Plan:** [202610/macro\_named\_input\_types.md](https://github.com/sase-org/sase--plans/blob/main/202610/macro_named_input_types.md)

## Description

model-tui: add the macro_arg_model completion kind that reuses the exact %model directive menu (aliases on @, provider drill-down, effort rows), open the existing ModelPickerModal for model inputs in the typed form, and add a visual snapshot.

## Notes

[2026-10-05T22:28:10Z · sase-1g4.6] PROPOSED FOLLOW-UP: Synchronize src/sase/config/sase.schema.json with the feature flag registry: check_feature_flags reports missing grok_rules_delivery, and the same failure reproduces on clean HEAD; related flag rollout phase sase-1gu.3 and lifecycle bead sase-1gv.

[2026-10-05T22:28:55Z · sase-1g4.6] Implemented macro model completion through the shared %model builder/catalog, provider drilldown and effort suffix handling, and the typed ModelPickerModal flow; updated docs/help and added detection, parity, typed form, and dark/light visual coverage. Verified focused unit tests (50 passed), targeted visual snapshots (2 passed; 2 goldens created and inspected), just fmt, and git diff --check. sase tool run check reached lint (feature flags), which fails identically on clean HEAD because the committed schema omits grok_rules_delivery; recorded that as PROPOSED FOLLOW-UP. epic-symbols reported no leftovers.

## Dependencies

- **Depends on:** [sase-1g4.3](sase-1g4.3.md) ✓ · ⧖ 2026-10-04
- **Depends on:** [sase-1g4.4](sase-1g4.4.md) ✓ · ⧖ 2026-10-04
- **Blocks:** [sase-1g4.7](sase-1g4.7.md) ✓ · ⧖ 2026-10-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1g4.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1g4.6/README.md) | [sase-1g4.6](sase-1g4.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`55c46c3`](https://github.com/sase-org/sase/commit/55c46c363386403e4e80aa3f48cf9e7d6c89dfe4) | feat(ace): add macro model argument completion | [sase-1g4.6](sase-1g4.6.md) | 2026-10-05 18:32:47 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1g4.6][1] | Confirm the baseline check follow-up note before closing | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1g4.6/README.md

<!-- sase:referenced-by:end -->
