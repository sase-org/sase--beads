# Bead: sase-177.4 — Skill, memory, and decision text for the up-front routing rule

[Bead Pages](../README.md) / [sase-177](README.md) / sase-177.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qc--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qc.md) · **Assignee:** `sase-177.4` · **Size:** medium
**Created:** 2026-09-23 17:47:11 EDT
**Plan:** [202609/muse\_single\_turn\_normalization.md](https://github.com/sase-org/sase--plans/blob/main/202609/muse_single_turn_normalization.md)

## Description

wait-guidance: rewrite sase_monitor and sase_final skill sources, the core-memory SASE Final Declaration template (and its test), and lint_and_test.md so no agent is told to declare-then-wait or to cancel an in-flight command for a monitor; fold in sase-16q; add a companion decision record on adapter harness normalization; regenerate memory; record follow-ups.

## Notes

[2026-09-23T21:54:05Z · sase-177.4] PROPOSED FOLLOW-UP: Mechanical routing in sase tool run — duration class per tool catalog entry plus SASE_PROVIDER_SYNC_CEILING_SECONDS (large, crosses sase-core boundary)

[2026-09-23T21:54:38Z · sase-177.4] PROPOSED FOLLOW-UP: Cheaper monitor hops — successor gets starter reply plus tool-call digest, slot-reservation lease, no post-kill bookkeeping wait (large)

[2026-09-23T21:55:08Z · sase-177.4] PROPOSED FOLLOW-UP: SASE-owned inline-then-escalate for ToolRuns — sase tool run --detach plus ceiling-bounded wait plus monitor join (xlarge, tool roadmap E2)

[2026-09-23T21:55:37Z · sase-177.4] PROPOSED FOLLOW-UP: Muse CLI-update smoke test asserting --enable-shell-tool still accepted and still synchronous with no managed bash (medium)

[2026-09-23T21:56:08Z · sase-177.4] PROPOSED FOLLOW-UP: Per-invocation run.toolset allowlist for Muse remaining async tools (workflow, cron_*, subagent_*, snooze_reminder) only if telemetry shows wait usage

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-177.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-177.4/README.md) | [sase-177.4](sase-177.4.md) | 0 |
