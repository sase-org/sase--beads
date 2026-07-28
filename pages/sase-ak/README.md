# Bead: sase-ak — Validate and display %wait agent-tribe references correctly

[Bead Pages](../README.md) / sase-ak

**Status:** ✓ closed · **Resolution:** done · **Type:** plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ak.land`
**Created:** 2026-07-28 21:04:51 UTC · **Closed:** 2026-07-28 22:32:47 UTC
**Plan:** [202607/tribe\_wait\_reference\_validation\_and\_display.md](https://github.com/sase-org/sase--plans/blob/main/202607/tribe_wait_reference_validation_and_display.md)

## Description

A `%wait(@<tribe>)` target is understood end to end: reserved pseudo-tribe references such as `@default` are rejected at launch instead of parking an agent forever, and the ACE Agents tab renders a real tribe wait as a pending-or-bound tribe target instead of a missing agent name.

## Notes

[2026-07-28T22:32:47Z · sase-ak.land] Land audit complete: reserved wait/fork/assignment guards, shared snapshot-driven tribe binding and index delegation, tribe-aware pending/bound detail rendering, and reserved-wait unresolvable row/detail surfaces all remain implemented. Integrated post-epic queued runner-slot rendering by passing tribe bindings while preserving the runner-only lane filter, and removed the temporary reserved-name bridge in favor of the canonical predicate. Verified 214 focused tests, 367 visual tests (1 skipped), and the full suite (23,291 passed, 7 skipped). Formatting, Ruff, mypy, pyscripts, Symvision, and toobig are green; just check stops only on unrelated global provider-skill drift and two unrelated plan-link pairs. Rechecked post-d67de4caf history; the only newer post-plan commit is CI-only.

[2026-07-28T22:35:33Z · sase-ak.land] Finalizer verification: bead already resolved done; focused, visual, and full suites passed, with repository-local gates green.

## Phases

| Bead | Title | Status | Size | Agents | Commits |
|---|---|---|---|---:|---:|
| [sase-ak.1](sase-ak.1.md) | Reject reserved tribe references in wait and fork targets | ✓ closed | small | 0 | 0 |
| [sase-ak.2](sase-ak.2.md) | Shared tribe wait binding resolver | ✓ closed | medium | 0 | 0 |
| [sase-ak.3](sase-ak.3.md) | Tribe-aware wait rendering in the Agents tab | ✓ closed | medium | 0 | 0 |
| [sase-ak.4](sase-ak.4.md) | Surface waits that can never resolve | ✓ closed | small | 0 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-ak: Validate and display %wait agent-tribe references correctly [closed]"]
    n1["sase-ak.1: Reject reserved tribe references in wait and fork targets [closed]"]
    n2["sase-ak.2: Shared tribe wait binding resolver [closed]"]
    n3["sase-ak.3: Tribe-aware wait rendering in the Agents tab [closed]"]
    n4["sase-ak.4: Surface waits that can never resolve [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n1 -.-> n4
    n2 -.-> n3
    n3 -.-> n4
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| bbugyi200.athena.sase-ak.land--code | [sase-ak](README.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`a9cbf16`](https://github.com/sase-org/sase--plans/commit/a9cbf16b70acc759c1ec2fd3b2a031ee64d3171b) | docs: mark tribe wait epic complete | [sase-ak](README.md) | 2026-07-28 22:37:17 |
