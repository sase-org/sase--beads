# Bead: sase-b1.6 — Floor bump, docs, snapshots, full check

[Bead Pages](../README.md) / [sase-b1](README.md) / sase-b1.6

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b1.6` · **Size:** small
**Created:** 2026-07-30 01:10:03 UTC · **Closed:** 2026-07-30 02:52:50 UTC
**Plan:** [202607/xprompt\_swarm\_stats.md](https://github.com/sase-org/sase--plans/blob/main/202607/xprompt_swarm_stats.md)

## Description

docs-and-goldens: bump the sase-core-rs floor to the published version containing the swarm kind, add the CHANGELOG entry and documentation updates, refresh the affected Statistics XPrompts PNG goldens, and run the full check plus visual suites.

## Notes

[2026-07-30T02:52:50Z · sase-b1.6] Bumped sase-core-rs floor to >=0.12.16 (release v0.12.16 carries the swarm-kind commit 009036d) in pyproject.toml, refreshed uv.lock (resolves 0.12.17), and updated the declared-minimum assertion in tests/test_sase_core_rs_telemetry_smoke_tool.py; tools/validate_sase_core_rs_version --published-minimum passes. Documented the swarm counting contract in docs/ace.md (kinds workflow/part/swarm, per-child attribution, nested chains, Refs==Runs, forward-only/no backfill). Added a kind=swarm row (#sase/reads) to the Statistics visual fixture and regenerated three goldens (xprompts, xprompts_model, xprompts_narrow) after inspecting each diff. just check passes (fmt, all lint incl. changelog/symvision/toobig, SASE validation, committed plans, test) and just test-visual passes 390/390. Did NOT hand-edit CHANGELOG.md: CONTRIBUTING.md and the lint(changelog) gate now forbid it (release-please owns it), so the entry must come from the feat: commit subject. Also added the missing '- **PROMPT:**' link line to four SDD plans (xprompt_swarm_stats, artifacts_files_subtab, bead_and_agent_artifact_refs, copy_as_palette) because a pre-existing plan-links validation failure was blocking just check. Changes are left uncommitted.

## Dependencies

- **Depends on:** [sase-b1.5](sase-b1.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-b1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b1.6/README.md) | [sase-b1.6](sase-b1.6.md) | 2 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`6e35387`](https://github.com/sase-org/sase/commit/6e35387e2ba5564c134ccc7ce1b84c5cd5957850) | feat(xprompts): require sase-core-rs with the swarm xprompt kind | [sase-b1.6](sase-b1.6.md) | 2026-07-30 02:53:56 |
| [`sase--plans@605f113`](https://github.com/sase-org/sase--plans/commit/605f11382296a5879b404efcb313b5339a4574f5) | fix: add missing PROMPT links to three plans | [sase-b1.6](sase-b1.6.md) | 2026-07-30 02:55:28 |
