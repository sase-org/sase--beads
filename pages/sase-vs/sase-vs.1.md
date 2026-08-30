# Bead: sase-vs.1 — Shared wait-spec parser and \`sase bead work --wait\`

[Bead Pages](../README.md) / [sase-vs](README.md) / sase-vs.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ga](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ga.md) · **Assignee:** `sase-vs.1` · **Size:** medium
**Created:** 2026-08-30 07:21:58 EDT · **Closed:** 2026-08-30 08:06:06 EDT
**Plan:** [202608/approval\_wait\_argument.md](https://github.com/sase-org/sase--plans/blob/main/202608/approval_wait_argument.md)

## Description

bead_work_wait: add the shared `agent,bead=<id>` wait-spec parser and a `sase bead work -w/--wait` option that renders the extra waits onto every unblocked epic segment.

## Notes

[2026-08-30T12:06:06Z · sase-vs.1] Added shared wait_spec parser and sase bead work --wait. Verified parser accept/reject cases, extra waits render only on unblocked root and land-only segments (not dependents), invalid specs exit 2 without launching or mutating beads, dry-run preview stamps %w on the root wave, and just check passed.

## Dependencies

- **Blocks:** [sase-vs.3](sase-vs.3.md) ✓ · ⧖ 2026-08-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-vs.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-vs.1/README.md) | [sase-vs.1](sase-vs.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9c5cbea`](https://github.com/sase-org/sase/commit/9c5cbeac56ea753c88550e8095016f2c3a5a153b) | feat(bead): add wait-spec parser and sase bead work --wait | [sase-vs.1](sase-vs.1.md) | 2026-08-30 08:07:54 EDT |
