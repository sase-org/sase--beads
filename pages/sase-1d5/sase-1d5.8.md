# Bead: sase-1d5.8 — Remove the beta flag, finish docs, and agent guidance

[Bead Pages](../README.md) / [sase-1d5](README.md) / sase-1d5.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tz](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tz.md) · **Assignee:** `sase-1d5.8` · **Size:** medium
**Created:** 2026-09-30 01:57:19 EDT · **Closed:** 2026-09-30 15:08:47 EDT
**Plan:** [202609/public\_bead\_attachments.md](https://github.com/sase-org/sase--plans/blob/main/202609/public_bead_attachments.md)

## Description

ga: remove public_bead_attachments by deleting its off branches and closing its flag bead. Rewrite the attachment docs around the audience model, put the agent visibility guidance into attach and note help, bead onboard, and the sase_new_task skill source, fix stale GA-era help text, and record the proposed follow-ups.

## Notes

[2026-09-30T18:51:31Z · sase-1d5.8] PROPOSED FOLLOW-UP: private descriptor metadata redaction (report section 5.3) behind a mixed-fleet reader gate — old readers require sha256 today, so redaction needs a reader gate; until then docs and help state that private protects bytes, not names or prose

[2026-09-30T18:51:45Z · sase-1d5.8] PROPOSED FOLLOW-UP: reuse the core attachment scanner in the agents-sidecar transcript and prompt-file publishers, then enable secret scanning plus push protection on the existing public sidecars (publisher needs GH013 handling first so transcript publication cannot stall)

[2026-09-30T18:52:02Z · sase-1d5.8] PROPOSED FOLLOW-UP: file a memory task adding a pointer to the attachment visibility agent guidance in the beads memory template (no memory files change inside this epic per the settled design)

[2026-09-30T18:52:14Z · sase-1d5.8] PROPOSED FOLLOW-UP: consider a fleet streaming blob endpoint for origin-only (local-only, over-cap) objects, but only if origin-only usage grows enough to justify it

[2026-09-30T19:08:19Z · sase-1d5.8--1] PROPOSED FOLLOW-UP: just check feature-flags lint rule 7 fails on closed flag bead sase-1dc (tool_run_escalation definition survives in-tree); reproduces identically on clean HEAD worktree (fails on both sase-1dc and sase-1dg there); removal is owned by in-progress phase sase-1cx.7

[2026-09-30T19:08:47Z · sase-1d5.8--1] ga verified: public_bead_attachments registry+schema entries and Off branches removed (On unconditional), flag bead sase-1dg closed, zero public_bead_attachments refs in src/tools/tests/schema, no epic-symbols; tests/test_bead/test_attachment_audience_cli.py (14) and tests/main/test_repo_init_handler_creation.py (37) pass; just check green on all gates except feature-flags rule 7 for unrelated tool_run_escalation (sase-1dc), proven pre-existing via clean-HEAD worktree and recorded as PROPOSED FOLLOW-UP owned by sase-1cx.7

## Dependencies

- **Depends on:** [sase-1d5.2](sase-1d5.2.md) ✓ · ⧖ 2026-09-30
- **Depends on:** [sase-1d5.5](sase-1d5.5.md) ✓ · ⧖ 2026-09-30
- **Depends on:** [sase-1d5.6](sase-1d5.6.md) ✓ · ⧖ 2026-09-30
- **Depends on:** [sase-1d5.7](sase-1d5.7.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1d5.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1d5.8.md) | [sase-1d5.8](sase-1d5.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7885562`](https://github.com/sase-org/sase/commit/7885562f5474bd75b4cef0c6a014a09d1f7a44a2) | feat(beads): graduate public bead attachments to GA, remove beta flag (sase-1d5.8) | [sase-1d5.8](sase-1d5.8.md) | 2026-09-30 15:39:42 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1cj.12.land][1] | Check whether the in-progress beta-flag removal phase covers the surviving public_bead_attachments flag definition | 2 |
| read-by | [agent:sase-1d5.8--1][2] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cj.12.land/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1d5.8.md

<!-- sase:referenced-by:end -->
