# Bead: sase-vd.4 — VCS release never frees a workspace the family still holds

[Bead Pages](../README.md) / [sase-vd](README.md) / sase-vd.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ft](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ft.md) · **Assignee:** `sase-vd.4` · **Size:** medium
**Created:** 2026-08-28 18:06:20 EDT · **Closed:** 2026-08-28 21:06:45 EDT
**Plan:** [202608/one\_workspace\_per\_agent\_family.md](https://github.com/sase-org/sase--plans/blob/main/202608/one_workspace_per_agent_family.md)

## Description

handoff-safe-vcs-release: make the `#git:`/`#gh:` release step identity-checked and handoff-aware -- release only a claim this run's pid still owns, clear only an occupant record naming this run, and skip both entirely when the turn ended by handing off mechanically to a monitor, gate, proc shell, pipe, or plan proposal whose follow-up will continue in the same checkout.

## Notes

[2026-08-29T01:06:45Z · sase-vd.4] Identity-checked, handoff-aware VCS release: #git and #gh skip both RUNNING release and occupant clear when a pending monitor/gate/pipe/plan/questions handoff marker is present; refuse release unless the matching RUNNING row still names this run's pid; refuse occupant clear unless the marker names this run; refusals are no-ops plus workspace_claims.jsonl records. just check passed (fmt, ruff, mypy, symvision, scoped tests including the new vcs_release, occupant, and running_field expected_pid coverage). sase-github test_gh_workspace_claims.py 29 passed. No --epic-symbol leftovers for sase-vd.4.

## Dependencies

- **Depends on:** [sase-vd.3](sase-vd.3.md) ✓ · ⧖ 2026-08-28
- **Blocks:** [sase-vd.5](sase-vd.5.md) ✓ · ⧖ 2026-08-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-vd.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-vd.4/README.md) | [sase-vd.4](sase-vd.4.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1a14630`](https://github.com/sase-org/sase/commit/1a1463028a7619fa7bcd6ad3331ee640ac5f69c5) | feat(workspace): skip VCS release on handoff and pid mismatch | [sase-vd.4](sase-vd.4.md) | 2026-08-28 21:08:15 EDT |
| sase-github | [`sase-github@2571c9d`](https://github.com/sase-org/sase-github/commit/2571c9d7466d4c6020a87b6ee86068c12170cdab) | feat(workspace): identity-check #gh release and skip on handoff | [sase-vd.4](sase-vd.4.md) | 2026-08-28 21:10:16 EDT |
