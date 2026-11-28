# Bead: sase-1vn.4 — Host-owned liveness for zombie epics

[Bead Pages](../README.md) / [sase-1vn](README.md) / sase-1vn.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1h5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1h5.md) · **Assignee:** `sase-1vn.4` · **Size:** large
**Created:** 2026-11-27 10:21:04 EST · **Closed:** 2026-11-28 02:25:39 EST
**Plan:** [202611/backlog\_epic\_1.md](https://github.com/sase-org/sase--plans/blob/main/202611/backlog_epic_1.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | file:explicit:2195f969cb91f0108061888d | attached via sase artifact create --bead |
| related | file:explicit:95fcc65660f2a5ea7525e495 | attached via sase artifact create --bead |

<!-- sase:links:end -->

## Description

zombie-epics: detect in_progress plan beads whose children are all closed and whose land agent is gone, report today's zombies, and recover per zombie_recovery (sase-12u).

## Notes

[2026-11-28T03:14:36Z · sase-1vn.4.1.2] Reporting phase live inventory (2026-11-28T03:12Z, core pin 91380657): sase bead zombies on the canonical sase store reports 33 zombie(s), 6 unknown, 2 owned, 90 not-zombie. Examples sase-zu and sase-zn are both still zombies (all descendants closed, child_landed, recovery eligible). Full report: file:explicit:95fcc65660f2a5ea7525e495. No bead was armed, claimed, launched, closed, or reopened.

[2026-11-28T06:40:36Z · sase-1vn.4.1.5] Zombie liveness phase evidence: read-only all-project report file:explicit:2195f969cb91f0108061888d (generated 2026-11-28T06:37:17Z) covered 11 projects and 162 plans: 38 recovery-eligible zombies, 2 owned, 15 unknown, 107 not zombies. The roost project store was not materialized and is recorded as a collection failure; all other project reports loaded. No historical bead rows were modified.

[2026-11-28T07:23:21Z · sase-1vn.4.1.land] PHASE VERIFIED by the sase-1vn.4.1 land agent. Child epic sase-1vn.4.1 completes this phase's scope. Detect: the shared core predicate needs an in_progress plan, a complete descendant tree with every descendant closed, and no session owner. Report: sase bead zombies (compact/json, -a) plus the TUI stranded badge; live inventories are attached here. Recover per zombie_recovery=relaunch: the epic_liveness AXE job relaunches only the land agent through a durable, guarded proc. sase-1vn.4.1 closes through host completion after its landing commit, and that close cascade-closes this phase (delegated work landed). Tested invariants for the outer land agent: (a) arming is report-only, and closes at or before the cutoff stay historical; (b) one claim per (project, epic, close-event token), created only if absent and published before launch; a losing or foreign host never launches and claims are never transferred; (c) proc id and fingerprint are deterministic per claim, so crash replay resumes the same request and a terminal proc stays consumed (no relaunch); (d) a close-token guard at launch_epic_bead_work aborts if a child reopened, an owner appeared, or the token changed, so recovery never launches phase workers; (e) 120s settlement grace, 30s budget, at most 1 submission per pass across all projects, fair restart-safe cursors; (f) unknown evidence, non-epic tiers, and owned plans are report-only; (g) nothing closes a plan bead automatically. No recovery proc has run (sase proc list -a -t epic-recovery is empty). Not closed per plan: sase-1vn and sase-12u; the evidence above is for the outer land agent's triage of sase-12u. Follow-ups filed: sase-1vv (sase-core query_cache timing flake), sase-1vw (admission overlap flake), sase-1vx (countdown-tick GC flake); the refresh_warmup_gc flake is already owned by sase-1v2.

## Dependencies

- **Depends on:** [sase-1vn.3](sase-1vn.3.md) ✓ · ⧖ 2026-11-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vn.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1vn.4.md) | [sase-1vn.4](sase-1vn.4.md) | 0 |
