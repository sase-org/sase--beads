# Bead: sase-1vb.1 — Send Rust the exact release-asset wire shape

[Bead Pages](../README.md) / [sase-1vb](README.md) / sase-1vb.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1ge](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1ge.md) · **Assignee:** `sase-1vb.1` · **Size:** small
**Created:** 2026-11-26 06:30:36 EST · **Closed:** 2026-11-26 06:48:48 EST
**Plan:** [202611/green\_github\_actions.md](https://github.com/sase-org/sase--plans/blob/main/202611/green_github_actions.md)

## Description

steward-wire: drop the transport-only asset id from the release wire, read abandoned-observation asset ids from the raw release, fix the fixtures that encode the wrong shape, and add real-binding regression coverage.

## Notes

[2026-11-26T11:48:48Z · sase-1vb.1] steward-wire done: _release_wire emits only name/kind/generation (id still validated), _fresh_train_abandoned reads raw assets, fixtures fixed, new unit + real-binding regression tests added. Verified: release_watch suites (61+82 passed) and sase tool run check succeeded.

## Dependencies

- **Blocks:** [sase-1vb.6](sase-1vb.6.md) ✓ · ⧖ 2026-11-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vb.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vb.1/README.md) | [sase-1vb.1](sase-1vb.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9bdc604`](https://github.com/sase-org/sase/commit/9bdc6046ab9d67725832c0a910fd606b0b4f3894) | fix(release-steward): send Rust the exact release-asset wire shape | [sase-1vb.1](sase-1vb.1.md) | 2026-11-26 06:50:36 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1vb.1][1] | check notes and remaining work | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vb.1/README.md

<!-- sase:referenced-by:end -->
