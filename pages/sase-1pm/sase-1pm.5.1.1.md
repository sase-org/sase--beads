# Bead: sase-1pm.5.1.1 — Define the shared rebase gate contract in Rust

[Bead Pages](../README.md) / [sase-1pm.5.1](sase-1pm.5.1.md) / sase-1pm.5.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pm.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pm.5.md) · **Assignee:** `sase-1pm.5.1.1` · **Size:** medium
**Created:** 2026-10-29 02:12:58 EDT · **Closed:** 2026-10-29 03:35:45 EDT
**Plan:** [202610/rebased\_stitch\_gate.md](https://github.com/sase-org/sase--plans/blob/main/202610/rebased_stitch_gate.md)

## Description

gate-policy: implement shared gate policy in sase-core, expose and test its Python bindings, and add the thin sase adapter. Own eligibility, changed-path union, pending-context merging, and verdict validation. Keep the gate disabled.

## Notes

[2026-10-29T07:35:22Z · sase-1pm.5.1.1] PROPOSED FOLLOW-UP: Remove stale Symvision --epic-symbol entries for closed sase-1pj.1.1.4 — after this phase fixed its facade symbols, clean check reported release_staging_reservation, staged_handoffs_enabled, and write_staged_handoff as stale; Justfile is unchanged here, the referenced bead is closed, and no existing task bead tracks these names.

[2026-10-29T07:35:45Z · sase-1pm.5.1.1] Implemented the Rust rebase-gate wire/policy and PyO3 bindings, plus the typed Python facade and lazy package exports. Verified: 7 Rust policy tests, 1 binding round-trip test, 2 facade tests, linked sase-core just check, just fix, focused Symvision, and git diff --check passed. Primary just check passed every stage through terminology; its remaining Symvision failure is the three stale --epic-symbol entries for closed sase-1pj.1.1.4, recorded as a PROPOSED FOLLOW-UP. No epic-symbol entries remain for this phase.

## Dependencies

- **Blocks:** [sase-1pm.5.1.2](sase-1pm.5.1.2.md) ✓ · ⧖ 2026-10-29
- **Blocks:** [sase-1pm.5.1.3](sase-1pm.5.1.3.md) ○ · ⧖ 2026-10-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pm.5.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pm.5.1.1/README.md) | [sase-1pm.5.1.1](sase-1pm.5.1.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@60fe51d`](https://github.com/sase-org/sase-core/commit/60fe51d627a6b5df57511d9d9f0388ec39ddc4b7) | feat(vcs): add rebase gate policy bindings | [sase-1pm.5.1.1](sase-1pm.5.1.1.md) | 2026-10-29 03:37:24 EDT |
| sase | [`c76fee2`](https://github.com/sase-org/sase/commit/c76fee2af11dfbad7cb57de9b670b02791b62bc0) | feat(core): add typed rebase gate facade | [sase-1pm.5.1.1](sase-1pm.5.1.1.md) | 2026-10-29 03:42:03 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pm.5.1.1][1] | Need the phase scope, design file, and prior notes before continuing this reserved phase | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pm.5.1.1/README.md

<!-- sase:referenced-by:end -->
