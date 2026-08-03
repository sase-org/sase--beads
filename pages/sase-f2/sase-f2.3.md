# Bead: sase-f2.3 — Read surfaces and documentation

[Bead Pages](../README.md) / [sase-f2](README.md) / sase-f2.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ej.land.w2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ej.land.w2/README.md) · **Assignee:** `sase-f2.3` · **Size:** medium
**Created:** 2026-08-03 14:48:36 EDT · **Closed:** 2026-08-03 15:59:34 EDT
**Plan:** [202608/revert\_stored\_prompt\_duality.md](https://github.com/sase-org/sase--plans/blob/main/202608/revert_stored_prompt_duality.md)

## Description

surfaces: revert the ACE Chats detail pane, the `sase chat show` and `sase agent prompts show` rendering selectors, and prompt search's section stripping, then delete `chat_prompt_sections.py` and remove every documentation paragraph describing the two stored renderings.

## Notes

[2026-08-03T19:59:34Z · sase-f2.3] Removed read-side stored prompt rendering selectors/helper/docs; verified focused pytest for changed surfaces, tests/test_xprompt_links.py, just check, and just test-visual.

## Dependencies

- **Depends on:** [sase-f2.1](sase-f2.1.md) ✓
- **Depends on:** [sase-f2.2](sase-f2.2.md) ✓
- **Blocks:** [sase-f2.4](sase-f2.4.md) ✓
- **Blocks:** [sase-f2.5](sase-f2.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-f2.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-f2.3/README.md) | [sase-f2.3](sase-f2.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1239c5f`](https://github.com/sase-org/sase/commit/1239c5f5c834782fa5ef90f5d21e471a0402d22d) | feat(cli)!: remove stored prompt rendering surfaces | [sase-f2.3](sase-f2.3.md) | 2026-08-03 16:01:37 EDT |
