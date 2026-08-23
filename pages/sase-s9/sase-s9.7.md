# Bead: sase-s9.7 — Documentation, visual snapshot, and copy review

[Bead Pages](../README.md) / [sase-s9](README.md) / sase-s9.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0bh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0bh.md) · **Assignee:** `sase-s9.7` · **Size:** small
**Created:** 2026-08-23 08:01:40 EDT · **Closed:** 2026-08-23 11:47:56 EDT
**Plan:** [202608/procs\_filter.md](https://github.com/sase-org/sase--plans/blob/main/202608/procs_filter.md)

## Description

polish: document the proc query dialect in the ACE Procs Tab reference, add a PNG snapshot of the filtered pane, and do a final pass over hint text, placeholder copy, and error wording.

## Notes

[2026-08-23T15:47:33Z · sase-s9.7] PROPOSED FOLLOW-UP: `sase validate` (init memory --check) fails on a clean master checkout in this workspace -- 7 files (task_types.md, README.md, AGENTS.md, and 4 provider shims) are reported out of sync. Confirmed pre-existing via git stash, not introduced by this phase. Also: `just test-visual` shows small (~0.4-0.5%) pixel drift on Procs-tab PNG snapshots even on unmodified master across repeated runs in this sandbox, consistent with the known local fontconfig/renderer nondeterminism noted in memory/build_and_run.md -- worth a flake bead if it keeps reproducing.

[2026-08-23T15:47:56Z · sase-s9.7] Added 'Filtering procs' doc section (full key table, m-cycle, worked example) and / + m rows to the Procs Tab Keybindings table in docs/ace.md; documented the bare-boolean shorthand (incl. Stitches sidecar behavior change) in the shared flat-dialect section. Added / and m entries to the Admin Center Procs help-modal section (binding_common.py), which had been missing them. Added and accepted a new PNG visual snapshot (config_center_procs_tab_filtered_120x40) covering the active teal filter bar, highlighted closed display, and the N/M shown header, verified by eye. Verified: just check passes every lint gate (fmt, ruff, mypy, flags, pyscripts, test-waits, changelog, terminology, symvision, toobig) and just test-scoped (718 passed); sase bead epic-symbols sase-s9.7 reports no leftover entries. SASE validation's init-memory-check failure and small PNG pixel drift under just test-visual are both pre-existing on unmodified master (confirmed via git stash) and unrelated to this change; recorded as a PROPOSED FOLLOW-UP note.

## Dependencies

- **Depends on:** [sase-s9.5](sase-s9.5.md) ✓ · ⧖ 2026-08-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-s9.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-s9.7/README.md) | [sase-s9.7](sase-s9.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`37abe19`](https://github.com/sase-org/sase/commit/37abe195b91db320983f9a450859d5f3c4b768f0) | docs(ace): document Procs tab filtering and add filtered PNG snapshot | [sase-s9.7](sase-s9.7.md) | 2026-08-23 11:48:51 EDT |
