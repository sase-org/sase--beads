# Bead: sase-16h.6 — Give the linked repos catalogs and guards

[Bead Pages](../README.md) / [sase-16h](README.md) / sase-16h.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pf](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pf.md) · **Assignee:** `sase-16h.6` · **Size:** medium
**Created:** 2026-09-22 13:05:44 EDT · **Closed:** 2026-09-22 18:29:21 EDT
**Plan:** [202609/tool\_e15\_enforced\_adoption.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_e15_enforced_adoption.md)

## Description

linked-repo-catalogs: add project tools catalogs and the recipe guard to sase-core, sase-telegram, sase-github, and sase-research-artifacts so enforcement and named upgrades reach the raw residual that lives outside the sase repo.

## Notes

[2026-09-22T22:05:07Z · sase-16h.6] Preconditions re-verified 2026-09-22: content_layout._is_project_root returns True on .git (_PROJECT_MARKERS=(.git,.hg,.jj), src/sase/content_layout.py:35,401); all four linked checkouts contain .git so adding a config file changes no root discovery. sase-telegram root sase.yml exists (commit_hooks before=just fmt), proving a linked repo carries a project config layer without SASE project registration. tools: is project-layer-only (config/tools.py:3-5, PROJECT_ONLY_TOP_LEVEL_KEYS in config/layers.py:29, stripped from non-local layers in config/inventory.py), so adding only a tools: key changes no merged-config value.

[2026-09-22T22:26:12Z · sase-16h.6] PROPOSED FOLLOW-UP: sase-core concurrent_priority_changes_and_auto_disables_are_serialized fails under full just check load but passes alone — candidate sase-core flake bead (run 48eedbade8)

[2026-09-22T22:26:46Z · sase-16h.6] PROPOSED FOLLOW-UP: sase-github 0.2.12 just install unresolvable in this workspace (sase>=0.17.0 needs sase-core-rs<0.33, only >=0.34.23 available) — fails identically on pristine tree, needs version-skew triage (run 95345c0a)

[2026-09-22T22:27:13Z · sase-16h.6] PROPOSED FOLLOW-UP: sase-telegram test_gate_shell_settlement fails against workspace sase source (validate_gate_spec skew, telegram 0.4.19 vs local sase) — needs version-skew triage (run a2edc227)

[2026-09-22T22:28:47Z · sase-16h.6] Verified 2026-09-22: catalogs (sase-core sase/sase.yml; telegram extends root sase.yml; github+research sase/sase.yml) with check argv [just,check], args deny, stages none, repo-matching inputs+toolchain; guard scripts (sase-core scripts/, plugins tools/, 0755) wired as first check dep; AGENTS/CLAUDE sections added. sase tool list shows check in all four. Guard matrix all four: raw agent refused exit2+3 lines, cross-root marker refused, wrapped/human allowed, bypass one line. Digests all distinct and != sase check 12b1748a (core 18dc41c8, tg a2f2a5c5, gh c0a5d0cb, ra f53749ed) so TYPICAL stays unmixed. Tool runs recorded: core 48eedbade8 (red, load flake, passes alone), tg a2edc227 (red, version-skew test), gh 95345c0a (red, pre-existing unresolvable install proven on pristine tree), ra bb39549a SUCCEEDED. sase guard tests 17 passed. lint_and_test.md paragraph added via memory_write + memory init republished. Adoption 7d: wrapped 10 / raw 426 / bypassed 0 / refusals-complied 0 (sase repo records only).

[2026-09-22T22:29:21Z · sase-16h.6] Linked catalogs+guards landed in all four repos and verified: sase tool list shows check everywhere; guard refuses raw/cross-root agent runs (exit 2) and allows wrapped/human/bypass in all four; all check digests distinct from sase 12b1748a; named runs recorded with new digests (research-artifacts green, other three red on pre-existing repo-side gates triaged as PROPOSED FOLLOW-UPs); sase guard tests 17 passed; lint_and_test.md updated; epic-symbols clean

## Dependencies

- **Depends on:** [sase-16h.5](sase-16h.5.md) ✓ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16h.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16h.6/README.md) | [sase-16h.6](sase-16h.6.md) | 4 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`49bf158`](https://github.com/sase-org/sase/commit/49bf158ce6b99362e31ea58d07812fc0cc8d3bf5) | docs(memory): linked repos use sase tool run check too | [sase-16h.6](sase-16h.6.md) | 2026-09-22 18:31:08 EDT |
| sase-core | [`sase-core@2017dbe`](https://github.com/sase-org/sase-core/commit/2017dbe95e6e030e6793dcb7ed99d2ebbef5524d) | feat(tool): add check catalog and recipe guard | [sase-16h.6](sase-16h.6.md) | 2026-09-22 18:34:25 EDT |
| sase-github | [`sase-github@e807f82`](https://github.com/sase-org/sase-github/commit/e807f823f6ee137c72503d8367d0a80543196b97) | feat(tool): add check catalog and recipe guard | [sase-16h.6](sase-16h.6.md) | 2026-09-22 18:36:52 EDT |
| sase-research-artifacts | [`sase-research-artifacts@760ff40`](https://github.com/sase-org/sase-research-artifacts/commit/760ff407f24fc25ce91facd5b984051d09d668e4) | feat(tool): add check catalog and recipe guard | [sase-16h.6](sase-16h.6.md) | 2026-09-22 18:39:38 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-16h.6][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16h.6/README.md

<!-- sase:referenced-by:end -->
