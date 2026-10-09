# Bead: sase-1i5.9.1.2.1.5 — Resolve the live unused-public backlog and any newly exposed lint failures

[Bead Pages](../README.md) / [sase-1i5.9.1.2.1](sase-1i5.9.1.2.1.md) / sase-1i5.9.1.2.1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1i5.9.1.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1i5.9.1.2.md) · **Assignee:** `sase-1i5.9.1.2.1.5` · **Size:** medium
**Created:** 2026-10-08 14:54:14 EDT · **Closed:** 2026-10-08 19:28:21 EDT
**Plan:** [202610/release\_master\_and\_full\_ci.md](https://github.com/sase-org/sase--plans/blob/main/202610/release_master_and_full_ci.md)

## Description

symvision: re-inventory lint after functional repairs, privatize in-file-only definitions, remove dead definitions, preserve real external consumers, and resolve every release-blocking lint error without new pragmas or suppressions.

## Notes

[2026-10-08T22:14:36Z · sase-1i5.9.1.2.1.5--1] PROPOSED FOLLOW-UP: test_directive_completion_includes_representative_descriptions expects short %auto description but sase-core 0.37.0 emits long description; reproduces identically on clean base (same assertion diff), needs test expectation update to core metadata.rs:784 or core window ratchet

[2026-10-08T22:14:41Z · sase-1i5.9.1.2.1.5--1] PROPOSED FOLLOW-UP: test_macro_string_literals_avoid_xprompt_terms flags tests/test_plugin_commands_mount.py:124 assert "xprompt" in reserved (KNOWN witness 477276a723e911ef2ce08d5f4e412d7f); reproduces identically on clean base TOTAL 1, needs allowlist entry or reserved-name assertion rework

[2026-10-08T23:28:21Z · sase-1i5.9.1.2.1.5--1] Closed by explicit `sase stitch create -B close` after create_commit landed 1fedb63427 ("feat(symvision): privatize in-file-only symbols and remove dead definitions"). The commit author requested bead completion after verifying the bead scope. Reopen with `sase bead open sase-1i5.9.1.2.1.5` if more work remains.

## Dependencies

- **Depends on:** [sase-1i5.9.1.2.1.1](sase-1i5.9.1.2.1.1.md) ✓ · ⧖ 2026-10-08
- **Depends on:** [sase-1i5.9.1.2.1.2](sase-1i5.9.1.2.1.2.md) ✓ · ⧖ 2026-10-08
- **Depends on:** [sase-1i5.9.1.2.1.3](sase-1i5.9.1.2.1.3.md) ✓ · ⧖ 2026-10-08
- **Depends on:** [sase-1i5.9.1.2.1.4](sase-1i5.9.1.2.1.4.md) ✓ · ⧖ 2026-10-08
- **Blocks:** [sase-1i5.9.1.2.1.6](sase-1i5.9.1.2.1.6.md) ✓ · ⧖ 2026-10-08
- **Blocks:** [sase-1i5.9.1.2.1.7](sase-1i5.9.1.2.1.7.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1i5.9.1.2.1.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1i5.9.1.2.1.5.md) | [sase-1i5.9.1.2.1.5](sase-1i5.9.1.2.1.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1fedb63`](https://github.com/sase-org/sase/commit/1fedb63427b8fc64b872ceed0ad5254d64b2d213) | feat(symvision): privatize in-file-only symbols and remove dead definitions | [sase-1i5.9.1.2.1.5](sase-1i5.9.1.2.1.5.md) | 2026-10-08 19:23:53 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1i5.9.1.2.1.5--1][1] | Need phase scope DECISIONS and design file | 5 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1i5.9.1.2.1.5.md

<!-- sase:referenced-by:end -->
