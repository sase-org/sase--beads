# Bead: sase-1d6.2 — Preserve each failed run's unlanded diff on its bead

[Bead Pages](../README.md) / [sase-1d6](README.md) / sase-1d6.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ua](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ua.md) · **Assignee:** `sase-1d6.2` · **Size:** medium
**Created:** 2026-09-30 06:21:11 EDT · **Closed:** 2026-09-30 06:31:23 EDT
**Plan:** [202609/relaunch\_failed\_epics.md](https://github.com/sase-org/sase--plans/blob/main/202609/relaunch_failed_epics.md)

## Description

salvage: without touching the five pinned workspaces, export each failed run's uncommitted sase and sase-core changes (including untracked files) as verified patches, and attach them with base SHAs and intended commit messages to sase-1d5.1, sase-1cx.1, sase-1cj.12.1, sase-1co, and sase-1ck.

## Notes

[2026-09-30T10:31:02Z · sase-1d6.2] SALVAGE COMPLETE. All five failed runs' uncommitted diffs were exported read-only (git diff/status/clone-from only; no add/stash/reset/checkout/clean/commit in the pinned workspaces, claims untouched) and posted as UNLANDED PRIOR ATTEMPT notes with verified patches. Dirty file sets matched the epic plan table exactly in all five workspaces.

Per-target notes (all accepted; no closed-bead fallback needed):
- sase-1d5.1 note #2: sase-1d5.1-core.patch, sase-core @ a354a8a96c06443fb2ed47b5699e9ae2142862d7, 20 files, 111224 bytes, sha256:6dde4859... (ws sase_13). Msg: feat(attachments): core attachment audience policy and scanner. Plan: core_attachment_audience.md.
- sase-1cx.1 note #2: sase-1cx.1-core.patch, sase-core @ 1e51ff3ce9c53ee1a4bc9f52c3642ac4eea8f423, 25 files, 88969 bytes, sha256:d591cf58... (ws sase_42). Msg: feat(tool-run): add detached starter scope, monitor join, and sync wait budget. Plan: core_detach_join.md.
- sase-1cj.12.1 note #2: sase-1cj.12.1-core.patch, sase-core @ 1e51ff3ce9c53ee1a4bc9f52c3642ac4eea8f423, 7 files, 35280 bytes, sha256:b379919c... (ws sase_14). Msg: fix(prompt-prediction): block structural tails, count support once, real origin inventory.
- sase-1co note #3: sase-1co-sase.patch, sase @ 859140f025decf1e11051412b9a8f6fac53f1252, 6 files, 7697 bytes, sha256:d36cf6f8...; sase-1co-core.patch, sase-core @ 1e51ff3ce9c53ee1a4bc9f52c3642ac4eea8f423, 4 files, 9767 bytes, sha256:377b69e6... (ws sase_12). Plan-done mark for midword_alternation.md never landed; tale midword_alternation_scanner_parity.md referenced.
- sase-1ck note (new): sase-1ck-sase.patch, sase @ b5d3021f5df310d36df2f30eb821254bfc467ca1, 37 files, 112044 bytes, sha256:d80b3629...; sase-1ck-core.patch, sase-core @ a354a8a96c06443fb2ed47b5699e9ae2142862d7, 3 files, 2934 bytes, sha256:db725b0e... (ws sase_16). Plan-done mark for bead_note_attachments.md never landed; tale finish_bead_note_attachments.md referenced.

Verification: all 7 patches passed git apply --check against pristine clones of their base SHAs (throwaway clones under /tmp/salvage-verify, outside managed workspaces).

CAVEAT for relaunch phase: sase bead attachment push reports no shared store on this machine, so the 7 attachments are local-only (content-addressed under /home/bryan/.sase/attachments). Durable second copies plus per-patch file lists live at /home/bryan/.local/state/sase/salvage-sase-1d6/ (outside any checkout). Relaunch on this machine can fetch via the bead attachments or that directory.

[2026-09-30T10:31:23Z · sase-1d6.2] Salvage verified: 7 patches (20+25+7+6+4+37+3 files) exported read-only from pinned workspaces sase_13/42/14/12/16, each passing git apply --check on pristine base SHAs, posted as UNLANDED PRIOR ATTEMPT notes with intended messages and plan refs on sase-1d5.1, sase-1cx.1, sase-1cj.12.1, sase-1co, sase-1ck; epic-symbols clean; own finalizer context shows no foreign obligations.

## Dependencies

- **Blocks:** [sase-1d6.3](sase-1d6.3.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1d6.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1d6.2/README.md) | [sase-1d6.2](sase-1d6.2.md) | 0 |
