# Bead: sase-1d7.11 — Cheap fleet reprojection signature computed before projection

[Bead Pages](../README.md) / [sase-1d7](README.md) / sase-1d7.11

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0uc](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0uc.md) · **Assignee:** `sase-1d7.11` · **Size:** medium
**Created:** 2026-09-30 07:18:21 EDT
**Plan:** [202609/unread\_ack\_reliability\_and\_tui\_responsiveness.md](https://github.com/sase-org/sase--plans/blob/main/202609/unread_ack_reliability_and_tui_responsiveness.md)

## Description

fleet-signature-cheap: replace the recursive deep-freeze projection signature with a structural signature from the roster generation and fleet wire revisions, checked before project_clan_tree runs, with host-level freshness fields patched in the header only.

## Notes

[2026-09-30T14:42:30Z · sase-1d7.11] Implemented fleet-signature-cheap: structural pre-projection signature (roster generation + removal generation + per-row wire keys/revisions/status/clan/attention/followed/dispatch + snapshot identities on FleetRowsProjection) checked before project_clan_tree; skip path patches volatile host fields onto live rows + header. Removed _freeze_projection_value/_agents_projection_signature. Inline-verified: standalone probe 21/21, ruff format+check clean, mypy clean on src (test-file mypy Liskov error pre-exists on clean tree, outside src gate). Remaining: cold rust build (extension missing here) + repo tests + idle bench + epic-symbols + close.

## Dependencies

- **Depends on:** [sase-1d7.3](sase-1d7.3.md) ✓ · ⧖ 2026-09-30
- **Depends on:** [sase-1d7.4](sase-1d7.4.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1d7.11](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1d7.11.md) | [sase-1d7.11](sase-1d7.11.md) | 0 |
