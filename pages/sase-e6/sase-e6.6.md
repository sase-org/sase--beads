# Bead: sase-e6.6 — Read surfaces, docs, and end-to-end verification

[Bead Pages](../README.md) / [sase-e6](README.md) / sase-e6.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.athena.rs` · **Assignee:** `sase-e6.6` · **Size:** small
**Created:** 2026-08-02 13:22:59 UTC · **Closed:** 2026-08-02 18:41:17 UTC
**Plan:** [202608/stored\_prompt\_duality.md](https://github.com/sase-org/sase--plans/blob/main/202608/stored_prompt_duality.md)

## Description

surfaces: teach the ACE chat detail view and the `sase agent prompts show` / `sase chat show` commands about the two renderings, update the documentation, and verify the whole path end to end.

## Notes

[2026-08-02T18:41:03Z · sase-e6.6] PROPOSED FOLLOW-UP: xprompt link resolver remaps workspace-local definitions under $HOME into chezmoi dot_local/state URLs - fakey verification linked #sync/#git to dotfiles paths that likely are not published source definitions.

[2026-08-02T18:41:17Z · sase-e6.6] Implemented ACE chat detail rendering, prompt/chat CLI rendering selectors, docs, and focused tests. Verified targeted pytest suite (69 passed), CLI help for chat/prompts show, fakey chat XPrompt links with unknown refs left literal, and full just check. Local agent prompt archive validate skipped because agents sidecar has not been created.

[2026-08-02T18:42:47Z · sase-e6.6] Verified focused pytest suite, CLI prompt selectors, fakey XPrompt link behavior, and full just check.

## Dependencies

- **Depends on:** [sase-e6.4](sase-e6.4.md) ✓
- **Depends on:** [sase-e6.5](sase-e6.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| bbugyi200.athena.sase-e6.6 | [sase-e6.6](sase-e6.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| gh\_sase-org\_\_sase | [`e3ca2c1`](https://github.com/sase-org/sase/commit/e3ca2c11c53040a67e50010e683f270efc1c624a) | feat: expose stored prompt renderings | [sase-e6.6](sase-e6.6.md) | 2026-08-02 18:43:36 |
