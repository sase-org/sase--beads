# Bead: sase-xe.16.11.7.14.6.7.3 — Finish actual instance replacement and unified cutover checks

[Bead Pages](../README.md) / [sase-xe.16.11.7.14.6.7](sase-xe.16.11.7.14.6.7.md) / sase-xe.16.11.7.14.6.7.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.athena.0jc` · **Assignee:** `sase-xe.16.11.7.14.6.7.3` · **Size:** medium
**Created:** 2026-09-11 09:46:27 EDT · **Closed:** 2026-09-11 12:33:59 EDT
**Plan:** [202609/launch\_recovery\_and\_xe\_closeout.md](https://github.com/sase-org/sase--plans/blob/main/202609/launch_recovery_and_xe_closeout.md)

## Description

acceptance-regressions: complete the captured-old-instance fencing proof, verify the existing successful HTTPS host fixture, resolve unified flag retirement, and reproduce and repair the reported target-picker focus hazard.

## Notes

[2026-09-11T16:33:59Z · sase-xe.16.11.7.14.6.7.3] Verified acceptance-regressions: (1) fleet_mutate_refuses_stale_revision_and_superseded_instance now captures the real old locator, replaces the seeded execution under the same logical identity, reconciles owner state, refuses the captured locator with conflict_already_handled and zero replacement side effects, then accepts the replacement locator; stale-revision remains GONE/gone_stale. (2) worker_trusts_pinned_ca_and_preserves_healthy_host_beside_faults is in released ancestry v0.33.0–v0.34.7 and reran ok. (3) ace_unified_agents Off-branch, registry, and schema are gone; closed orphan flag bead sase-z6; check_feature_flags rule 8 no longer names it (sase-z9 remains, owned by sase-z8). (4) Target-picker cancel/select restore prompt focus; Enter submits the prompt, not bulk stop on a filtered remote list; kill_agent/jump_to_agent_patch are unavailable while the prompt owns keys. cargo clippy -p sase_gateway --tests clean; ruff/mypy clean on the sase tree; just check blocked at _setup by pre-existing missing core binding provider_usage_normalize_grok_billing.

## Dependencies

- **Depends on:** [sase-xe.16.11.7.14.6.7.1](sase-xe.16.11.7.14.6.7.1.md) ✓ · ⧖ 2026-09-11
- **Depends on:** [sase-xe.16.11.7.14.6.7.2](sase-xe.16.11.7.14.6.7.2.md) ✓ · ⧖ 2026-09-11
- **Blocks:** [sase-xe.16.11.7.14.6.7.4](sase-xe.16.11.7.14.6.7.4.md) ◐ · ⧖ 2026-09-11

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`94c5a87`](https://github.com/sase-org/sase/commit/94c5a875d90f41c3d50ae2b05e4aa787b9d73f9e) | feat: Finish actual instance replacement and unified cutover checks (sase-xe.16.11.7.14.6.7.3) | [sase-xe.16.11.7.14.6.7.3](sase-xe.16.11.7.14.6.7.3.md) | 2026-09-11 13:34:40 EDT |
