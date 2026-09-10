# Bead: sase-za.1 — Capacity-only artifact scan in the Rust core

[Bead Pages](../README.md) / [sase-za](README.md) / sase-za.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ih](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ih.md) · **Assignee:** `sase-za.1` · **Size:** medium
**Created:** 2026-09-10 11:44:16 EDT · **Closed:** 2026-09-10 12:30:01 EDT
**Plan:** [202609/host\_resource\_diet.md](https://github.com/sase-org/sase--plans/blob/main/202609/host_resource_diet.md)

## Description

capacity-scan-mode: add an additive sase-core scan option that skips done artifact dirs before parsing and returns only running/waiting records, exposed through the scan-options wire and sase_core_rs with Rust tests and the revision-pin bump.

## Notes

[2026-09-10T16:30:01Z · sase-za.1] Auto-closed by `sase stitch create` after create_commit landed ae07c41f4 ("feat(core): add capacity_only mode to agent scan wire"). No verification is implied by this note. Reopen with `sase bead open sase-za.1`, or pass `-B|--do-not-close-bead` on mid-flight commits.

## Dependencies

- **Blocks:** [sase-za.2](sase-za.2.md) ◐ · ⧖ 2026-09-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-za.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-za.1/README.md) | [sase-za.1](sase-za.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@161206b`](https://github.com/sase-org/sase-core/commit/161206bac94875d1c5aac1be8d89095c85877507) | feat(agent\_scan): add capacity\_only fast path to scanner | [sase-za.1](sase-za.1.md) | 2026-09-10 12:30:34 EDT |
