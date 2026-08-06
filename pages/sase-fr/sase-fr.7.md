# Bead: sase-fr.7 — Generated bead pages close history

[Bead Pages](../README.md) / [sase-fr](README.md) / sase-fr.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tr](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tr/README.md) · **Assignee:** `sase-fr.7` · **Size:** small
**Created:** 2026-08-05 21:25:55 EDT · **Closed:** 2026-08-05 23:38:57 EDT
**Plan:** [202608/bead\_close\_history.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_close_history.md)

## Description

pages: render a Previously Closed section and primary-fact badge on generated bead pages and add a reopen column to the lineage roster.

## Notes

[2026-08-06T03:38:57Z · sase-fr.7] Implemented render_close_history + primary-fact badge in rendering_identity.py, wired into rendering.py above description; added ↺ column to roster.py lineage table; trimmed stale --epic-symbol whitelist entries in Justfile for symbols now used. Added 3 new tests (bounded callouts newest-first, missing-reason placeholder, roster column) plus updated 2 existing tests for the new column/section. Verified: 26/26 targeted bead_pages tests pass; full just check passes (25696/25697, fmt/lint/symvision/validate all green) with the sole failure being test_concurrent_bead_mutations_wait_past_the_old_lock_timeout, a pre-existing load-sensitive flake unrelated to this change (passes in isolation; already tracked across many prior beads and epic sase-fd).

## Dependencies

- **Depends on:** [sase-fr.3](sase-fr.3.md) ✓ · ⧖ 2026-08-05
- **Blocks:** [sase-fr.8](sase-fr.8.md) ✓ · ⧖ 2026-08-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fr.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fr.7/README.md) | [sase-fr.7](sase-fr.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bf448ef`](https://github.com/sase-org/sase/commit/bf448ef99c12a28702cc1f38eaae03634a4dc089) | feat(bead-pages): render close history and reopen badge on generated pages | [sase-fr.7](sase-fr.7.md) | 2026-08-05 23:40:02 EDT |
