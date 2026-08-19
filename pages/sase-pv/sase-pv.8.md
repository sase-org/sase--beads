# Bead: sase-pv.8 — Delete the \`flag\` issue type end to end

[Bead Pages](../README.md) / [sase-pv](README.md) / sase-pv.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.06a](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.06a.md) · **Assignee:** `sase-pv.8` · **Size:** medium
**Created:** 2026-08-18 11:26:06 EDT · **Closed:** 2026-08-18 20:15:15 EDT
**Plan:** [202608/flag\_task\_type.md](https://github.com/sase-org/sase--plans/blob/main/202608/flag_task_type.md)

## Description

retire: remove the flag issue type, `FlagRecord`, and `BeadFlagWire` from the Rust wire, the Python model, the storage codecs, the create grammar, and the compatibility mirror schema.

## Notes

[2026-08-18T22:28:30Z · sase-pv.7.f0] BLOCKER FOR THIS PHASE, found while migrating in sase-pv.7: `sase bead rm` does not delete a bead's event stream. It appends an `issue_removed` tombstone and drops the row from `issues.jsonl`, leaving the original `issue_created` event -- including `"issue_type":"flag"` and the `flag` object -- in `events/streams/<id>.jsonl` permanently. After the migration, five such streams remain in the store: sase-nw, sase-nx, sase-om, sase-pa, sase-pk. `issues.jsonl` and the compatibility mirror have zero flag rows; only the raw streams are affected.

WHY IT BLOCKS: `read_store_issues` routes to `read_event_store_issues` whenever the event store is present (crates/sase_core/src/bead/read.rs:64-75), and `MutableStore::load` does the same (bead/mutation.rs:2382-2384), so `read_event_store` (bead/jsonl.rs:223) parses every stream file on every read and every mutation. Deleting `IssueTypeWire::Flag` from the wire therefore does not just orphan those five beads -- serde will reject their files and the whole store load will fail.

TWO CONSTRAINTS ON ANY FIX:
- Deleting a stream file outright is already publishable. `prepare_event_streams_for_commit` skips a changed path when `not (repo_root / path).is_file()`, with the comment "Removing the file is a store-level mutation (bead rm), not a truncated append-only stream" (src/sase/bead/_stream_integrity.py:92-95). Editing the events inside such a file is not publishable; that is what blocked the original migrate design.
- `events/manifest.json` carries `stream_count`, and `read_event_store` errors on `manifest.stream_count != streams.len()` (bead/jsonl.rs:238-242), so a prune must rewrite the manifest in the same mutation.

SUGGESTED SHAPE (owner's call): a one-time store migration in sase-core that drops the event streams of removed beads whose `issue_created` payload is flag-typed and rewrites `manifest.json` -- structurally the same `needs_*` / `*_sql` shape this phase already owes the compatibility mirror, and it can land alongside it. Making `sase bead rm` prune streams in general is a larger, separate decision. Keeping a deserialize-only `flag` variant would defeat the epic's purpose and is not recommended.

[2026-08-19T00:14:26Z · sase-pv.8--1] PROPOSED FOLLOW-UP: split tests/_suite_gate.py — toobig fails at 1197 lines vs 1000, unmodified by sase-pv.8

[2026-08-19T00:14:49Z · sase-pv.8--1] PROPOSED FOLLOW-UP: flake tests/test_ace_testing.py::test_ace_page_fast_startup_is_structurally_quiet — leftover cancelled sase-artifacts-project-choices task after AcePage exit; failed once in full suite then passed on rerun; not caused by flag issue-type retirement

[2026-08-19T00:15:15Z · sase-pv.8--1] Flag issue type retired end to end. Rust/Python FlagRecord, IssueType.FLAG, flag(...) create grammar, and BEAD_TYPE_PRESENTATIONS["flag"] are gone; tombstoned flag streams prune on read; SQLite drop-flag migration runs before external_ref index rewrite. Flag tasks remain task_type=flag; type:flag stays an ACE/CLI filter token. Follow-up suite leftovers fixed: CLI list JSON goldens/envelopes no longer count by_type.flag; BEAD lane keys flag identity off task_type=flag; filter-bar profile tests use BEAD_FILTER_TYPE_VALUES. Verified: sase-core just check (prior); Python ruff/mypy/fmt/flags/symvision/keep-sorted/validate/validate-committed-plans; previously failing nodes (CLI goldens/list, filter bar, task-type accents, flag BEAD lane) plus related presentation tests. just check lint(toobig) still fails only on unmodified tests/_suite_gate.py (1197/1000); AcePage startup flake noted as follow-up. No --epic-symbol leftovers. Docs/memory remain sase-pv.9.

[2026-08-19T00:16:37Z · sase-pv.8--1] Flag issue type retired end to end in Python and sase-core: IssueType.FLAG, BeadFlagWire, FlagRecord, flag_codec, flag(...) create grammar, and BEAD_TYPE_PRESENTATIONS[flag] are gone. Tombstoned flag streams are pruned; SQLite drop-flag migration runs before the external-ref index rewrite. Flag work stays as task beads of task_type=flag; type:flag remains an ACE/CLI filter token. Previously failing leftover tests (CLI by_type.flag goldens, filter-bar type:flag token, task-type accent vs retired bead type, agents-tab BEAD lane) now pass; AcePage startup flake passed on rerun. Docs/memory remain sase-pv.9. lint(toobig) on unmodified tests/_suite_gate.py is recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-pv.7](sase-pv.7.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-pv.9](sase-pv.9.md) ◐ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-pv.8](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-pv.8.md) | [sase-pv.8](sase-pv.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a317a2e`](https://github.com/sase-org/sase/commit/a317a2e359e8dfc1f8428473a7ebbdd106a94b0f) | feat(bead)!: delete the flag issue type | [sase-pv.8](sase-pv.8.md) | 2026-08-18 20:18:15 EDT |
