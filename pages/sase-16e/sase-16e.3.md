# Bead: sase-16e.3 — Last-resort workspace re-creation and non-holding setup failures

[Bead Pages](../README.md) / [sase-16e](README.md) / sase-16e.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pc](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pc.md) · **Assignee:** `sase-16e.3` · **Size:** medium
**Created:** 2026-09-22 12:13:31 EDT · **Closed:** 2026-09-22 16:59:11 EDT
**Plan:** [202609/self\_healing\_workspace\_prep.md](https://github.com/sase-org/sase--plans/blob/main/202609/self_healing_workspace_prep.md)

## Description

reclone: when in-place healing still fails, rescue and move the numbered checkout aside, re-materialize it from the primary checkout, chdir into it, and prepare it once more (launch, retry, and linked-repo paths); release rather than hold workspaces whose setup ultimately failed.

## Notes

[2026-09-22T20:58:25Z · sase-16e.3] PROPOSED FOLLOW-UP: just check is red on stale --epic-symbol entries for closed bead sase-16j.3 (AgentActionChoice, AgentActionChooserModal, GateNotificationIndex) — another epic land agent should drop the entries and clean up the symbols

[2026-09-22T20:59:11Z · sase-16e.3] Reclone implemented and verified: recreate_managed_workspace rescues/re-materializes numbered checkouts; launch+retry+linked paths re-prep once after eligible failures; final setup failures tag setup_workspace_failed (non-hold). 11 new tests in test_axe_runner_workspace_reclone.py pass plus 101 neighbor tests; ruff/mypy clean. just check symvision fails only on pre-existing stale sase-16e.3-unrelated sase-16j.3 epic-symbol entries (noted as follow-up).

## Dependencies

- **Depends on:** [sase-16e.2](sase-16e.2.md) ✓ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16e.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16e.3/README.md) | [sase-16e.3](sase-16e.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`505934a`](https://github.com/sase-org/sase/commit/505934a639b318b995bab43a98925e67150e4705) | feat(axe): re-create managed workspace with reclone on preparation failure | [sase-16e.3](sase-16e.3.md) | 2026-09-22 17:02:04 EDT |
