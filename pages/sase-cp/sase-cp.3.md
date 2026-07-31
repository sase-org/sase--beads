# Bead: sase-cp.3 — Remove deployed skill copies and verify rollout

[Bead Pages](../README.md) / [sase-cp](README.md) / sase-cp.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.qn](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.qn/README.md) · **Assignee:** `sase-cp.3` · **Size:** small
**Created:** 2026-07-31 19:01:11 UTC · **Closed:** 2026-07-31 19:46:14 UTC
**Plan:** [202607/sase\_beads\_memory.md](https://github.com/sase-org/sase--plans/blob/main/202607/sase_beads_memory.md)

## Description

cleanup: git rm the six chezmoi skill copies, delete the seven home skill directories, and verify the new note reached home memory.

## Notes

[2026-07-31T19:49:00Z · sase-cp.3] Verified: (1) chezmoi commit 67b58a6f git-rm'd all six home/dot_*/skills/sase_beads/SKILL.md copies, pushed, after-commit hook `chezmoi update -a --force` ran; (2) all seven home copies deleted, including the unmanaged ~/.gemini/skills/sase_beads — `find ~ -maxdepth 6 -path "*skills*sase_beads*" -not -path "*/.local/state/sase/*"` now prints nothing; (3) ~/sase/memory/sase_beads.md exists and both ~/AGENTS.md and ~/CLAUDE.md list it in Tier 2 (line 58); (4) `sase memory read sase_beads.md` returns the note. Caveat on `sase skill list`: it still shows a /sase_beads source and 5 missing targets because the global `sase` on PATH is a uv editable install pointing at /home/bryan/projects/github/sase-org/sase, which is 2 commits behind origin/master and still holds the retired src/sase/xprompts/skills/sase_beads.md. The source is confirmed ABSENT on origin/master (642b4f490); that checkout was left untouched and the listing clears itself once it pulls.

[2026-07-31T19:49:08Z · sase-cp.3] PROPOSED FOLLOW-UP: the global `sase` editable install points at the user's primary dev checkout, so any `sase skill init --force` run from a stale checkout resurrects retired skill copies in chezmoi and ~ — worth pairing the `sase skill init --prune` idea with a staleness guard.

[2026-07-31T19:49:19Z · sase-cp.3] cleanup verified: six chezmoi skill copies git-rm'd and committed (67b58a6f), seven home skill dirs deleted, home memory note + Tier 2 listing confirmed, sase memory read returns the note

## Dependencies

- **Depends on:** [sase-cp.2](sase-cp.2.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-cp.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-cp.3/README.md) | [sase-cp.3](sase-cp.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| chezmoi | [`chezmoi@67b58a6`](https://github.com/bbugyi200/dotfiles/commit/67b58a6f6e5eee2bef7d3e9ccd39f4f5598bbab2) | chore(skills): remove deployed sase\_beads skill copies | [sase-cp.3](sase-cp.3.md) | 2026-07-31 19:46:33 |
