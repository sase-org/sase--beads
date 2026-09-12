# Bead: sase-zq.2 — Enforce and carry the decision through every commit path

[Bead Pages](../README.md) / [sase-zq](README.md) / sase-zq.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0jp](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0jp.md) · **Assignee:** `sase-zq.2` · **Size:** medium
**Created:** 2026-09-11 15:33:37 EDT · **Closed:** 2026-09-12 10:43:24 EDT
**Plan:** [202609/explicit\_bead\_action.md](https://github.com/sase-org/sase--plans/blob/main/202609/explicit_bead_action.md)

## Description

integrate_policy: replace the opt-out CLI, enforce preflight and resume rules, carry declared choices through host finalization, and migrate callers, skill sources, documentation, and focused tests together.

## Notes

[2026-09-12T11:04:43Z · sase-zm.1] DISCOVERED ISSUE from sase-zm.1: Justfile _lint-symvision now whitelists FinalizerAssignedBeadWire and finalizer_assigned_bead_from_dict as --epic-symbol sase-zq.2(...). sase-zq.1 exported them for this phase and closed without the whitelist, which made just check red repo-wide. Consume them from a non-test src caller or drop the Justfile entries when they are no longer public-without-consumer.

[2026-09-12T14:43:24Z · sase-zq.2] Implemented explicit bead_action enforcement through stitch, resume, finalizer declarations, docs, skills, and tests. Verified: sase bead epic-symbols sase-zq.2 (no entries); just check (passed, scoped lane escalated to full suite due packaging-config).

## Dependencies

- **Depends on:** [sase-zq.1](sase-zq.1.md) ✓ · ⧖ 2026-09-11
- **Blocks:** [sase-zq.3](sase-zq.3.md) ◐ · ⧖ 2026-09-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zq.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zq.2/README.md) | [sase-zq.2](sase-zq.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`df33453`](https://github.com/sase-org/sase/commit/df33453b7f9b0012f549b64174d9364e05889da5) | feat(commit): require explicit bead action | [sase-zq.2](sase-zq.2.md) | 2026-09-12 10:45:26 EDT |
