# Bead: sase-1t3.12 — Terminalize stale running rows in index maintenance

[Bead Pages](../README.md) / [sase-1t3](README.md) / sase-1t3.12

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.62.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.62.linker.w0.md) · **Assignee:** `sase-1t3.12` · **Size:** large
**Created:** 2026-11-16 07:57:56 EST · **Closed:** 2026-11-16 13:25:25 EST
**Plan:** [202611/tui\_storm\_trust\_heap\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202611/tui_storm_trust_heap_recovery.md)

## Description

stale-index-rows: find out why about 12.5k index rows stay running with no done marker, and terminalize them in sase-core background maintenance using real witnesses, without changing the Agents live predicate.

## Notes

[2026-11-16T13:18:47Z · sase-1t3.12] PLANNING: Read parent design and existing Rust/Python maintenance; no earlier phase notes or implementation to resume. Read-only Rust index projection on 2026-11-16 found 23,293 rows, 12,398 running/no-done, zero running markers, and 13,012 current maintenance candidates versus a 10,000-row limit. Code confirms home-only running.json writer, oldest-first selection without a cursor, overbroad workspace-number claim protection, and no candidate PID/identity check. Contribution of each cause still needs measured classification. Authored a medium tale using the existing maintenance API, with witness-based policy, persistent fair traversal, binding/integration tests, and before/after measurements; this is planning only, no implementation or production-index mutation. No epic-symbol entries at planning time. Parent research ref was unavailable via audited artifact read; independent baseline collected instead.

[2026-11-16T14:49:57Z · sase-1t3.12] Implemented witnessed stale-index terminalization for sase-1t3.12.

Policy now lives in sase-core `agent_scan/index/terminalization.rs`. Bounded maintenance revalidates source markers, requires age grace plus positive process death/identity change, and matches claims by artifact timestamp (legacy no-timestamp workspace claims stay conservative). Leftover `running.json` is not a veto. The public entry point is unchanged; additive diagnostics default to zero. A keyset cursor over `(timestamp, artifact_dir)` advances past skipped rows and wraps after an empty select / short batch. Rebuild clears `terminalization_cursor:%` meta keys. Python remains a thin caller and logs compact batch diagnostics.

Investigation (athena production index backup, schema 37, projects_root `/home/bryan/.sase/projects`):
- total 23306; `status=running` and no done marker 12396; `has_running_marker=1` 0
- terminalization candidates 13012 (same as the old `has_running_marker=0` filter)
- candidate timestamps 20260706063245..20261116075923
- candidates with pid>0: 12935; with process_identity: 8321
- Overbroad workspace/cl_name claim protection and the cursor-less LIMIT prefix were real defects; they do not explain the whole backlog. Most rows were dead local processes with no matching timestamped claim.

Scratch backup pass (copy of `~/.sase/agent_artifact_index.sqlite` via Python sqlite backup API; sources and `/proc` read-only; 24h grace, max_rows=10000, full cursor cycle, 16.25s):
- examined 13012, synthesized 12806, source_done 0
- skipped_live 0, skipped_claim 2, skipped_fresh 122, skipped_unknown 82, skipped_race 0
- remaining candidates 206 (= 2+122+82); running/no-done 12396 -> 299
- backup cached Agents-list query 0.827s / 79 records; revalidate 0.994s / 79 records (Cached and Revalidate converged)

Production facade pass after that (same knobs, 12.23s, no source writes):
- before: total 23306, running/no-done 12397, candidates 13012
- pass1: examined 10000 synthesized 9925 skipped_fresh 1 skipped_unknown 74
- pass2: examined 3012 synthesized 2880 skipped_claim 2 skipped_fresh 121 skipped_unknown 9 wrapped
- after: total 18832, running/no-done 301, candidates 207
- remaining 207 candidates are the conservative skips (fresh/held/unknown). Live Agents-list cached query 0.056s / 79 records.

Verification:
- `just test -p sase_core terminalization` 34 passed
- `just test -p sase_core_py terminalize_binding` 1 passed
- pytest wire/lifecycle/scheduler/offthread 38 passed
- Live-predicate regression: matching live workspace row without `running.json` stays active

sase-core `sase tool run check` is red on clippy `needless_bool` in unmodified files. Identical on clean HEAD `50a6d972` (tool run `624757425a9b6a438e54efc838234bbd`): `plan/decisions/grammar.rs:900`, `prompt_prediction/tokenize.rs:514` and `:838`, `tool_run/store/demand.rs:47`. Dirty-tree run `7449ecea1de2a04cfbf412f37d74622e` had those four plus our collapsible_if, which was fixed.

PROPOSED FOLLOW-UP: land a tiny clippy `needless_bool` cleanup on the four clean-base sites above so sase-core `just check` is green again. Witness: tool run `624757425a9b6a438e54efc838234bbd` on `50a6d972`.

[2026-11-16T15:19:15Z · sase-1t3.12] ## Verification

- `sase tool run check` in sase (run `70340607c0b8bc97ad399b1869e4494c`): lint green; scoped tests escalated to the full suite (`core-identity-changed`). 61196 passed, 1 failed: `tests/main/test_agents_dispatch_handler.py::test_dispatch_index_rebuild_json` expected the rebuild JSON without additive defaulted terminalization diagnostics. Updated the snapshot; 11 related tests pass.
- `just rust-install` rebuilt `sase_core_rs` 0.44.2 into this workspace `.venv`.
- `just fix` clean after the snapshot update.
- sase-core `sase tool run check` still matches clean-base clippy (`needless_bool` in `plan/decisions/grammar.rs:900`, `prompt_prediction/tokenize.rs:514` and `:838`, `tool_run/store/demand.rs:47`; witness `624757425a9b6a438e54efc838234bbd`). Our extra `collapsible_if` was flattened. PROPOSED FOLLOW-UP already on this bead.

Host should run `just check` again after this snapshot fix before landing.

[2026-11-16T16:08:33Z · sase-1t3.12--1] VERIFICATION: just check monitor kyb2khn6wdrc / tool run e3295df430d8ae18f2e451ff6a882b4f failed NEW on tests/test_models_panel_history.py::test_footer_shows_history_only_for_supported_rows[large-True] (OptionDoesNotExist: 'large'). Alias/bucket rows only appear after the provider-snapshot worker; compose starts with empty alias views and pause() can return first under load. History tests now wait for snapshot idle and the target option before highlighting. 20 history tests + 24 dispatch/wire tests pass. Unrelated to terminalization policy; needed for the landing gate. -r Record the check recovery on the assigned phase bead

[2026-11-16T18:25:25Z · sase-1t3.12--4] Closed by explicit `sase stitch create -B close` after create_commit landed f8c2763ae3 ("feat(agent-scan): surface terminalization diagnostics on the index update wire"). The commit author requested bead completion after verifying the bead scope. Reopen with `sase bead open sase-1t3.12` if more work remains.

## Dependencies

- **Blocks:** [sase-1t3.14](sase-1t3.14.md) ✓ · ⧖ 2026-11-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t3.12](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.12.md) | [sase-1t3.12](sase-1t3.12.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@969096d`](https://github.com/sase-org/sase-core/commit/969096d095350a73ce38d5ee4f90b62c2bbe420f) | feat(agent-scan): terminalize stale running index rows with lifecycle witnesses | [sase-1t3.12](sase-1t3.12.md) | 2026-11-16 13:22:55 EST |
| sase | [`f8c2763`](https://github.com/sase-org/sase/commit/f8c2763ae38fc3bb67afed60d8356b346563b5ec) | feat(agent-scan): surface terminalization diagnostics on the index update wire | [sase-1t3.12](sase-1t3.12.md) | 2026-11-16 13:24:31 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1t3.12--4][1] | Need assigned bead scope to choose keep vs close on host completion | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.12.md

<!-- sase:referenced-by:end -->
