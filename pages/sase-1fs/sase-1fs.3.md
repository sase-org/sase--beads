# Bead: sase-1fs.3 — Run bob-cli recovery and prove remote completeness

[Bead Pages](../README.md) / [sase-1fs](README.md) / sase-1fs.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.4s.f1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.4s.f1.md) · **Assignee:** `sase-1fs.3` · **Size:** medium
**Created:** 2026-10-03 12:42:06 EDT · **Closed:** 2026-10-05 10:01:05 EDT
**Plan:** [202610/bob\_cli\_agents\_publication\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202610/bob_cli_agents_publication_recovery.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | file:explicit:f600dfd99e9253a3d3061a92 | attached via sase artifact create --bead |

<!-- sase:links:end -->

## Description

bob_cli_backfill: use the verified host/core versions, recover bob-cli on each relevant owner machine, reconcile missing pages, and record remote and repeat-run evidence.

## Notes

[2026-10-04T00:16:51Z · sase-1fs.3--7] PROPOSED FOLLOW-UP: Recover two Athena child prompts — bbugyi200.athena.0f6 and bbugyi200.athena.research.3f.cdx still have no canonical archive entry, and deferred prompt restore has no local source.

[2026-10-04T00:17:04Z · sase-1fs.3--7] PROPOSED FOLLOW-UP: Repair invalid artifact-link event store — operation_id de29d2e25c1cfb4381f223c44d576f8c was reused for different link events and left seven linked publication requests quarantined; repair only through a supported migration.

[2026-10-04T00:17:18Z · sase-1fs.3--7] PROPOSED FOLLOW-UP: Restore Apollo prompt and research linker publication — bbugyi200.apollo.4w has no recoverable prompt source and research.v/research.05 linker hood publication timed out at 120s, leaving three requests quarantined.

[2026-10-04T00:17:32Z · sase-1fs.3--7] PROPOSED FOLLOW-UP: Reconcile Athena retry diagnostics — 193 retried retired requests still report the known legacy manifest file-set mismatch for bbugyi200.apollo.d; preserve requests and verify paths before further retries.

[2026-10-04T00:17:46Z · sase-1fs.3--7] PROPOSED FOLLOW-UP: Repair the existing Mac prompt artifact reference — validation reports prompts/202609/bbugyi200.kellys_mbp.8.md points to a missing SHA object, plus 62 prompt-unpublished and 28 plan-unresolved warnings; preserve the dirty Mac checkout.

[2026-10-04T00:38:21Z · sase-1fs.3--8] PROPOSED FOLLOW-UP: Resolve existing Symvision unused-public-symbol findings — just check on the clean workspace at b51df19d88d26d43377530c7176cdf8e3c83802f reports format_kill_classification, classify_runner_kill, reset_oom_baseline, oom_kill_evidence, and KillProvenance in src/sase/axe/runner_kill_provenance.py; the file is unchanged from parent 683138e7289897823fbb1178b8febd8e3c0a373c and predates this recovery phase.

## Dependencies

- **Depends on:** [sase-1fs.1](sase-1fs.1.md) ✓ · ⧖ 2026-10-03
- **Depends on:** [sase-1fs.2](sase-1fs.2.md) ✓ · ⧖ 2026-10-03

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1fs.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1fs.3.md) | [sase-1fs.3](sase-1fs.3.md) | 0 |
