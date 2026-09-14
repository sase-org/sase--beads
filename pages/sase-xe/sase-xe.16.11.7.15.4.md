# Bead: sase-xe.16.11.7.15.4 — Publish, ratchet, and verify the new core surface

[Bead Pages](../README.md) / [sase-xe.16.11.7.15](sase-xe.16.11.7.15.md) / sase-xe.16.11.7.15.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.v](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.v.md) · **Assignee:** `sase-xe.16.11.7.15.4` · **Size:** small
**Created:** 2026-09-13 18:38:05 EDT · **Closed:** 2026-09-14 08:37:59 EDT
**Plan:** [202609/remote\_agents\_display\_parity.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_agents_display_parity.md)

## Description

published-core-adoption: wait for release-plz to publish the new core surface, ratchet the pin and dependency floor with supported tools, just install, and verify the installed wheel exposes the new fields before any consumer lands.

## Notes

[2026-09-14T12:37:12Z · sase-xe.16.11.7.15.4--4] PROPOSED FOLLOW-UP: commit 9dbc850062 (refactor(ops): split agent command helpers) silently broke the agent-tribe-terminology allowlist test by moving item.agent_tag serialization from agent.py into a new unlisted file (_agent_revert.py) -- worth a broader audit for other allowlist/file-move drift from that refactor. Note: another agent (bead sase-z4.6.5.4.6) independently landed the identical allowlist fix upstream (commit d2687b6799) before this phase's commit reached master; the rebase absorbed it cleanly with no conflict.

[2026-09-14T12:37:59Z · sase-xe.16.11.7.15.4--4] Verified sase-core-rs 0.34.26 (published, floor already pinned) exposes the wire-parity fields from sase-xe.16.11.7.15.3 (started_at_unix, stopped_at_unix, workspace_num, agent_clan, agent_clan_generation, clan_tribe, tribe, labels.project_label) by force-installing the published PyPI wheel and probing fleet_project_resolved_agent_summary(); tools/validate_sase_core_rs and tools/validate_sase_core_rs_version --published-minimum both exit 0. Ran tools/ratchet_core_revision, pinning sase-core-revision.txt to sase-core remote HEAD a35b18220fb3 (release-plz version-bump-only commit). Along the way fixed two unrelated pre-existing just-check blockers found while verifying: (1) a symvision false positive on src/sase/monitor/store_lane.py (relative 'from . import store' defeats symvision's alias tracking; switched to absolute import, no behavior change); (2) the test_agent_tribe_terminology.py allowlist was stale after commit 9dbc850062 moved agent_tag serialization into _agent_revert.py (another agent landed the same fix upstream via bead sase-z4.6.5.4.6 before our commit reached master; rebase absorbed it cleanly). Committed as three separate commits via /sase_git_commit (7e922da666, d699f2761a, plus the third change already present via the absorbed upstream commit). Full 'just check' (lint/type/test) ran green (exit 0) against this exact tree state prior to committing. No --epic-symbol entries for this phase. Working tree clean, pushed, up to date with origin/master.

## Dependencies

- **Depends on:** [sase-xe.16.11.7.15.3](sase-xe.16.11.7.15.3.md) ✓ · ⧖ 2026-09-13
- **Blocks:** [sase-xe.16.11.7.15.5](sase-xe.16.11.7.15.5.md) ✓ · ⧖ 2026-09-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-xe.16.11.7.15.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-xe.16.11.7.15.4.md) | [sase-xe.16.11.7.15.4](sase-xe.16.11.7.15.4.md) | 3 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`631e0b5`](https://github.com/sase-org/sase/commit/631e0b510d89ce4fdaa224e9cad3b601c8b3b0ee) | chore(core): ratchet sase-core revision pin to published v0.34.25 | [sase-xe.16.11.7.15.4](sase-xe.16.11.7.15.4.md) | 2026-09-13 22:01:58 EDT |
| sase | [`7e922da`](https://github.com/sase-org/sase/commit/7e922da66631b2283ae2d31626abf3acaf4d4c59) | chore(core): ratchet sase-core-revision.txt to a35b18220fb3 | [sase-xe.16.11.7.15.4](sase-xe.16.11.7.15.4.md) | 2026-09-14 08:26:43 EDT |
| sase | [`d699f27`](https://github.com/sase-org/sase/commit/d699f2761a4da7ec0387ff1a10ee5e3cea0563f5) | fix(monitor): use absolute import for store module in store\_lane.py | [sase-xe.16.11.7.15.4](sase-xe.16.11.7.15.4.md) | 2026-09-14 08:32:09 EDT |
