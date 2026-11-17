# Bead: sase-1tc.1.1.2 — Evaluate authored commands before interpolating data

[Bead Pages](../README.md) / [sase-1tc.1.1](sase-1tc.1.1.md) / sase-1tc.1.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tc.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tc.1.md) · **Assignee:** `sase-1tc.1.1.2` · **Size:** medium
**Created:** 2026-11-17 11:31:49 EST · **Closed:** 2026-11-17 15:02:14 EST
**Plan:** [202611/cmdsub\_source\_provenance.md](https://github.com/sase-org/sase--plans/blob/main/202611/cmdsub_source_provenance.md)

## Description

preprocessing: implement source-aware Jinja rendering, explicit preprocessing provenance, and macro argument/recursive expansion integration. Prove generated data never reaches either command execution pass.

## Notes

[2026-11-17T18:34:52Z · sase-1tc.1.1.2] PROPOSED FOLLOW-UP: harden late top-level Jinja against rendered data containing {{ }} (model _raw/_response now reaches render_toplevel_jinja2 unwrapped; StrictUndefined sys.exit is a robustness regression for that channel)

[2026-11-17T18:34:58Z · sase-1tc.1.1.2] PROPOSED FOLLOW-UP: audit prompt-directive extraction against interpolated data (model output carrying %model/%id lines is now visible to extract_prompt_directives for _raw/_response, previously hidden by the facade)

[2026-11-17T20:02:14Z · sase-1tc.1.1.2] preprocessing: source-aware Jinja renderer (src/sase/macro/source_render.py) plus core-policy adapter (src/sase/macro/cmdsub_source.py) plus macro two-pass integration with admitted-definition boundaries and if-segment filtering before execution; generated data never reaches either execution pass; human source commands execute once at boundaries. 32 new tests in tests/test_cmdsub_source_provenance.py green plus updated authorship/code-blocks/args/disabled-regions suites; just check run d8081f50da06a2b0ee624a5212586986 verdict pass. sase-core-revision.txt ratcheted d2010865 to 1191f9a6 (phase-1 core commit); legacy process_command_substitution and scanner helpers deleted (zero callers); execute_cmd_cached public for the boundary; symvision clean. Two PROPOSED FOLLOW-UP notes already on the bead (late top-level Jinja {{ }} hardening; directive extraction vs data).

[2026-11-17T20:09:01Z · sase-1tc.1.1.2--1] Monitor a6aa562de61a075e2db9863e6e94f0c7 (t0qbyk3ys4cz) tested intermediate code and reported 10 NEW failures; all 10 pass on the final tree (25 passed in focused rerun 2026-11-17). Stale monitor, no reopen. Close stands.

## Dependencies

- **Depends on:** [sase-1tc.1.1.1](sase-1tc.1.1.1.md) ✓ · ⧖ 2026-11-17
- **Blocks:** [sase-1tc.1.1.3](sase-1tc.1.1.3.md) ✓ · ⧖ 2026-11-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tc.1.1.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tc.1.1.2.md) | [sase-1tc.1.1.2](sase-1tc.1.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`efc66a4`](https://github.com/sase-org/sase/commit/efc66a420b8c738e52cefa4f04bc28eec0031132) | feat(macro): evaluate authored commands before interpolating data | [sase-1tc.1.1.2](sase-1tc.1.1.2.md) | 2026-11-17 15:12:16 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tc.1.1.2--1][1] | Need phase scope and design for failure triage | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tc.1.1.2.md

<!-- sase:referenced-by:end -->
