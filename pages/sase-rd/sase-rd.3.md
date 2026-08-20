# Bead: sase-rd.3 — sase snippet command group

[Bead Pages](../README.md) / [sase-rd](README.md) / sase-rd.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08h](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08h.md) · **Assignee:** `sase-rd.3` · **Size:** medium
**Created:** 2026-08-20 07:38:53 EDT · **Closed:** 2026-08-20 09:47:29 EDT
**Plan:** [202608/snippets\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202608/snippets_panel.md)

## Description

snippet-cli: expose add, delete, list, and show with rich and machine-readable output over the shared service.

## Notes

[2026-08-20T13:47:03Z · sase-rd.3] PROPOSED FOLLOW-UP: live completion for snippet show/delete triggers — the completion fast path forbids sase.xprompt imports, so catalog-backed trigger candidates were left unkinded like glossary add TERM

[2026-08-20T13:47:29Z · sase-rd.3] Verified sase snippet add/delete/list/show over the shared catalog: parser help and options are alphabetical with short aliases, bare sase snippet delegates to list, rich/names/markdown/json formats and dry-run/force/shadow/read-only/lookup/context/write exits match the contract, restore commands shlex-round-trip multiline templates and spaced paths, epic-symbols for this phase are gone (update_snippet re-keyed to sase-rd.5), and just check passed including an escalated full suite.

[2026-08-20T13:48:38Z · sase-rd.3] Verified sase snippet add/delete/list/show over the shared catalog: parser help and options are alphabetical with short aliases, bare sase snippet delegates to list, rich/names/markdown/json formats and dry-run/force/shadow/read-only/lookup/context/write exits match the contract, restore commands shlex-round-trip multiline templates and spaced paths, epic-symbols for this phase are gone (update_snippet re-keyed to sase-rd.5), and just check passed including an escalated full suite.

## Dependencies

- **Depends on:** [sase-rd.2](sase-rd.2.md) ✓ · ⧖ 2026-08-20
- **Blocks:** [sase-rd.5](sase-rd.5.md) ✓ · ⧖ 2026-08-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-rd.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-rd.3/README.md) | [sase-rd.3](sase-rd.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f3a52bc`](https://github.com/sase-org/sase/commit/f3a52bc0aa11e7939406bb5d998906087bd56254) | feat(snippet): add sase snippet CLI for catalog add/list/show/delete | [sase-rd.3](sase-rd.3.md) | 2026-08-20 09:49:43 EDT |
