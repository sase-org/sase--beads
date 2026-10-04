# Bead: sase-1fv.2 — Provenance-accurate snippet redefinition analysis and warnings

[Bead Pages](../README.md) / [sase-1fv](README.md) / sase-1fv.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0w7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0w7.md) · **Assignee:** `sase-1fv.2` · **Size:** medium
**Created:** 2026-10-04 06:33:01 EDT · **Closed:** 2026-10-04 07:27:13 EDT
**Plan:** [202610/existing\_macro\_snippet\_editing.md](https://github.com/sase-org/sase--plans/blob/main/202610/existing_macro_snippet_editing.md)

## Description

snippet-redefinition: replace the inverted, partial `snippet_collision` check with a helper built on the provenance snippet catalog's real layer order (built-in, plugin, user, overlay, project, and macro-derived sources plus aliases), then wire it into the snippet name step, its loaded body, and the save-time warning.

## Notes

[2026-10-04T11:26:19Z · sase-1fv.2--1] PROPOSED FOLLOW-UP: reset_oom_baseline unused-public in src/sase/axe/runner_kill_provenance.py — pre-existing on master (9fe4405683, tests-only caller); this check labeled it NEW with 0 witnesses while sibling unused publics in the same file (KillProvenance, classify_runner_kill, format_kill_classification, oom_kill_evidence) are KNOWN. Related: sase-1ay unused-public backlog, sase-1c1 green-master CI.

[2026-10-04T11:27:13Z · sase-1fv.2--1] Replaced inverted snippet_collision with provenance-catalog redefinition (later-wins layers, built-in/plugin/macro/alias sites). Wired name-step verdicts, in-memory existing_body, and save-time warning refresh. Privatized leftover get_macro_snippet_entries and _refresh_snippet_save_warning. 93 targeted tests passed. No --epic-symbol leftovers. Pre-existing NEW unused-public reset_oom_baseline recorded as PROPOSED FOLLOW-UP (sase-1ay / sase-1c1).

[2026-10-04T12:17:15Z · sase-1fv.2--3] PROPOSED FOLLOW-UP: test_current_docs_skills_and_memory_avoid_stale_family_phrases fails on docs/configuration.md "families/" — KNOWN, untouched by this phase, reproduces on the same just-check as the runner_kill_provenance unused-publics. Related: sase-1c1 green-master CI.

## Dependencies

- **Blocks:** [sase-1fv.4](sase-1fv.4.md) ✓ · ⧖ 2026-10-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1fv.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1fv.2.md) | [sase-1fv.2](sase-1fv.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2608a24`](https://github.com/sase-org/sase/commit/2608a2439e1dd058d86ac1650abb91c8d2b6c3c9) | feat(snippet): replace inverted collision with provenance redefinition | [sase-1fv.2](sase-1fv.2.md) | 2026-10-04 08:41:50 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1eq.5.1.4--1][1] | Check whether this bead tracks the reproduced runner kill Symvision findings | 1 |
| read-by | [agent:sase-1fv.2--4][2] | Need notes and close state after recovery | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.5.1.4.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1fv.2.md

<!-- sase:referenced-by:end -->
