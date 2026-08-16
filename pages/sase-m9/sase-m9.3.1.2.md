# Bead: sase-m9.3.1.2 — Migrate patch and agent proc producers

[Bead Pages](../README.md) / [sase-m9.3.1](sase-m9.3.1.md) / sase-m9.3.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m9.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m9.3.md) · **Assignee:** `sase-m9.3.1.2` · **Size:** large
**Created:** 2026-08-15 15:17:09 EDT · **Closed:** 2026-08-15 18:37:14 EDT
**Plan:** [202608/ace\_proc\_ownership.md](https://github.com/sase-org/sase--plans/blob/main/202608/ace_proc_ownership.md)

## Description

migrate-patch-and-agent-producers: move ACE patch/status/rebase/sync/rewind/mail and agent launch, approve, revert, cleanup, wait, rename, and tribe-assignment operations onto the durable domain commands; preserve optimistic UI behavior, reconstruct completion from result envelopes, and translate patch identity, dedup, exclusive scopes, workspace claims, AXE slots, and agent metadata locks into atomically reserved namespaced concurrency keys.

## Notes

[2026-08-15T22:37:14Z · sase-m9.3.1.2] Migrated every inventory Patch and agent producer onto argv-only durable submit. Patch mutations use sase patch + project-qualified ace:patch:{project}:{name} keys; agent directives/launch/cleanup/revert use sase agent persist-directive|persist-cleanup|revert and sase run with namespaced keys. Revert previews are session-local Textual workers (no proc row). Completion maps typed envelopes; collisions warn without rollback; workspace claims settle once. just install and all lint gates passed. Focused durable/inventory/ops/cleanup/launch/e2e tests passed. Grep of Patch/agent action modules shows no leftover callable _submit_proc/_submit_tracked_proc except sibling-phase monitor-stop. just test-visual skipped: no widget or rendered-text change. just check escalated (stale coverage baseline + serial budget) and failed ~60 FORCE_COLOR ANSI substring tests already tracked on sase-m7; those are not caused by this phase. Parent epic left open.

[2026-08-15T22:38:24Z · sase-m9.3.1.2] Verified: just install succeeded; ruff/mypy/Symvision lint gates passed; focused durable-submit, durable-ops, producer-inventory, Patch/agent action, cleanup, launch, ops-command, and save/revive tests passed; AST inventory plus grep of Patch/agent action modules show no leftover callable _submit_proc/_submit_tracked_proc except sibling-phase monitor-stop; just test-visual skipped (no widget/rendered-text change). just check lint passed then scoped tests escalated (stale coverage baseline / serial budget); escalated suite had environment-sensitive FORCE_COLOR=1 ANSI substring failures already tracked on sase-m7, not caused by this migration. Parent epic left open.

## Dependencies

- **Depends on:** [sase-m9.3.1.1](sase-m9.3.1.1.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-m9.3.1.4](sase-m9.3.1.4.md) ✓ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m9.3.1.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m9.3.1.2.md) | [sase-m9.3.1.2](sase-m9.3.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0835b38`](https://github.com/sase-org/sase/commit/0835b38d24fb0316d23e664b2d3d7a0ee079c49c) | feat(ace): migrate Patch and agent producers to durable argv | [sase-m9.3.1.2](sase-m9.3.1.2.md) | 2026-08-15 18:40:26 EDT |
