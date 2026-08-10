# Bead: sase-il — Canonical sase-size memory and size-driven agent routing

[Bead Pages](../README.md) / sase-il

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wt](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wt/README.md) · **Assignee:** `sase-il.land`
**Created:** 2026-08-09 16:43:06 EDT
**Plan:** [202608/sase\_sizes\_memory.md](https://github.com/sase-org/sase--plans/blob/main/202608/sase_sizes_memory.md)

## Description

One generated long-term memory note owns every sase-size instruction, tale plans carry a validated `size`, and coder follow-ups route through the size-specific phase-worker aliases instead of the retired coder alias bucket.

## Notes

[2026-08-10T12:33:26Z · sase-ik.land] DISCOVERED ISSUE: `just check-full` on clean master during sase-ik landing verification fails deterministically at committed-plan validation: `202608/new_task_recent_task_sweep.md:1: error [tale-size-missing] required tale field size is missing`. The plan was committed in 59ea423c6 at 2026-08-09 17:55, after phase sase-il.3 made tale size mandatory in sase/core (46fbdc07a / 3c10a0cb7 at 17:43). This is causally linked to the active size-adoption epic, not glossary epic sase-ik; it blocks every full check before the test-cost lane. Add an intentional tale size or otherwise migrate the committed plan, then rerun committed-plan validation.

[2026-08-10T12:41:43Z · sase-ib.land] DISCOVERED ISSUE (independent reproduction): the tale-size-missing failure also blocks plain `just check`, not only `just check-full`. Reproduced on 2026-08-10 while landing epic sase-ib in workspace sase_11 with only that epic's landing diff applied: every lint gate and SASE validation passed, then validate-committed-plans failed with `202608/new_task_recent_task_sweep.md:1: error [tale-size-missing]` (3548 files, 180 strict, 1 error) and `just check` exited 1 before its scoped test lane ever ran. Corroborates the 2026-08-10T12:33:26Z note from sase-ik.land; no task bead filed.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-il.1](sase-il.1.md) | Robust long-note parent support | ✓ closed | medium | 2026-08-09 | 1 | 1 |
| [sase-il.2](sase-il.2.md) | Generated sase\_sizes.md memory note | ✓ closed | medium | 2026-08-09 | 1 | 1 |
| [sase-il.3](sase-il.3.md) | Required tale size in sase-core | ✓ closed | medium | 2026-08-09 | 1 | 3 |
| [sase-il.4](sase-il.4.md) | Adopt tale size in sase | ✓ closed | medium | 2026-08-09 | 1 | 1 |
| [sase-il.5](sase-il.5.md) | Retire the coder alias bucket | ◐ in_progress | large | 2026-08-09 | 1 | 0 |
| [sase-il.6](sase-il.6.md) | Verify plan handoff for large task beads | ✓ closed | small | 2026-08-09 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-il: Canonical sase-size memory and size-driven agent routing [in_progress]"]
    n1["sase-il.1: Robust long-note parent support [closed]"]
    n2["sase-il.2: Generated sase_sizes.md memory note [closed]"]
    n3["sase-il.3: Required tale size in sase-core [closed]"]
    n4["sase-il.4: Adopt tale size in sase [closed]"]
    n5["sase-il.5: Retire the coder alias bucket [in_progress]"]
    n6["sase-il.6: Verify plan handoff for large task beads [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n1 -.-> n2
    n2 -.-> n4
    n3 -.-> n4
    n4 -.-> n5
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-il.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-il.1/README.md) | [sase-il.1](sase-il.1.md) | 1 |
| [bbugyi200.athena.sase-il.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-il.2/README.md) | [sase-il.2](sase-il.2.md) | 1 |
| [bbugyi200.athena.sase-il.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-il.3/README.md) | [sase-il.3](sase-il.3.md) | 3 |
| [bbugyi200.athena.sase-il.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-il.4/README.md) | [sase-il.4](sase-il.4.md) | 1 |
| [bbugyi200.athena.sase-il.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-il.5/README.md) | [sase-il.5](sase-il.5.md) | 0 |
| [bbugyi200.athena.sase-il.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-il.6/README.md) | [sase-il.6](sase-il.6.md) | 1 |
| [bbugyi200.athena.sase-il.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-il.land/README.md) | [sase-il](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2f71b6b`](https://github.com/sase-org/sase/commit/2f71b6bc4d5ee19ea44bc7afbad605bc99abe7d5) | test: cover plan handoff in task launch path | [sase-il.6](sase-il.6.md) | 2026-08-09 17:26:10 EDT |
| sase | [`f21c8d8`](https://github.com/sase-org/sase/commit/f21c8d8504cb60788aba13dcb4c0f28081662c3b) | feat(memory): support long-note parent metadata | [sase-il.1](sase-il.1.md) | 2026-08-09 17:34:01 EDT |
| sase-core | [`sase-core@3c10a0c`](https://github.com/sase-org/sase-core/commit/3c10a0cb7b8a222503440760f946b2cdfef15beb) | feat!: require tale size in core plan validation | [sase-il.3](sase-il.3.md) | 2026-08-09 17:41:09 EDT |
| sase--plans | [`sase--plans@97845e6`](https://github.com/sase-org/sase--plans/commit/97845e6e0c04dc551b67e2cf275da9a5bfb4f330) | chore(plans): backfill tale sizes for committed plans | [sase-il.3](sase-il.3.md) | 2026-08-09 17:42:23 EDT |
| sase | [`46fbdc0`](https://github.com/sase-org/sase/commit/46fbdc07a158cb4f97ce2c70913dd146fb6b0cc8) | feat!: require tale size in SASE plan validation | [sase-il.3](sase-il.3.md) | 2026-08-09 17:43:43 EDT |
| sase | [`f42a68c`](https://github.com/sase-org/sase/commit/f42a68c074088ec05e1a804659e2abc54a2c458d) | feat(memory): generate SASE size guidance note | [sase-il.2](sase-il.2.md) | 2026-08-10 07:47:42 EDT |
| sase | [`b9008c5`](https://github.com/sase-org/sase/commit/b9008c535c4c0fd3bb4f199284c1a8369b2fd9f2) | feat(plan): normalize legacy tale size for launches | [sase-il.4](sase-il.4.md) | 2026-08-10 08:47:40 EDT |
