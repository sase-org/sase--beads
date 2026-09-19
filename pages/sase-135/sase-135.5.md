# Bead: sase-135.5 — Capture fingerprints, host samples, and recording metrics

[Bead Pages](../README.md) / [sase-135](README.md) / sase-135.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0nm](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0nm.md) · **Assignee:** `sase-135.5` · **Size:** medium
**Created:** 2026-09-18 22:19:23 EDT · **Closed:** 2026-09-19 12:39:24 EDT
**Plan:** [202609/tool\_e1\_named\_tools.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_e1_named_tools.md)

## Description

run-evidence: Implement section 5, including complete-or-explicitly-incomplete pre/post repository fingerprints, bounded probes, PSI/loadavg samples, low-cardinality telemetry, and evidence/concurrency acceptance cases.

## Notes

[2026-09-19T16:39:24Z · sase-135.5] Implemented run-evidence: bounded pre/post fingerprints (git/input/toolchain/env, complete-or-explicitly-incomplete), 10s host samples (loadavg/CPU/PSI-when-available), and low-cardinality ToolRun recording metrics (attempts/errors/settlements; metric catalog 37->40). Finish stores canonical fingerprint_before/after and sets mutated_input only when both fingerprints are complete. Observation failures never change the child.

DEMO: tools/smoke_sase_tool_runs --sase .venv/bin/sase -> dod-6-evidence pass (mutated_input true, dirty.txt, samples, evidence complete); dod-6-samples pass (>=3 samples over 21s, elapsed[-1]>=15s); dod-10-concurrent pass (independent event files); failed=0.
DEMO: sase bead epic-symbols sase-135.5 -> no leftovers. Removed sase-135.5(tool_run_canonicalize_fingerprint) and sase-135.5(tool_run_unknown_evidence) Justfile exemptions after executor/observe started calling them.

Verified: just check passed (lint + scoped suite escalated to full because core-identity-changed/justfile). cargo test -p sase_core tool_run: 27 passed including finish_stores_canonical_fingerprints_and_mutated_input and incomplete_fingerprints_do_not_guess_mutated_input. cargo clippy -p sase_core --all-targets -- -D warnings. tests/tool 69 passed. PSI fields stay null with availability diagnostics when unavailable; never substituted as zero.

## Dependencies

- **Depends on:** [sase-135.4](sase-135.4.md) ✓ · ⧖ 2026-09-18
- **Blocks:** [sase-135.6](sase-135.6.md) ◐ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-135.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-135.5/README.md) | [sase-135.5](sase-135.5.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1f6adf4`](https://github.com/sase-org/sase/commit/1f6adf43bb2b77a52f57c985beb4de1e966dfa8a) | feat(tool): capture ToolRun fingerprints, host samples, and recording metrics | [sase-135.5](sase-135.5.md) | 2026-09-19 12:43:07 EDT |
| sase-core | [`sase-core@e8578c1`](https://github.com/sase-org/sase-core/commit/e8578c1eea01968b7f5cf6a2d9cf9554df5f33c9) | feat(tool-run): persist canonical before/after fingerprints on finish | [sase-135.5](sase-135.5.md) | 2026-09-19 12:46:15 EDT |
