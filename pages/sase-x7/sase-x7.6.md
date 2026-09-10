# Bead: sase-x7.6 — Back up and migrate local state on all three machines

[Bead Pages](../README.md) / [sase-x7](README.md) / sase-x7.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0gk](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0gk.md) · **Assignee:** `sase-x7.6` · **Size:** medium
**Created:** 2026-09-05 18:55:31 EDT · **Closed:** 2026-09-06 19:21:02 EDT
**Plan:** [202609/canonical\_only\_fleet\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/canonical_only_fleet_cutover.md)

## Description

local-state-cutover: Execute the rehearsed maintenance runbook on athena, mac, and apollo; back up quiescent state, apply the supported import-state purge, migrate remaining local stores and roots, remove verified residue without following symlinks, and produce per-host receipts before resuming compatible writers.

## Notes

[2026-09-06T04:09:48Z · sase-x7.2.1.land] DISCOVERED ISSUE (from sibling phase sase-x7.2's migration-kit epic sase-x7.2.1, phase sase-x7.2.1.4 kit-rehearsal): the shipped 'procs-residue' operation can never archive athena's real ~/.sase/tasks/tasks.jsonl residue as currently scoped, so this phase must not assume the kit will clear it. Proved on real athena data on 2026-09-05: all 22 legacy rows in the live tasks.jsonl (created 2026-08-14) have no counterpart in the current ~/.sase/procs/procs.jsonl (101 rows, all created 2026-08-29 or later), because the canonical proc store retains only a rolling recent window rather than every historical record. 'sase migrate plan procs-residue' therefore refuses the whole manifest, which is the correct marker-is-not-proof behavior the migration-kit plan demanded and is a successful outcome for the kit, not a kit defect. This phase needs a deliberate decision, one of: (a) a human-verified manual archive path for residue whose canonical siblings have already rotated out of the proc store, executed outside the kit's automated catalog; or (b) a widened reconciliation rule that accepts a legacy row as safe when no live proc record of any kind references its id AND the row predates the canonical store's oldest retained row - which would require a change to migration_reconcile_procs in sase-core (crates/sase_core/src/migration/procs.rs) and to src/sase/migration_kit/operations/procs_residue.py. Recorded by sase-x7.2.1.land; the same finding is in the kit-rehearsal receipt.

[2026-09-06T12:17:31Z · sase-x7.2.1.5.land] DISCOVERED ISSUE (proposed by sase-x7.2.1.5.2 note #1): mac and apollo live sase-core-rs remain 0.32.23, below the migration kit floor >=0.32.25. The mac rehearsal proved the isolated 0.32.25 build and deliberately did not touch the editable live install. Before any real apply, local-state-cutover must raise and verify the live floor on both hosts using a planned install path, not sase update against mac's editable checkout mid-window. This is already a hard precondition in the published mac/apollo manifests, so it is owned by this active phase rather than a new task bead.

[2026-09-06T23:20:17Z · sase-x7.6] PROPOSED FOLLOW-UP: migration kit live-root planning is too broad for post-cutover verification -- after athena import purge/manual residue archive, `sase migrate plan procs-residue` failed hashing live ~/.sase when chats_catalog.sqlite-shm disappeared, and timed state/lock plans did not complete; later kit cleanup should either narrow root digests or document this migration-kit-only limitation before deletion.

[2026-09-06T23:21:02Z · sase-x7.6] Verified local-state cutover on 2026-09-06: mac and apollo reachable, live uv tool installs report sase-core-rs 0.32.25, import-purge previews empty, latest procs/state residue verifies clean, and legacy roots absent with code-swap-v2.lock retained. On athena, verified backup athena-20260906T182328-d91f9e exists, applied supported import purge with no errors, after-preview is empty across artifact_dirs/bundle_files/chat_files/import_dirs/receipt_files/cache_dirs/dismissed_identities/surviving_import_names, manually archived stale tasks/agent_tags/plan_approval/user_question/code-swap.lock to that backup under migration-archives/manual-athena-local-state-20260906T231519Z, confirmed archive counts 14886 task files, 7 plan-approval files, 39 question files, agent_tags.json 245212 bytes, no open handles, no symlinks, no legacy proc id overlap with current procs, legacy proc rows predate the current proc window, originals absent, canonical procs still has 101 rows, and current code-swap-v2.lock remains present. Ran sase bead epic-symbols sase-x7.6 after work: no entries.

## Dependencies

- **Depends on:** [sase-x7.2](sase-x7.2.md) ✓ · ⧖ 2026-09-05
- **Depends on:** [sase-x7.3](sase-x7.3.md) ✓ · ⧖ 2026-09-05
- **Blocks:** [sase-x7.7](sase-x7.7.md) ◐ · ⧖ 2026-09-05
- **Blocks:** [sase-x7.8](sase-x7.8.md) ◐ · ⧖ 2026-09-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-x7.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-x7.6/README.md) | [sase-x7.6](sase-x7.6.md) | 0 |
