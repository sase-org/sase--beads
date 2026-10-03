# Bead: sase-1es.3 — Cold-path import and startup diet

[Bead Pages](../README.md) / [sase-1es](README.md) / sase-1es.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0v9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0v9.md) · **Assignee:** `sase-1es.3` · **Size:** medium
**Created:** 2026-10-02 08:37:48 EDT · **Closed:** 2026-10-02 12:15:13 EDT
**Plan:** [202610/pager\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202610/pager_performance.md)

## Description

cold-path-diet: make `sase.pager` imports lazy, move pure helpers out of `sase.ace.tui` into leaf modules, defer heavy imports to use sites, skip interactive-only work in plain mode, and add import-weight regression tests.

## Notes

[2026-10-02T16:14:45Z · sase-1es.3--1] PROPOSED FOLLOW-UP: 4 directive-completion/contract failures reproduce identically on clean base tree (verified via git stash): test_directive_completion_matches_aliases_to_canonical_insertions, test_ctrl_t_at_alias_partial_inserts_canonical_directive, test_percent_partial_auto_opens_directive_panel, test_runtime_directive_vocabulary_matches_core_contract (extra contract alias macros_enabled->xprompts_enabled). Unrelated to cold-path diet; triaged as pre-existing in monitor run vhvzq6rnbk9e.

[2026-10-02T16:15:13Z · sase-1es.3--1] Cold-path diet done: pager_handler import ~0.26s (was 1.56s), plain file run makes 0 collect_repo_inventory calls with identical bodies, 8 new tests in tests/pager/test_cold_path_import_cost.py pass, ruff/mypy clean. Fixed wrap-test regression from moving wrap helpers to sase.markdown_wrap (patch target updated). 4 directive-completion/contract failures reproduce identically on clean base tree, recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-1es.1](sase-1es.1.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1es.5](sase-1es.5.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1es.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1es.3.md) | [sase-1es.3](sase-1es.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`acac8d8`](https://github.com/sase-org/sase/commit/acac8d83e010f3aa26ebebfaadc26d521fec09af) | perf(pager): lighten cold-path imports and startup work | [sase-1es.3](sase-1es.3.md) | 2026-10-02 12:52:06 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:0vd][1] | Check phase deps and notes to assess conflict with three-pane split work | 1 |
| read-by | [agent:sase-1eq.1.1.7--1][2] | cite prior clean-base tracking of directive failures | 1 |
| read-by | [agent:sase-1es.3--1][3] | Need phase scope | 1 |
| read-by | [agent:sase-1es.8][4] | Need prior phase measurements for final comparison | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.0vd/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.1.1.7.md
[3]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1es.3.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1es.8/README.md

<!-- sase:referenced-by:end -->
