# Bead: sase-10r.1 — Emergency reclaim on apollo

[Bead Pages](../README.md) / [sase-10r](README.md) / sase-10r.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.kellys\_mbp.0l](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.kellys_mbp.0l.md) · **Assignee:** `sase-10r.1` · **Size:** small
**Created:** 2026-09-14 06:56:21 EDT · **Closed:** 2026-09-14 07:18:20 EDT
**Plan:** [202609/apollo\_disk\_reclaim\_1.md](https://github.com/sase-org/sase--plans/blob/main/202609/apollo_disk_reclaim_1.md)

## Description

apollo-emergency-reclaim: over ssh with no repo changes, delete finished agents' cargo targets, stale zorg target dirs, trashed pre-cutover SASE trees, stale pytest scratch, and legacy cargo strays, with liveness guards and before/after df accounting.

## Notes

[2026-09-14T11:17:32Z · sase-10r.1] PROPOSED FOLLOW-UP: ~146M remains in ~/.local/share/Trash/files/_cacache on apollo, owned by root (files are -r--r--r-- root:root inside a root-owned directory). bryan has no passwordless sudo so this cannot be removed as part of this phase; needs a sudo-capable pass or an owner audit of how root-owned files ended up in bryans npm trash.

[2026-09-14T11:18:20Z · sase-10r.1] Emergency reclaim done over ssh apollo, no repo changes. df -h / went from 9.3G to 110G available (target was 80G). Steps: (1) deleted dead entries under ~/.cache/sase/tmp/{cargo-targets,agent-tmp} after a liveness scan of every bryan-owned process's environ/cwd/fd plus a 30m mtime check, keeping all launches with a live CARGO_TARGET_DIR/TMPDIR match (~19G freed). (2) permanently deleted Trash sase-org, sase_1, and most of _cacache after confirming each .trashinfo Path/DeletionDate (~49G freed; ~146M of _cacache left behind, root-owned, noted as follow-up). (3) rm -rf'd target/ in zorg_100, zorg_101, zorg_102, and the primary zorg checkout after confirming no process cwd was under zettel-org (~29G freed). (4) reaped stale (>2h, no live .lock) pytest-<N>/garbage-* run dirs under every /var/tmp/sase-<hash> root, then removed orphan root sase-5d01d5fa entirely after confirming its checkout hash matched none of the current workspaces/sase-org/sase-core checkouts and nothing in it predated the 12h window (~1G+ freed). (5) rm -rf'd the legacy ~/tmp/sase/cargo-targets stray after confirming no live env/cwd/recent-mtime match (~1.8G freed). Step 6 (uv/npm cache prune) was skipped since free space already exceeded 60G well before reaching it. Verified after: the run_agent_runner.py PIDs seen at the start of the sweep are still alive except three that finished normally during the sweep, and 'sase disk list' runs cleanly. No --epic-symbol entries for this bead.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.kellys\_mbp.sase-10r.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.kellys_mbp.sase-10r.1/README.md) | [sase-10r.1](sase-10r.1.md) | 0 |
