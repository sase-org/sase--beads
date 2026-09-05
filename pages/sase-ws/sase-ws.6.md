# Bead: sase-ws.6 — Docs, memory record, and final sweep

[Bead Pages](../README.md) / [sase-ws](README.md) / sase-ws.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.y` · **Assignee:** `sase-ws.6` · **Size:** medium
**Created:** 2026-09-04 13:48:32 EDT · **Closed:** 2026-09-05 16:24:38 EDT
**Plan:** [202609/remove\_agents\_sync\_import.md](https://github.com/sase-org/sase--plans/blob/main/202609/remove_agents_sync_import.md)

## Description

docs-memory-sweep: rewrite the import sections out of the docs, supersede the v1-import-retired decision with a new publish-only decision record, regenerate the instruction shims, and grep-sweep the tree for leftover import-leg references.

## Notes

[2026-09-05T20:24:38Z · sase-ws.6] Wrote decision record sase/memory/decisions/agents-sync-publish-only.md describing the epic's final publish-only state (v1/v2 import engine and ACE import UI deleted, purge-local-state is the sole cleanup path), and superseded sase/memory/decisions/v1-import-retired.md with a back-link. Grep-swept the tree via a subagent and fixed the genuinely stale docs it found: removed the redundant 'Shared History Import Retirement' section from docs/agents_sidecar.md, and rewrote the stale ACE Update-panel prose in docs/configuration.md and docs/plugins.md (dropped the deleted 'agents' scope/'Cached agent hoods' leg from the ,U panel description, verified against src/sase/ace/update_scope.py + update_panel.py + update_panel_state.py which confirm only SASE/Providers legs remain) and fixed a stale 'imports shared history' line about `sase agent sync`. Ran `sase memory init --no-commit` to regenerate AGENTS.md/CLAUDE.md/GEMINI.md/QWEN.md/OPENCODE.md and the memory README from the updated decision roster. Verified with `just install`, `just fmt`, and `just check` (all lint gates green; scoped test lane escalated to the full suite per contract-set-only/core-identity-changed rules and passed, confirming the epic's previously-reported test_inventory_records_infrastructure_and_classifications regression is already resolved). sase bead epic-symbols sase-ws.6 reported no entries.

## Dependencies

- **Depends on:** [sase-ws.5](sase-ws.5.md) ✓ · ⧖ 2026-09-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-ws.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-ws.6/README.md) | [sase-ws.6](sase-ws.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`302875c`](https://github.com/sase-org/sase/commit/302875cbc6d8d3fd7484e57012eff72db7c61e76) | docs(agents-sync): remove stale import-leg references, add decision records | [sase-ws.6](sase-ws.6.md) | 2026-09-05 16:26:36 EDT |
