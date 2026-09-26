# Bead: sase-1ab.1.1.2 — Named-proc store, launch, and holds

[Bead Pages](../README.md) / [sase-1ab.1.1](sase-1ab.1.1.md) / sase-1ab.1.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1ab.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ab.1.md) · **Assignee:** `sase-1ab.1.1.2` · **Size:** medium
**Created:** 2026-09-26 00:28:16 EDT · **Closed:** 2026-09-26 01:14:03 EDT
**Plan:** [202609/sase\_core\_turn\_expand.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_core_turn_expand.md)

## Description

procs: rename proc-shell fields, lifecycle helpers, launch-plan names, and hold candidates to named-proc vocabulary, accept the new spellings, keep emitted values legacy, and register the new name validator beside the legacy binding.

## Notes

[2026-09-26T05:13:29Z · sase-1ab.1.1.2] Remaining concept hits in owned files: legacy pins for contract-flip — shell_name/shell_kind serde renames (procs/wire.rs, agent_launch/wires.rs, proc_runtime.rs), proc_shell hold candidate rename (agent_hold.rs), shell: conflict-key prefix + PROC_LIFECYCLE_NAMED_PROC="proc-shell" (procs/store.rs), "proc_shell" selector-match kind + hold_selector_match_is_named_proc reader, invalid-proc-shell-name diagnostic (plan_resolution.rs); legacy binding validate_standalone_proc_shell_name beside validate_standalone_named_proc_name; test names referencing legacy keys

[2026-09-26T05:13:39Z · sase-1ab.1.1.2] PROPOSED FOLLOW-UP: contract-flip must flip shell_name->proc_name, shell_kind->proc_role, proc_shell->named_proc, shell:->named-proc:, proc-shell lifecycle, invalid-proc-shell-name code, and remove legacy bindings (files listed in phase notes)

[2026-09-26T05:14:03Z · sase-1ab.1.1.2] Phase procs done in sase-core working tree (uncommitted): renamed proc-shell fields/helpers/validators/hold candidate to named-proc vocabulary with legacy serde pins and dual-name binding; sase tool run check passed (run 0cb6b0fbd12b56edad20ee65895f83dd); versions, SQLite, goldens, parity JSON unchanged

## Dependencies

- **Depends on:** [sase-1ab.1.1.1](sase-1ab.1.1.1.md) ✓ · ⧖ 2026-09-26
- **Blocks:** [sase-1ab.1.1.3](sase-1ab.1.1.3.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ab.1.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ab.1.1.2/README.md) | [sase-1ab.1.1.2](sase-1ab.1.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@4a04cea`](https://github.com/sase-org/sase-core/commit/4a04cea5b20cf17615cd7acafec9f1ad4dfadce3) | refactor(core): rename proc-shell store, launch, and hold wires to named-proc vocabulary | [sase-1ab.1.1.2](sase-1ab.1.1.2.md) | 2026-09-26 01:15:29 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ab.1.1.2][1] | Need the phase scope and design file | 2 |
| read-by | [agent:sase-1ab.1.1.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ab.1.1.2/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ab.1.1.land/README.md

<!-- sase:referenced-by:end -->
