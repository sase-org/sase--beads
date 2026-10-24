# Bead: sase-1nf.10.1.9.1.1 — Recover Apollo bob-cli unpublished owner content

[Bead Pages](../README.md) / [sase-1nf.10.1.9.1](sase-1nf.10.1.9.1.md) / sase-1nf.10.1.9.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1nf.10.1.9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.10.1.9.md) · **Assignee:** `sase-1nf.10.1.9.1.1` · **Size:** medium
**Created:** 2026-10-21 07:39:04 EDT · **Closed:** 2026-10-21 07:54:57 EDT
**Plan:** [202610/publication\_recovery\_proof.md](https://github.com/sase-org/sase--plans/blob/main/202610/publication_recovery_proof.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | file:explicit:011580d597e093d5de392dca | attached via sase artifact create --bead |
| related | file:explicit:05af6c55b55e24008cbd9f2f | attached via sase artifact create --bead |
| related | file:explicit:5c0712e63bd61170cc2a3b9f | attached via sase artifact create --bead |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

<!-- sase:links:end -->

## Description

apollo-replay: execute the backup-first stale-replay helper, prove unique content reached the remote, and verify repeat apply is a no-op.

## Notes

[2026-10-21T11:54:19Z · sase-1nf.10.1.9.1.1] PROPOSED FOLLOW-UP: stale-replay helper reads upstream blobs through text-mode git output, so bare CR bytes in chats are rewritten to LF before the prefix check (apollo bob-cli 1--mon/2--mon chats byte-identical yet refused, 364 CR bytes). Fix _git_optional_bytes to capture binary and add a regression test with CR-containing fixtures.

[2026-10-21T11:54:33Z · sase-1nf.10.1.9.1.1] PROPOSED FOLLOW-UP: stale-replay prefix-only merge cannot carry one-sided terminal transitions (apollo bob-cli 2--1/6 active-to-completed state.json, extended prompt_steps) even though upstream is untouched since merge-base; apply refuses with backup intact. Add a merge-base-aware keep-local policy in sase-core with fixtures, then re-run apollo-replay apply with the preserved backup.

[2026-10-21T11:54:57Z · sase-1nf.10.1.9.1.1] apollo-replay BLOCKED but preserved: report stage=verified (unknown empty, checksums+bundle OK, backup durable outside clone); apply refused before mutation (identity/content unreconcilable, backup intact) over 5 same-run divergences — 3 genuine one-sided terminal transitions (2--1/6 completed states, extended prompt_steps; upstream untouched since merge-base) + 2 false positives from helper text-mode CR-to-LF mangling of identical chats. Clone verified unchanged (HEAD 2abeff3f9, clean, 1/567). Unique runs 2--2 and 2--mon-0 inventoried with digests, preserved in backup, NOT yet published. Evidence: file:explicit:05af6c55b55e24008cbd9f2f, file:explicit:011580d597e093d5de392dca, file:explicit:5c0712e63bd61170cc2a3b9f. Two PROPOSED FOLLOW-UP notes recorded (binary-safe helper reads; merge-base-aware keep-local policy). No source changes.

## Dependencies

- **Blocks:** [sase-1nf.10.1.9.1.2](sase-1nf.10.1.9.1.2.md) ✓ · ⧖ 2026-10-21

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1nf.10.1.9.1.6.5][1] | Review required parent epic and phase evidence before final acceptance | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.10.1.9.1.6.5/README.md

<!-- sase:referenced-by:end -->
