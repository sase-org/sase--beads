# Bead: sase-ix.3 — Making withheld corroboration visible

[Bead Pages](../README.md) / [sase-ix](README.md) / sase-ix.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.x9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.x9/README.md) · **Assignee:** `sase-ix.3` · **Size:** small
**Created:** 2026-08-10 10:50:38 EDT · **Closed:** 2026-08-10 12:22:31 EDT
**Plan:** [202608/plus\_one\_post\_close\_reopen\_race.md](https://github.com/sase-org/sase--plans/blob/main/202608/plus_one_post_close_reopen_race.md)

## Description

surfaces: render post-close corroboration on the closed bead across the CLI, ACE, generated pages, and gate previews, and teach the task-filing skill when the override applies.

## Notes

[2026-08-10T16:21:37Z · sase-ix.3] PROPOSED FOLLOW-UP: committed plan validation rejects existing large tale plans — `just check` fails before tests on 21 committed 202608 tale plans whose size is `large`; these predate this phase and need plan metadata cleanup or validator migration.

[2026-08-10T16:22:31Z · sase-ix.3] Implemented post-close +1 visibility across CLI/detail/list/search JSON, ACE rows/detail, generated pages, TaskTriage/BeadSnooze payloads, SQLite/JSON codecs, and the sase_new_task source template. Verified with .venv/bin/pytest targeted bead/gate/ACE/skill tests (118 passed), cargo test -p sase_core bead::search::tests::matches_every_searchable_field, and just check through lint/mypy/SASE validation; just check is blocked by preexisting committed-plan tale-size errors recorded as a PROPOSED FOLLOW-UP.

[2026-08-10T16:23:20Z · sase-ix.3] Verified targeted Python bead/gate/ACE/skill tests passed; Rust search unit passed; just check passed lint/mypy and failed only on preexisting 21 large tale plan validation issues recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-ix.2](sase-ix.2.md) ✓ · ⧖ 2026-08-10
- **Blocks:** [sase-ix.4](sase-ix.4.md) ◐ · ⧖ 2026-08-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ix.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ix.3/README.md) | [sase-ix.3](sase-ix.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`187085a`](https://github.com/sase-org/sase/commit/187085a80b60f59641dfd076a9cb5cea9e499fca) | feat(beads): surface withheld post-close corroboration | [sase-ix.3](sase-ix.3.md) | 2026-08-10 12:24:21 EDT |
