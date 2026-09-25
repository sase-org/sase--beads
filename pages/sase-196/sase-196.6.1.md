# Bead: sase-196.6.1 — Restore Apollo's missing prompt-archive object

[Bead Pages](../README.md) / [sase-196.6](sase-196.6.md) / sase-196.6.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-196.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-196.land.md) · **Assignee:** `sase-196.6.1` · **Size:** medium
**Created:** 2026-09-25 12:06:27 EDT · **Closed:** 2026-09-25 12:36:43 EDT
**Plan:** [202609/restore\_prompt\_archive\_objects.md](https://github.com/sase-org/sase--plans/blob/main/202609/restore_prompt_archive_objects.md)

## Description

apollo-object: recover the exact object linked by an already-published sase prompt, then publish it through the fixed agents sync path.

## Notes

[2026-09-25T16:36:32Z · sase-196.6.1] PROPOSED FOLLOW-UP: `sase agent sync -p sase` on athena ends with "agents sync failed: artifact-link legacy index writes are fenced; use link events" (RuntimeError from src/sase/sdd/_artifact_link_store_sidecar.py _upsert_sidecar/_remove_sidecar_rows, fenced by a8d99d295) AFTER the pull/push had already published the object, and the run took ~19 min (an earlier 5-min-timeout run was killed after committing f400dbc84b but before pushing). Reproduces on the clean master base tree; some caller during the sync export/link pass still uses the legacy index write path instead of link events.

[2026-09-25T16:36:43Z · sase-196.6.1] Restored Apollo's missing prompt-archive object files/objects/sha256/41/412ed4ed...6268 (18548 bytes): verified on Apollo it is a regular file whose sha256 equals its filename, copied its exact bytes to athena's agents sidecar and re-verified the destination hash; Apollo copy preserved (untouched, still 18548 bytes). Published via the checkout's .venv/bin/sase agent sync -p sase (pre-pull pending-object sweep): sidecar commit f400dbc84b 'chore(agents): publish pending prompt-archive objects' is tracked and contained in origin/main (HEAD 452c04078d == origin/main), sidecar worktree clean. .venv/bin/sase agent prompts validate: 'Prompt archive validation passed: 6492 prompts, 208 warnings', exit 0 (no artifact-missing error). sase bead epic-symbols: no entries. Caveat recorded as PROPOSED FOLLOW-UP: sync's final result row reported a fenced artifact-link legacy-index write error after publication and took ~19 min.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-196.6.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-196.6.1/README.md) | [sase-196.6.1](sase-196.6.1.md) | 0 |
