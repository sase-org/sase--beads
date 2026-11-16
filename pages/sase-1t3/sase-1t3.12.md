# Bead: sase-1t3.12 — Terminalize stale running rows in index maintenance

[Bead Pages](../README.md) / [sase-1t3](README.md) / sase-1t3.12

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.62.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.62.linker.w0.md) · **Assignee:** `sase-1t3.12` · **Size:** large
**Created:** 2026-11-16 07:57:56 EST
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

## Dependencies

- **Blocks:** [sase-1t3.14](sase-1t3.14.md) ◐ · ⧖ 2026-11-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t3.12](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.12.md) | [sase-1t3.12](sase-1t3.12.md) | 0 |
