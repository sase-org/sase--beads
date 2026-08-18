# Bead: sase-pv — A feature flag is a task bead, not a bead type

[Bead Pages](../README.md) / sase-pv

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.06a](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.06a.md) · **Assignee:** `sase-pv.land`
**Created:** 2026-08-18 11:26:02 EDT
**Plan:** [202608/flag\_task\_type.md](https://github.com/sase-org/sase--plans/blob/main/202608/flag_task_type.md)

## Description

SASE feature flags stop being a bespoke bead type and become ordinary task beads of a project-local `flag` task type whose required fields force every new flag to record what its two branches do and what has to be true before the losing branch is deleted. The `flag` issue type, `FlagRecord`, and `BeadFlagWire` are gone; only `beta` and `sunset` kinds survive; and the five live flag beads are migrated in place.

## Notes

[2026-08-18T19:25:37Z · sase-ps.land] DISCOVERED ISSUE: three tests fail deterministically on master a2357e214, all from this epic's flag-CLI rebuild (98b27e849 'feat(feature-flags)!: collapse flag kinds and rebuild flag new on typed task beads' / c5a0dcf4a 'feat(flags): read flag identity and due-ness from task fields').

REPRODUCTION (workspace sase_14, clean tree at a2357e214, after 'just install'). Serial run, no parallelism, 2.60s — not the full-parallel-lane flake that task sase-pr describes:
  .venv/bin/python -m pytest -q -n 0 tests/feature_flags/test_integrity.py::test_kind_mismatch_when_default_disagrees_with_kind tests/completion/test_snapshot.py
  -> 3 failed, 2 passed

1) tests/feature_flags/test_integrity.py::test_kind_mismatch_when_default_disagrees_with_kind
   TypeError: demo_flag() got an unexpected keyword argument 'default' (tests/feature_flags/test_integrity.py:34). The test helper's signature no longer accepts 'default' after the kind collapse; the test was not updated with it.

2+3) tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift and ::test_current_structural_view_matches_checked_in_snapshot
   The checked-in CLI completion snapshot (tests/completion/snapshots/cli_spec.json) is stale. I diffed it structurally against the live argparse tree: no commands or options changed anywhere in the CLI except under 'sase flag new', where every difference is this epic's — kind choices went from 4 to 2 with 'ops' replaced by 'sunset'; '-r/--remove-by' became '--remove-when'; '-s/--scope' became '--when-disabled'; '-z/--size' became '--remove-when'; a '--when-enabled' option was added; the option count went 6 -> 8; and the description digest moved efa8d71a3d020af7 -> bebc50f4c03bd8c8. Regenerate with 'just' recipe at Justfile:310 / tools/sync_completion_spec.

IMPACT: 'just check-full' and any full 'just test' are red for every agent until these are fixed; 'just check' is red for anyone whose scoped selection reaches either file.

FOUND BY the sase-ps land agent (2026-08-18) during that epic's landing verification: a full 'just test' on a2357e214 gave 3 failed, 33525 passed, 13 skipped, and these were the only three. sase-ps (runner-slot occupancy) touches no flag or completion code, and all 105 runner-slot tests pass on the same tree. Recorded here rather than as a task because this epic is active and owns the change.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-pv.1](sase-pv.1.md) | Free the \`flag\` task-type slug | ✓ closed | small | 2026-08-18 | 1 | 2 |
| [sase-pv.2](sase-pv.2.md) | Declare the \`flag\` task type in project config | ✓ closed | small | 2026-08-18 | 1 | 1 |
| [sase-pv.3](sase-pv.3.md) | Two kinds, a derived default, and a rebuilt \`sase flag new\` | ✓ closed | medium | 2026-08-18 | 1 | 1 |
| [sase-pv.4](sase-pv.4.md) | Due-ness, identity, and integrity read task-type fields | ✓ closed | medium | 2026-08-18 | 1 | 2 |
| [sase-pv.5](sase-pv.5.md) | FlagTriage is a task-bead gate | ✓ closed | medium | 2026-08-18 | 1 | 1 |
| [sase-pv.6](sase-pv.6.md) | Every bead surface renders a flag as a typed task | ✓ closed | medium | 2026-08-18 | 1 | 1 |
| [sase-pv.7](sase-pv.7.md) | Migrate the five live flag beads | ◐ in_progress | medium | 2026-08-18 | 1 | 0 |
| [sase-pv.8](sase-pv.8.md) | Delete the \`flag\` issue type end to end | ◐ in_progress | medium | 2026-08-18 | 1 | 0 |
| [sase-pv.9](sase-pv.9.md) | Memory notes, generated instructions, and documentation | ◐ in_progress | medium | 2026-08-18 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-pv: A feature flag is a task bead, not a bead type [in_progress]"]
    n1["sase-pv.1: Free the `flag` task-type slug [closed]"]
    n2["sase-pv.2: Declare the `flag` task type in project config [closed]"]
    n3["sase-pv.3: Two kinds, a derived default, and a rebuilt `sase flag new` [closed]"]
    n4["sase-pv.4: Due-ness, identity, and integrity read task-type fields [closed]"]
    n5["sase-pv.5: FlagTriage is a task-bead gate [closed]"]
    n6["sase-pv.6: Every bead surface renders a flag as a typed task [closed]"]
    n7["sase-pv.7: Migrate the five live flag beads [in_progress]"]
    n8["sase-pv.8: Delete the `flag` issue type end to end [in_progress]"]
    n9["sase-pv.9: Memory notes, generated instructions, and documentation [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n0 --> n9
    n1 -.-> n2
    n2 -.-> n3
    n2 -.-> n4
    n3 -.-> n7
    n4 -.-> n5
    n4 -.-> n6
    n5 -.-> n7
    n6 -.-> n7
    n7 -.-> n8
    n8 -.-> n9
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-pv.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-pv.1.md) | [sase-pv.1](sase-pv.1.md) | 2 |
| [bbugyi200.athena.sase-pv.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-pv.2/README.md) | [sase-pv.2](sase-pv.2.md) | 1 |
| [bbugyi200.athena.sase-pv.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-pv.3/README.md) | [sase-pv.3](sase-pv.3.md) | 1 |
| [bbugyi200.athena.sase-pv.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-pv.4/README.md) | [sase-pv.4](sase-pv.4.md) | 2 |
| [bbugyi200.athena.sase-pv.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-pv.5/README.md) | [sase-pv.5](sase-pv.5.md) | 1 |
| [bbugyi200.athena.sase-pv.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-pv.6/README.md) | [sase-pv.6](sase-pv.6.md) | 1 |
| [bbugyi200.athena.sase-pv.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-pv.7/README.md) | [sase-pv.7](sase-pv.7.md) | 0 |
| [bbugyi200.athena.sase-pv.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-pv.8/README.md) | [sase-pv.8](sase-pv.8.md) | 0 |
| [bbugyi200.athena.sase-pv.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-pv.9/README.md) | [sase-pv.9](sase-pv.9.md) | 0 |
| [bbugyi200.athena.sase-pv.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-pv.land/README.md) | [sase-pv](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@3f4e773`](https://github.com/sase-org/sase-core/commit/3f4e7733703454904a15848a33298713591895e6) | feat(task\_type): drop flag from reserved task-type slugs | [sase-pv.1](sase-pv.1.md) | 2026-08-18 12:25:44 EDT |
| sase | [`24ce7e0`](https://github.com/sase-org/sase/commit/24ce7e0569ed94368acbbe518607d29594753bbe) | test: accept flag as a claimable task-type slug | [sase-pv.1](sase-pv.1.md) | 2026-08-18 12:29:18 EDT |
| sase | [`88d2a15`](https://github.com/sase-org/sase/commit/88d2a1582a1d4a94f75e55fc61c230f049b75691) | feat(task-types): declare the project-local flag task type | [sase-pv.2](sase-pv.2.md) | 2026-08-18 12:57:33 EDT |
| sase | [`98b27e8`](https://github.com/sase-org/sase/commit/98b27e849c3a3b562dc9f9a1c389945a73f26d4a) | feat(feature-flags)!: collapse flag kinds and rebuild flag new on typed task beads | [sase-pv.3](sase-pv.3.md) | 2026-08-18 13:40:50 EDT |
| sase | [`c5a0dcf`](https://github.com/sase-org/sase/commit/c5a0dcf4a4f3b56f548af1e02377c1c0daa9188f) | feat(flags): read flag identity and due-ness from task fields | [sase-pv.4](sase-pv.4.md) | 2026-08-18 14:13:11 EDT |
| sase-core | [`sase-core@c121e0e`](https://github.com/sase-org/sase-core/commit/c121e0ed6bfbd1e11fa4ca27ab166f7dcf63db8d) | feat(bead): persist task\_type\_fields on bead update | [sase-pv.4](sase-pv.4.md) | 2026-08-18 14:16:26 EDT |
| sase | [`65a34b9`](https://github.com/sase-org/sase/commit/65a34b9096c0ab8a301725697495d4bb340bcf64) | feat(flags): treat FlagTriage as a task-bead gate | [sase-pv.5](sase-pv.5.md) | 2026-08-18 15:32:29 EDT |
| sase | [`2b2c5ed`](https://github.com/sase-org/sase/commit/2b2c5edefe1b4e94b83c6e3016bb5245d92c75cf) | feat(beads)!: render flags as typed tasks on every bead surface | [sase-pv.6](sase-pv.6.md) | 2026-08-18 15:55:19 EDT |
