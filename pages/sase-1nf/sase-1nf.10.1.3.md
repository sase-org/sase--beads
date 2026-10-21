# Bead: sase-1nf.10.1.3 — Apply failure scope and bounded selection to commit drains

[Bead Pages](../README.md) / [sase-1nf.10.1](sase-1nf.10.1.md) / sase-1nf.10.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1nf.10](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.10.md) · **Assignee:** `sase-1nf.10.1.3` · **Size:** medium
**Created:** 2026-10-20 15:40:51 EDT · **Closed:** 2026-10-20 19:42:10 EDT
**Plan:** [202610/publication\_drain\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/publication_drain_fixes.md)

## Description

drain-accounting: thread structured failure provenance and selected logical keys through the transaction, charge only attempted hood requests, preserve timeout stage, and cap background drain batches.

## Notes

[2026-10-20T23:42:10Z · sase-1nf.10.1.3] drain-accounting landed: repository failures preserve attempts via decide_publication_failure_accounting, hood timeouts charge only alarm-stage keys, commit batches capped at 25 with preferred new key, ack gated on page/revision/prompt policy, cleanup-after-success keeps drained rows without resurrect. Verification: sase tool run check fb580a8c1547b1b1a7826cb58d1bd92a exit 0 (all lint incl symvision/mypy, scoped tests); focused suites green (commit_publication, queue, bounded_drain, drain_accounting x5, core recovery, drain_measure). Epic-symbols clean.

## Dependencies

- **Depends on:** [sase-1nf.10.1.1](sase-1nf.10.1.1.md) ✓ · ⧖ 2026-10-20
- **Depends on:** [sase-1nf.10.1.2](sase-1nf.10.1.2.md) ✓ · ⧖ 2026-10-20
- **Blocks:** [sase-1nf.10.1.4](sase-1nf.10.1.4.md) ◐ · ⧖ 2026-10-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nf.10.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.10.1.3/README.md) | [sase-1nf.10.1.3](sase-1nf.10.1.3.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:9n--3][1] | Verify unchanged upstream Symvision whitelist is stale after its owning phase closed | 1 |
| read-by | [agent:sase-1nf.10.1.1][2] | Need later-phase consumers so unused facade APIs can be epic-symbol keyed to still-open beads | 1 |
| read-by | [agent:sase-1nf.10.1.3][3] | Need the phase scope and design file | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.9n.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.10.1.1/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.10.1.3/README.md

<!-- sase:referenced-by:end -->
