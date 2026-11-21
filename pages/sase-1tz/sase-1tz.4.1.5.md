# Bead: sase-1tz.4.1.5 — Resolve sidecar payloads in every reader, then externalize payloads over 8 KB

[Bead Pages](../README.md) / [sase-1tz.4.1](sase-1tz.4.1.md) / sase-1tz.4.1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.4.md) · **Assignee:** `sase-1tz.4.1.5` · **Size:** medium
**Created:** 2026-11-20 14:00:22 EST · **Closed:** 2026-11-21 07:22:27 EST
**Plan:** [202611/hygiene\_gateway\_notifications\_retention.md](https://github.com/sase-org/sase--plans/blob/main/202611/hygiene_gateway_notifications_retention.md)

## Description

blob_adopt: the TUI, Telegram, and mobile readers that need full action_data or note text resolve sidecar references. Then the Python store wrapper externalizes payloads over 8 KB by default, and live oversize rows migrate once.

## Notes

[2026-11-20T23:53:04Z · sase-1tz.4.1.5] blob_adopt pre-install baseline (read-only, 2026-11-20). Payload-byte counts are the sum of compact UTF-8 JSON encodings for each row's action_data and notes; rows_over_8k counts rows whose combined values exceed 8,192 bytes; broken_files counts files entries that no longer exist.

- athena: live_store_bytes=5,123,812; rows=2,252; action_data_and_notes_bytes=3,358,579; rows_over_8k=76; broken_files=452.
- apollo: live_store_bytes=4,187,514; rows=1,709; action_data_and_notes_bytes=3,216,430; rows_over_8k=69; broken_files=352.

After-install repeat command (run on both hosts after deploying the wrapper):

\```sh
for host in athena apollo; do
  ssh "$host" 'python3 -c "import json,pathlib; p=pathlib.Path.home()/\".sase/notifications/notifications.jsonl\"; rows=[json.loads(line) for line in p.read_text(encoding=\"utf-8\").splitlines() if line.strip()]; sizes=[len(json.dumps(row.get(\"action_data\") or {},ensure_ascii=False,separators=(\",\",\":\")).encode())+len(json.dumps(row.get(\"notes\") or [],ensure_ascii=False,separators=(\",\",\":\")).encode()) for row in rows]; print(json.dumps({\"live_store_bytes\":p.stat().st_size,\"rows\":len(rows),\"action_data_and_notes_bytes\":sum(sizes),\"rows_over_8k\":sum(size>8192 for size in sizes),\"broken_files\":sum(1 for row in rows for file in row.get(\"files\",[]) if not pathlib.Path(file).expanduser().exists())}))"'
done
\```

[2026-11-21T00:41:31Z · sase-1tz.4.1.5] PROPOSED FOLLOW-UP: Root check b39b8fadcdba2c8bee27d0716949cd12 confirmed the known artifact-directory audit mismatch at src/sase/scripts/_bead_task_triage_gates.py:reap_settled_bundles; this file and the audit test are unchanged from HEAD. It was already reproduced on clean master and recorded on parent epic sase-1tz.4.1 note #1, attributed to phase sase-1tz.4.1.9. Do not create a duplicate task; follow the existing epic record.

[2026-11-21T12:02:02Z · sase-1tz.4.1.5] Reader audit: prior main implementation landed in sase 88d36297cc and Telegram bffd4f6; no reimplementation or live-host mutations needed. Full-value readers: notify show resolves all fields; TUI report/run-prune review resolve report and run_prune_review; JumpToAgent selects by short identity then loads raw_prompt.md from the agent artifact directory; gate-error fallback now resolves message/recovery commands off-loop; waiter reconciliation/expiry now resolves waiters JSON (and compares resolved notes/data to avoid repeated writes), with confirmation using inline waiter_count and execution retaining a missing-payload notice. Telegram completion formatting resolves prompt/output_variables/notes, project_context resolves pending prompt or prompt_path, and response attachments now resolve commit_message. Remaining TUI note displays and mobile notes/cards intentionally use previews. Rust notifications/mobile.rs only consumes short identity/path/count keys and reads gate branches from request_path. Added real-sidecar regressions for >200 KB prompts, mobile previews, large waiter lists/no-op reconciliation, missing waiter payloads, and Telegram attachment content. Existing default externalization and compaction migration tests retained. First focused run: 78 passed.

[2026-11-21T12:15:02Z · sase-1tz.4.1.5] Verification update: main repository sase tool run check e09f2dea2640f77d7f7d05e9b79f4657 passed all stages, including scoped tests (7m22s). The earlier artifact-audit failure in note #2 did not recur. Additional focused reader/confirmation run passed 10 tests. Telegram check 07180631866d77a41c3b5fd5c0e8f582 is still building the pinned Rust binding before lint/tests.

[2026-11-21T12:22:15Z · sase-1tz.4.1.5] PROPOSED FOLLOW-UP: Telegram check has four pre-existing tag-catalog fixture errors, already tracked by sase-1ug — check 07180631866d77a41c3b5fd5c0e8f582 passed Ruff, mypy, and 881 tests (including the new real-sidecar prompt and attachment regressions), with four AttributeError setup errors for removed sase.project_display_names._project_display_name_map_cached. Independently reproduced all four identically using git-archive clean source/test snapshots of sase cd7c9f85c4 and sase-telegram bffd4f6 (confirmed imported module paths point into snapshots). Exact cases: tests/test_formatting.py::TestBuildForkCopyText::test_tag_prompt_renders_tag_form; tests/test_inbound.py::TestBeadProjectContext::{test_extract_project_from_tag_prompt,test_records_project_context_for_tag_prompt,test_fork_wait_copy_text_uses_tag_form}. No duplicate task or fixture changes made. Main check e09f2dea2640f77d7f7d05e9b79f4657 passed; phase implementation and all new regressions are complete.

[2026-11-21T12:22:27Z · sase-1tz.4.1.5] Completed reader adoption on top of landed sase 88d36297cc / Telegram bffd4f6: resolve large waiter lists and gate-error fallback values, keep missing-payload notices open, preserve no-op reconciliation and TUI responsiveness, and hydrate Telegram commit-message attachments. Real >200 KB prompt, mobile preview, waiter, and attachment regressions pass. Main sase tool run check e09f2dea2640f77d7f7d05e9b79f4657 passed. Telegram check 07180631866d77a41c3b5fd5c0e8f582: Ruff/mypy and 881 tests passed; four unchanged fixture errors reproduced identically on clean bases and recorded as PROPOSED FOLLOW-UP citing sase-1ug. Measurements and after-install repeat command already recorded. No epic-symbol entries; no ancestor closed.

## Dependencies

- **Depends on:** [sase-1tz.4.1.4](sase-1tz.4.1.4.md) ✓ · ⧖ 2026-11-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.4.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.5/README.md) | [sase-1tz.4.1.5](sase-1tz.4.1.5.md) | 4 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`88d3629`](https://github.com/sase-org/sase/commit/88d36297ccb8c756fcb72346c5caf18231f373fc) | feat(notifications): externalize payloads over 8 KiB | [sase-1tz.4.1.5](sase-1tz.4.1.5.md) | 2026-11-20 19:43:56 EST |
| sase-telegram | [`sase-telegram@bffd4f6`](https://github.com/sase-org/sase-telegram/commit/bffd4f6cf02992125d0229c9c8cf7ee44bb15e07) | fix(telegram): resolve notification sidecar payloads | [sase-1tz.4.1.5](sase-1tz.4.1.5.md) | 2026-11-20 19:45:33 EST |
| sase | [`39b594a`](https://github.com/sase-org/sase/commit/39b594a30cb42239958f2725347bc92da9c3b6d4) | fix(notifications): resolve remaining sidecar payload readers | [sase-1tz.4.1.5](sase-1tz.4.1.5.md) | 2026-11-21 07:24:05 EST |
| sase-telegram | [`sase-telegram@4f2939f`](https://github.com/sase-org/sase-telegram/commit/4f2939fc20ab5bccfc2a0cc361672b7b49fccebd) | fix(telegram): resolve sidecar commit messages in attachments | [sase-1tz.4.1.5](sase-1tz.4.1.5.md) | 2026-11-21 07:25:45 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.4.1.5][1] | Confirm pre-install measurements and repeat command were recorded | 4 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.5/README.md

<!-- sase:referenced-by:end -->
