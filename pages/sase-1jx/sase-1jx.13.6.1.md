# Bead: sase-1jx.13.6.1 — Close the strict-mode and provider test gaps in sase-core and sase-github

[Bead Pages](../README.md) / [sase-1jx.13.6](sase-1jx.13.6.md) / sase-1jx.13.6.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jx.13.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.13.land.md) · **Assignee:** `sase-1jx.13.6.1` · **Size:** small
**Created:** 2026-10-12 19:35:35 EDT · **Closed:** 2026-10-12 20:23:11 EDT
**Plan:** [202610/new\_project\_wizard\_final\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202610/new_project_wizard_final_repairs.md)

## Description

provider-gaps: in sase-core, make an explicit request for an excluded field's behavior a strict-mode conflict even when it equals the field default; in sase-github, add the missing add_readme argv tests.

## Notes

[2026-10-13T00:23:11Z · sase-1jx.13.6.1] Strict mode now conflicts when an excluded field is explicitly requested even at its default (template + add_readme=true). Off/empty excluded values stay valid and omitted. Added table tests for that pair, all-numbered local numbered_copy hiding, and inventory-only linked/sidecar identities. sase-github argv tests cover template+add_readme=false (no conflict, no --add-readme), no-template add_readme=false (no flag), missing add_readme (emits --add-readme), and each template conflict flag alone. sase tool run check passed in sase-core (5cc7c387c28b79d8c17343b66dd7dab2) and sase-github (d98f80f1e503cc121940a44554d6a872). Did not move sase-core-revision.txt. epic-symbols: none leftover.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jx.13.6.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.13.6.1/README.md) | [sase-1jx.13.6.1](sase-1jx.13.6.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@2fc3d77`](https://github.com/sase-org/sase-core/commit/2fc3d7754a3585180d0d2d7bd7ca1e034de31cdc) | fix(project-onboarding): conflict excluded fields at default in strict mode | [sase-1jx.13.6.1](sase-1jx.13.6.1.md) | 2026-10-12 20:25:01 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jx.13.6.1][1] | Need the phase scope and design file | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.13.6.1/README.md

<!-- sase:referenced-by:end -->
