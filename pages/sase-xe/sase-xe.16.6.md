# Bead: sase-xe.16.6 — Canonical \`sase machine init\` with real activation and honest outcomes

[Bead Pages](../README.md) / [sase-xe.16](sase-xe.16.md) / sase-xe.16.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08c](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08c.md) · **Assignee:** `sase-xe.16.6` · **Size:** large
**Created:** 2026-09-08 10:21:36 EDT
**Plan:** [202609/remote\_dispatch\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_completion.md)

## Description

machine-init: add canonical `sase machine init` and refactor `sase init machine` and the init-registry machine spec to delegate to one shared machine-owned planner/apply service. Checks and previews stay offline; discovery runs only during explicit apply, after local identity setup. Existing enrolled machines must not suppress an explicit rescan, while an all-enrolled or zero-machine registry must not leave `sase init --check` permanently red. Read enrollment bundles with a hidden prompt (getpass), file, or stdin - never bare input(). Reuse `sase machine add`'s EnrollmentResult handling so quarantined or failed enrollment is reported truthfully instead of the current unconditional 'Enrolled'. After write_machine_record on a chezmoi-enabled controller, deploy the scoped change through the established apply_chezmoi mechanism honoring its tracked-proc contract, reload the merged config, resolve the credential, and run an authenticated hello before declaring success; apply failure or partial enrollment leaves actionable recovery state since the target may have consumed the bootstrap. Skip already-enrolled identities, never overwrite a pin during rescan, and route changed identity to `sase machine repair`. Fix stale docs/init.md wording and add behavioral tests for the interactive flow.

## Dependencies

- **Blocks:** [sase-xe.16.10](sase-xe.16.10.md) ◐ · ⧖ 2026-09-08
- **Depends on:** [sase-xe.16.4](sase-xe.16.4.md) ✓ · ⧖ 2026-09-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.16.6/README.md) | [sase-xe.16.6](sase-xe.16.6.md) | 0 |
