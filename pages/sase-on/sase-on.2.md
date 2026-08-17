# Bead: sase-on.2 — BeadStaleCleanup gate contract

[Bead Pages](../README.md) / [sase-on](README.md) / sase-on.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.04x](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04x.md) · **Assignee:** `sase-on.2` · **Size:** medium
**Created:** 2026-08-17 11:47:55 EDT · **Closed:** 2026-08-17 12:33:24 EDT
**Plan:** [202608/task\_bead\_gate\_thresholds.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_bead_gate_thresholds.md)

## Description

gate: build the trusted BeadStaleCleanup gate kind — constants, payload, per-bead select/unselect inputs, spec builder, payload-pure preview, command wrapper, response translation, adapter registration, and kind validation.

## Notes

[2026-08-17T16:09:33Z · sase-on.2] PROPOSED FOLLOW-UP: just check lint (feature flags) fails on live flag bead sase-om (key completion_refresh_on_update) with no registry definition in this tree — rule 8; unrelated to BeadStaleCleanup. The definition likely lives on sase-oc.7 unpublished work; this workspace has zero references to that key.

[2026-08-17T16:14:15Z · sase-on.2] PROPOSED FOLLOW-UP: just validate fails init memory --check — chezmoi home AGENTS.md/provider shims/README.md need refresh; no memory files were edited in this phase.

[2026-08-17T16:33:24Z · sase-on.2] Built the trusted BeadStaleCleanup gate kind: constants, frozen payload, per-bead close/keep inputs (absent=close), spec builder, payload-pure stale.md preview, command wrapper, response translation, adapter (generic_form, forbidden auto, optional feedback), kind validation, and BeadStaleCleanup priority/debug icon. Verified create_gate round-trips; command defaults/keep/all-keep/bad-stdin; preview ages from stale_as_of and never shows ProjectSpec keys; validation rejects tampered option/command/preview/resources/presentation plus empty/duplicate/over-cap rosters; translation maps 1-based indexes through the persisted roster. sase bead epic-symbols sase-on.2 is empty; create_bead_stale_cleanup_gate remains --epic-symbol sase-on(...) until the chop consumer. Dedicated gate tests passed; test-scoped escalated to the full suite (Justfile) and passed. just check lint besides two unrelated reds: live flag bead sase-om has no definition, and init memory --check wants chezmoi shim refresh (both recorded as PROPOSED FOLLOW-UP).

[2026-08-17T16:34:34Z · sase-on.2] Verified BeadStaleCleanup gate contract: spec/command/preview/validation/translation tests, adapter registration (generic_form, forbidden auto), payload-pure ages via stale_as_of, project_display_name_for labels, index remapping through persisted roster. sase bead epic-symbols sase-on.2 is empty; create_bead_stale_cleanup_gate remains --epic-symbol on parent sase-on until the chop consumer. Dedicated gate tests passed; test-scoped escalated to full suite (Justfile) and passed.

## Dependencies

- **Blocks:** [sase-on.3](sase-on.3.md) ◐ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-on.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-on.2/README.md) | [sase-on.2](sase-on.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3cfc5dd`](https://github.com/sase-org/sase/commit/3cfc5ddf48b48dbbc7f379fd8ef46c3586543660) | feat(gates): add BeadStaleCleanup notification gate contract | [sase-on.2](sase-on.2.md) | 2026-08-17 12:35:24 EDT |
