# Bead: sase-lb.1.5 — Follow-up and family-attach launches never pair workspace 0 with a numbered directory

[Bead Pages](../README.md) / [sase-lb.1](sase-lb.1.md) / sase-lb.1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.015](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.015.md) · **Assignee:** `sase-lb.1.5` · **Size:** medium
**Created:** 2026-08-14 11:10:42 EDT · **Closed:** 2026-08-14 12:21:01 EDT
**Plan:** [202608/workspace\_claim\_invariant.md](https://github.com/sase-org/sase--plans/blob/main/202608/workspace_claim_invariant.md)

## Description

followup: normalize workspace number and directory together in the monitor follow-up and family-attach launch paths so a degraded launch moves out of the numbered workspace instead of squatting in it unclaimed.

## Notes

[2026-08-14T16:21:01Z · sase-lb.1.5] Added resolve_consistent_workspace_pair() to workspace_provider/lookup.py enforcing the corollary that workspace_num==0 may only pair with the primary checkout. Wired it into monitor/followup.py::launch_followup_agent (repairs meta pairing before the normal/degraded prompt is composed, degraded-#0 fallback now names the primary directory) and agent/_family_attach_launch.py::prepare_family_attach_launch (repairs parent pairing in both the deferred and preallocated branches, raises FamilyAttachError when unresolvable). Added/extended tests in test_workspace_lookup.py, test_monitor_followup.py, and test_dynamic_agent_family_attach_resolution.py covering: normal claim inheritance, meta-pairing repair via registry, fallback to primary with an informative degraded reason, family-attach repair for both deferred and preallocated branches, and fail-loudly on an unresolvable pair. Verified with 'just check' (fmt, ruff, mypy, pyscripts, symvision, keep-sorted, SASE validation, scoped tests) — all green, exit 0.

## Dependencies

- **Depends on:** [sase-lb.1.1](sase-lb.1.1.md) ✓ · ⧖ 2026-08-14
- **Depends on:** [sase-lb.1.2](sase-lb.1.2.md) ✓ · ⧖ 2026-08-14
- **Blocks:** [sase-lb.1.7](sase-lb.1.7.md) ✓ · ⧖ 2026-08-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-lb.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-lb.1.5/README.md) | [sase-lb.1.5](sase-lb.1.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b00c8a5`](https://github.com/sase-org/sase/commit/b00c8a5f2672a0ff11550af31e0c532b60809767) | fix: repair workspace 0/directory pairing in followup and family-attach launches | [sase-lb.1.5](sase-lb.1.5.md) | 2026-08-14 12:21:39 EDT |
