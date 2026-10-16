# Bead: sase-1li.1 — sase-core launch claim attaches to visibly closed beads

[Bead Pages](../README.md) / [sase-1li](README.md) / sase-1li.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.4n.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.4n.linker.w0.md) · **Assignee:** `sase-1li.1` · **Size:** medium
**Created:** 2026-10-16 13:03:50 EDT · **Closed:** 2026-10-16 14:26:46 EDT
**Plan:** [202610/closed\_bead\_launch\_attach.md](https://github.com/sase-org/sase--plans/blob/main/202610/closed_bead_launch_attach.md)

## Description

core: teach sase-core's run_claim_launch an optional submission time and run ID; attach to a bead closed at or before submission (status untouched, one CLOSED-BEAD LAUNCH: note by the launching agent, same mutation), refuse later closes as closed_while_queued, keep the legacy error when no submission time is given, and expose the new kwargs on the Python binding with tests.

## Notes

[2026-10-16T18:24:31Z · sase-1li.1] PROPOSED FOLLOW-UP: sase-1gz flake of federation_worker listener_creates_private_socket_and_rejects_symlink under parallel sase-core check; passed in isolation

[2026-10-16T18:26:46Z · sase-1li.1] sase-core run_claim_launch attaches to beads closed at or before submitted_at (status/assignee/resolution/close metadata untouched, one CLOSED-BEAD LAUNCH note by the launching agent, changed=true, noted_ids=[id]); closed_while_queued refuses later closes with no writes; absent submitted_at keeps the legacy closed error; Python binding exposes submitted_at/run_id. Verified: unit attach/refuse/equal-timestamp/invalid-submitted_at/note-format/two-notes, dual-mode cache=replay, mutation-proof family arm, replay goldens byte-identical, Python attach+closed_while_queued, clippy. sase tool run check hit known flake sase-1gz (gateway IPC listener) which passed in isolation. No leftover --epic-symbol entries.

## Dependencies

- **Blocks:** [sase-1li.2](sase-1li.2.md) ✓ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1li.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1li.1/README.md) | [sase-1li.1](sase-1li.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@594faf3`](https://github.com/sase-org/sase-core/commit/594faf31d80af79a148cb67968318b2bfb1a5770) | feat(bead): attach launch claims to beads closed before submission | [sase-1li.1](sase-1li.1.md) | 2026-10-16 14:27:54 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1li.1][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1li.1/README.md

<!-- sase:referenced-by:end -->
