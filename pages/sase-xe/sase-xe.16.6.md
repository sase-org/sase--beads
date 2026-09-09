# Bead: sase-xe.16.6 — Canonical \`sase machine init\` with real activation and honest outcomes

[Bead Pages](../README.md) / [sase-xe.16](sase-xe.16.md) / sase-xe.16.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08c](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08c.md) · **Assignee:** `sase-xe.16.6` · **Size:** large
**Created:** 2026-09-08 10:21:36 EDT · **Closed:** 2026-09-08 17:44:12 EDT
**Plan:** [202609/remote\_dispatch\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_completion.md)

## Description

machine-init: add canonical `sase machine init` and refactor `sase init machine` and the init-registry machine spec to delegate to one shared machine-owned planner/apply service. Checks and previews stay offline; discovery runs only during explicit apply, after local identity setup. Existing enrolled machines must not suppress an explicit rescan, while an all-enrolled or zero-machine registry must not leave `sase init --check` permanently red. Read enrollment bundles with a hidden prompt (getpass), file, or stdin - never bare input(). Reuse `sase machine add`'s EnrollmentResult handling so quarantined or failed enrollment is reported truthfully instead of the current unconditional 'Enrolled'. After write_machine_record on a chezmoi-enabled controller, deploy the scoped change through the established apply_chezmoi mechanism honoring its tracked-proc contract, reload the merged config, resolve the credential, and run an authenticated hello before declaring success; apply failure or partial enrollment leaves actionable recovery state since the target may have consumed the bootstrap. Skip already-enrolled identities, never overwrite a pin during rescan, and route changed identity to `sase machine repair`. Fix stale docs/init.md wording and add behavioral tests for the interactive flow.

## Notes

[2026-09-08T21:43:38Z · sase-xe.16.6] PROPOSED FOLLOW-UP: share chezmoi apply + authenticated hello activation with sase machine add so direct enrollment on a chezmoi controller also deploys the applied overlay, not only the canonical init path.

[2026-09-08T21:44:12Z · sase-xe.16.6] Canonical sase machine init now owns planner/apply; sase init machine and the init-registry machine spec delegate to it. Verified: five-spec init order config-machine-memory-repo-skills; offline --check/--json never discovers and is not perpetual drift for zero-machine or all-enrolled registries; TTY-gated offer only; enrollment bundles from hidden getpass, --bootstrap-file, or stdin never via echoing input(); rescan lists enrolled beside new candidates, skips exact pin matches, and routes changed identity to sase machine repair without overwriting pins; quarantine reuses machine-add JSON fields and exits nonzero; chezmoi source-vs-applied activation copies only after apply; authenticated hello is required before enrolled success; apply/hello failure prints retry-apply or re-bootstrap + repair recovery. epic-symbols: none remaining.

## Dependencies

- **Blocks:** [sase-xe.16.10](sase-xe.16.10.md) ○ · ⧖ 2026-09-08
- **Depends on:** [sase-xe.16.4](sase-xe.16.4.md) ✓ · ⧖ 2026-09-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xe.16.6.md) | [sase-xe.16.6](sase-xe.16.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`338e3b3`](https://github.com/sase-org/sase/commit/338e3b349e131797f122bff3e5fd8583279ca913) | feat(machine): add canonical sase machine init with verified activation | [sase-xe.16.6](sase-xe.16.6.md) | 2026-09-08 17:47:40 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-xe.16.6][1] | Need the phase bead scope and status before implementing | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xe.16.6.md

<!-- sase:referenced-by:end -->
