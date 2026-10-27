# Bead: sase-1ou.2.1.1 — Diagnose and fix the Rust store contention policy

[Bead Pages](../README.md) / [sase-1ou.2.1](sase-1ou.2.1.md) / sase-1ou.2.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1ou.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ou.2.md) · **Assignee:** `sase-1ou.2.1.1` · **Size:** medium
**Created:** 2026-10-27 10:41:26 EDT · **Closed:** 2026-10-27 12:04:33 EDT
**Plan:** [202610/toolrun\_sqlite\_contention.md](https://github.com/sase-org/sase--plans/blob/main/202610/toolrun_sqlite_contention.md)

## Description

core-contention: capture the clean-base failure and lock timeline, fix the responsible connection or transaction paths in sase-core, and test bounded contention and safe replay through the bindings.

## Notes

[2026-10-27T16:04:00Z · sase-1ou.2.1.1] POLICY: ToolRun store keeps 250ms default (zero-means-core-default). Write-open skips SCHEMA_SQL when schema_version, child-observation columns, and required tables (including triage/receipts) are current. One elapsed BusyBudget covers open/WAL/statements/retries; sqlite busy_timeout is sliced to 25ms so sqlite3_open_v2 BUSY is retried. Persist-WAL plus SQLITE_DBCONFIG_NO_CKPT_ON_CLOSE so last-close does not exclusive-checkpoint. Retention FS inspect runs after the writer commit. Busy (extended_code) is distinct from corruption; 0-byte in-progress creates are not quarantined. ToolRun PyO3 defaults pass busy_timeout_ms=0; unrelated telemetry bindings stay 250. No wire schema change.

EVIDENCE: unfixed core 89576266 / sase pin 800caef4. WAL BEGIN IMMEDIATE/EXCLUSIVE never busies a reader; show failure is locking_mode=EXCLUSIVE / last-close checkpoint / sqlite3_open_v2 ignoring busy_timeout. just test -p sase_core tool_run::store: 138 pass, 1 ignored. just test -p sase_core_py timeout: 2 pass. sase tool run 368488858077809ada7e7a75e54808a6: our contention and timeout tests green under the full gate; exit 101 is only federation_worker::imp::tests::ipc::listener_creates_private_socket_and_rejects_symlink (known flake sase-1gz). Do not ratchet the sase pin here — caller-integration owns that.

[2026-10-27T16:04:15Z · sase-1ou.2.1.1] PROPOSED FOLLOW-UP: sase-core check exit 101 is known flake sase-1gz — federation_worker::imp::tests::ipc::listener_creates_private_socket_and_rejects_symlink (unexpected error: federation worker is already running) under the parallel gate; our tool_run store/contention and PyO3 timeout tests passed in the same run 368488858077809ada7e7a75e54808a6.

[2026-10-27T16:04:33Z · sase-1ou.2.1.1] Rust store contention policy landed in sase-core: skip redundant schema writes on current stores (version + child columns + required tables), bounded BusyBudget retry with 25ms sqlite slices, persist-WAL + NO_CKPT_ON_CLOSE, retention FS after commit, PyO3 ToolRun defaults pass 0. just test -p sase_core tool_run::store 138 pass; just test -p sase_core_py timeout 2 pass; epic-symbols clean. sase tool run 368488858077809ada7e7a75e54808a6 failed only on known flake sase-1gz (gateway listener_creates_private_socket). Default remains 250ms. Pin ratchet left to caller-integration. Did not close parent sase-1ou.2.1 / sase-1ou.2 / sase-18t.

## Dependencies

- **Blocks:** [sase-1ou.2.1.2](sase-1ou.2.1.2.md) ◐ · ⧖ 2026-10-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ou.2.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ou.2.1.1/README.md) | [sase-1ou.2.1.1](sase-1ou.2.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@6d11122`](https://github.com/sase-org/sase-core/commit/6d11122eed284f2589ecfd99d3c60c02fc949dbc) | fix(tool\_run): bound SQLite store contention at the connection boundary | [sase-1ou.2.1.1](sase-1ou.2.1.1.md) | 2026-10-27 12:05:44 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ou.2.1.1][1] | Need the phase scope and design file | 4 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ou.2.1.1/README.md

<!-- sase:referenced-by:end -->
