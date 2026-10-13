# Bead: sase-1ko.2 — Instruction manifest wire v2 in sase-core (delivery slots and fallback), binding, adapter, pin move

[Bead Pages](../README.md) / [sase-1ko](README.md) / sase-1ko.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.13.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.13.linker.w0.md) · **Assignee:** `sase-1ko.2` · **Size:** medium
**Created:** 2026-10-13 18:10:34 EDT · **Closed:** 2026-10-13 19:37:11 EDT
**Plan:** [202610/e3\_explicit\_delivery\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202610/e3_explicit_delivery_cutover.md)

## Description

delivery-wire: bump the instruction manifest wire to v2. Add the subagent delivery slot, the delivery fallback block, and the channel and slot invariants. Keep v1 manifests readable. Update the binding, the Python adapter constants, the golden fixtures in both repos, and the sase-core pin.

## Notes

[2026-10-13T22:57:12Z · sase-1ko.2] PROPOSED FOLLOW-UP: sase-core clippy 1.95 nonminimal_bool deny in project_onboarding/classify.rs — reproduced identically by wrapped check 2663480b36c98c757f649d4b6c99d4db on a clean base tree; the authored-tree run was 6830d681e7506b147ac075023ee38e3b. Existing CI task sase-1an tracks this clean-base clippy failure.

[2026-10-13T23:35:12Z · sase-1ko.2] PROPOSED FOLLOW-UP: Remove the stale --epic-symbol whitelist for closed bead sase-1kj.7 — unchanged Justfile line 457 makes primary symvision lint fail before it inspects symbols; exact-symbol search found no active task bead tracking this cleanup.

[2026-10-13T23:37:11Z · sase-1ko.2] Implemented the v2 manifest contract, validation, Python adapter, binding coverage, and matching golden fixtures while preserving v1 reads. Verified core instruction_manifest (16 tests), core_py instruction_manifest (5 tests), primary targeted pytest (27 tests), binding surface check, formatting, whitespace, and fixture parity. Full checks hit recorded clean-base core clippy failure tracked by sase-1an and an unchanged stale Justfile epic symbol for closed bead sase-1kj.7. Confirmed no epic symbols remain for this phase.

## Dependencies

- **Blocks:** [sase-1ko.5](sase-1ko.5.md) ◐ · ⧖ 2026-10-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1ko.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1ko.2/README.md) | [sase-1ko.2](sase-1ko.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@973017b`](https://github.com/sase-org/sase-core/commit/973017b6b6a91c0e843d60a65040c9496e94d423) | feat(instruction-manifest)!: add v2 delivery slots and fallback | [sase-1ko.2](sase-1ko.2.md) | 2026-10-13 19:38:10 EDT |
| sase | [`96090a5`](https://github.com/sase-org/sase/commit/96090a52cfb4b38a64e8a05a23d305bf0009080b) | feat(instructions): adopt manifest v2 delivery slots | [sase-1ko.2](sase-1ko.2.md) | 2026-10-13 19:44:26 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ko.2][1] | Confirm recorded clean-base follow-ups before closing | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1ko.2/README.md

<!-- sase:referenced-by:end -->
