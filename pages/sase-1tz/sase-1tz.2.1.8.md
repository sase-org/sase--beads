# Bead: sase-1tz.2.1.8 — Rotate tui\_stalls.jsonl, tolerate torn lines, and write fault headers only on faults

[Bead Pages](../README.md) / [sase-1tz.2.1](sase-1tz.2.1.md) / sase-1tz.2.1.8

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.md) · **Assignee:** `sase-1tz.2.1.8` · **Size:** medium
**Created:** 2026-11-19 11:13:27 EST
**Plan:** [202611/noise\_publication\_digests\_tui\_stalls.md](https://github.com/sase-org/sase--plans/blob/main/202611/noise_publication_digests_tui_stalls.md)

## Description

stall_telemetry: tui_stalls.jsonl size-rotates through the shared bounded-append helper and drops its non-atomic in-place prune. Every reader tolerates torn lines, and long stalls get bounded stack re-samples. tui_faults.log gets a header only when a fault actually happens.

## Notes

[2026-11-19T19:54:57Z · sase-1tz.2.1.8] MEASUREMENT (stall_telemetry, before install, read-only, 2026-11-19 ~13:10 EST).
athena: tui_stalls.jsonl 38,343,353 B / 43,366 lines / 0 torn, covering 48.05 h (old prune). Rows: 36,377 tui_gc_pause (34,245 young gen-0/1 'automatic' pauses of 50 ms-0.5 s = 11.3 MB), 2,645 tui_hitch (10.7 MB, ~3.6 KB of it main_thread_stack per row), 2,644 tui_hitch_recovered (8.2 MB). tui_stalls.jsonl.1 2,097,057 B / 1,589 lines / 0 torn (Nov 16). tui_faults.log 16,967 B = 356 session headers, 0 fault dumps.
apollo: tui_stalls.jsonl 16,685,304 B / 7,399 lines / 3 torn (48.1 h). tui_stalls.jsonl.1 2,097,067 B / 1,065 lines / 0 torn. tui_faults.log 14,795 B = 310 headers, 0 dumps.
Slimming, replayed on the live rows (drop young pause rows < 0.5 s; hitch stacks capped at 24 innermost frames, hitch-recovery stacks at 8): athena 19.8 MiB per 48 h, apollo 11.5 MiB per 48 h. So STALL_MAX_BYTES = 24 MiB per segment (one segment alone holds 48 h; ~20% headroom over athena; both segments <= 48 MiB).
Rust perf_logs_query was verified tolerant already (sources.rs skips and counts malformed_skipped; test malformed_timestamp_and_partial_trailing_lines_are_reported). No sase-core change and no pin move.
AFTER INSTALL (both hosts; TUIs must restart): (1) ls -la ~/.sase/logs/tui_stalls.jsonl* ~/.sase/logs/tui_faults.log ~/.sase/logs/tui_faults.d/ (2) torn-line count: python3 - <<'EOF'
import json, glob, os
for p in sorted(glob.glob(os.path.expanduser('~/.sase/logs/tui_stalls.jsonl*'))):
    torn = 0
    for line in open(p, 'rb'):
        try: json.loads(line)
        except json.JSONDecodeError: torn += 1
    print(p, os.path.getsize(p), 'torn', torn)
EOF
(3) no young pause rows below 0.5 s: jq -cR 'fromjson? | select(.event=="tui_gc_pause" and .generation<2 and .duration_s<0.5)' ~/.sase/logs/tui_stalls.jsonl | wc -l, which should be 0 for rows newer than the restart.
Expected after install: the first append rotates the oversize 38 MB active file into .1, dropping the old 2 MB .1. That 38 MB .1 then stays until the new active file reaches 24 MiB (about 48+ h on athena), and after that both segments stay <= 24 MiB. tui_faults.log stops gaining a header per TUI start; tui_faults.d/ holds one empty spool per live TUI.

[2026-11-19T19:55:15Z · sase-1tz.2.1.8] PROPOSED FOLLOW-UP: four KNOWN base-tree test failures seen in just check (run a6d0419fc49515d0e58f88b2544dcf23, witness 203b10da45bc5567b16d396fbb323c64, no owner), unrelated to stall_telemetry — tests/test_macro_terminology.py::test_macro_string_literals_avoid_xprompt_terms (flags %xprompts_enabled literals in tests/turns/test_workspace_retention_agents_scratch.py); tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed (unreviewed site src/sase/agents_sync/publication_scratch.py:sweep_publication_scratch from c756511c11); tests/agents_sync/test_commit_publication_drain_accounting.py::test_cleanup_after_success_does_not_resurrect; tests/fakey/test_gate_capacity_custom_e2e.py::test_synchronous_gate_answer_claims_and_releases_runner_slot_capacity_like_an_agent.

## Dependencies

- **Blocks:** [sase-1tz.2.1.13](sase-1tz.2.1.13.md) ◐ · ⧖ 2026-11-19
- **Blocks:** [sase-1tz.2.1.9](sase-1tz.2.1.9.md) ◐ · ⧖ 2026-11-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.2.1.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.8/README.md) | [sase-1tz.2.1.8](sase-1tz.2.1.8.md) | 0 |
