# Bead: sase-fq.8.1 — Identify the OS error behind the scratch-file failure on a CI runner

[Bead Pages](../README.md) / [sase-fq.8](sase-fq.8.md) / sase-fq.8.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-fq.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fq.land/README.md) · **Assignee:** `sase-fq.8.1` · **Size:** medium
**Created:** 2026-08-06 07:05:06 EDT · **Closed:** 2026-08-06 07:35:14 EDT
**Plan:** [202608/artifact\_ref\_scratch\_failure.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_ref_scratch_failure.md)

## Description

scratch-probe: land a diagnostic that makes the next master CI run report the actual OS error and resource state behind CommitLogFailure::Scratch, and record the answer in the phase notes.

## Notes

[2026-08-06T11:36:20Z · sase-fq.8.1] SCRATCH-PROBE LANDED: tests/_scratch_resource_probe.py reports the scratch-file resource state (TMPDIR + permissions, statvfs free blocks/inodes, RLIMIT_NOFILE, open-fd count and fd-target histogram, live tempfile.TemporaryFile() and os.dup() attempts with errno) and test_commit_completion_rows_match_shared_inventory_and_resolve prints it and attaches it to the assertion message whenever either inventory comes back empty. Parity assertion unchanged. Landed via PR https://github.com/sase-org/sase/pull/278 (branch sase_fq_8_1_scratch_probe_1) rather than a direct master push, per user decision, so CI runs the probe on pull_request without putting a diagnostic-only commit on master. Verified locally: just lint green, just test-scoped green (25837 passed, 7 skipped), targeted probe+catalog tests green.

[2026-08-06T11:37:13Z · sase-fq.8.1] LOCAL REPRODUCTION: the CI stderr message is reproducible locally from BOTH live candidates, and they are indistinguishable in the current message. (1) EMFILE/errno 24 -- lowering RLIMIT_NOFILE to just above the live fd count and exhausting it makes both tempfile.TemporaryFile() and os.dup() fail with errno 24, which is exactly the pair of syscalls behind CommitLogFailure::Scratch (tempfile::tempfile() = open, try_clone() = dup). Covered as a regression test in tests/ace/tui/widgets/test_artifact_ref_scratch_probe.py::test_report_names_emfile_when_descriptors_are_exhausted. (2) ENOSPC/errno 28 -- pointing TMPDIR at an inode-exhausted filesystem produces the same CommitLogFailure::Scratch message, including the misleading "check that TMPDIR exists and is writable" advice, while the directory is present and writable. Because sase-core discards the io::Error, the message cannot tell these apart; that is why the probe has to run on a real GitHub runner to settle it.

## Dependencies

- **Blocks:** [sase-fq.8.2](sase-fq.8.2.md) ✓ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fq.8.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-fq.8.1.md) | [sase-fq.8.1](sase-fq.8.1.md) | 0 |
