# Bead: sase-sq.5 — Decision web and flag removal

[Bead Pages](../README.md) / [sase-sq](README.md) / sase-sq.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0cb](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0cb.md) · **Assignee:** `sase-sq.5` · **Size:** medium
**Created:** 2026-08-24 09:32:16 EDT · **Closed:** 2026-08-24 17:54:34 EDT
**Plan:** [202608/memory\_webs.md](https://github.com/sase-org/sase--plans/blob/main/202608/memory_webs.md)

## Description

decisions: remove the memory_webs beta flag and close its flag bead, then ship the `decisions` core web with six authored decision records.

## Notes

[2026-08-24T21:53:15Z · sase-sq.5--3] PROPOSED FOLLOW-UP: roster.py render_strand_roster's inline branch (web.roster == inline) still emits one unwrapped paragraph with no width wrapping -- same latent bug class as the list branch fixed earlier this turn. Only test fixtures use roster: inline today so it has not broken CI yet, but will as soon as a real web descriptor adopts it; wire it through sase.markdown_wrap.wrap_markdown the same way the list branch now is.

[2026-08-24T21:53:49Z · sase-sq.5--3] PROPOSED FOLLOW-UP: sase-core commit bda9efc (feat(bead)!: store notes as structured records, released as v0.32.0) breaks bead event-stream append-only integrity checks against beads.jsonl history committed under the pre-0.32.0 string-notes schema -- any 'sase bead note'/'close' mutation fails with BeadStreamIntegrityError ('worktree rewrote ancestor event 1 (removed payload.issue.notes)') once sase-core_rs is rebuilt from a checkout at or past that commit, because 'just install' always builds from the linked sase-core checkout regardless of pyproject.toml's pinned <0.32.0 window. Reproduced on two unrelated bead trees (sase-sq, sase-sy) in this workspace; worked around this turn by checking out sase-core to the v0.31.14 tag (last commit before the breaking change) in this workspace's linked repo clone and rebuilding. The sase Python codebase needs to either add notes-schema compatibility for structured records before the window ratchets past 0.32.0, or the window ratchet needs to be blocked until that lands -- otherwise every workspace that rebuilds against a sase-core checkout past bda9efc will have its bead CLI silently break on any note/close mutation.

[2026-08-24T21:54:34Z · sase-sq.5--3] memory_webs flag removed (registry, schema, all call sites, tests); decisions.md core web shipped with 6 decision strands under sase/memory/decisions/, sase memory init clean; fixed a roster.py list-branch wrapping bug (prose-width mismatch vs prettier) with a regression test; fixed a LayoutCollisionError crash in init_memory_handler._memory_web_scope_warnings exposed by the flag removal, with regression coverage via the existing test suite. Also discovered and worked around (this workspace only) a sase-core v0.32.0 bead-notes-schema breaking change that corrupted bead event-stream mutations; recorded as a PROPOSED FOLLOW-UP. just check (full suite) is clean; flag task bead sase-sy closed.

## Dependencies

- **Depends on:** [sase-sq.3](sase-sq.3.md) ✓ · ⧖ 2026-08-24
- **Depends on:** [sase-sq.4](sase-sq.4.md) ✓ · ⧖ 2026-08-24
- **Blocks:** [sase-sq.6](sase-sq.6.md) ✓ · ⧖ 2026-08-24
- **Blocks:** [sase-sq.7](sase-sq.7.md) ◐ · ⧖ 2026-08-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-sq.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-sq.5.md) | [sase-sq.5](sase-sq.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0adb544`](https://github.com/sase-org/sase/commit/0adb544096e9e87001cee9631c98e0a32be6c5d4) | feat(memory): remove memory\_webs flag and ship the decisions web | [sase-sq.5](sase-sq.5.md) | 2026-08-24 17:56:58 EDT |
