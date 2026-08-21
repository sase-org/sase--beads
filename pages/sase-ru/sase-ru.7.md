# Bead: sase-ru.7 — Make completion refresh unconditional

[Bead Pages](../README.md) / [sase-ru](README.md) / sase-ru.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.09i](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.09i.md) · **Assignee:** `sase-ru.7` · **Size:** small
**Created:** 2026-08-21 10:44:29 EDT · **Closed:** 2026-08-21 12:43:41 EDT
**Plan:** [202608/open\_feature\_flag\_closeout.md](https://github.com/sase-org/sase--plans/blob/main/202608/open_feature_flag_closeout.md)

## Description

completion_retirement: remove completion_refresh_on_update after its soak passes while preserving managed-file skips, update success, failure isolation, and bead integrity.

## Notes

[2026-08-21T16:28:36Z · sase-ru.7] Inventory before retirement: sase flag list -j still listed completion_refresh_on_update (sase-qg open, beta, default Off, env override On). Soak evidence already on sase-qg (sase-ru.2, file:explicit:247001ef31ee220528ea9398). Removed Off early-return in maybe_refresh_installed_completions, deleted FeatureFlag member + registry/schema/docs, converted Off tests to dry-run/upgrade-failure eligibility. Focused pytest 72 passed.

[2026-08-21T16:30:32Z · sase-ru.7] PROPOSED FOLLOW-UP: tools/check_feature_flags remains red after sase-qg close — rule 7 for closed beads sase-qe/qh/qq/qf whose definitions still live in this tree until their retirement phases land, and rule 8 for out-of-scope sase-rc (artifact_links). Not caused by completion_refresh_on_update retirement.

[2026-08-21T16:42:50Z · sase-ru.7] PROPOSED FOLLOW-UP: escalated full suite 62 failed unrelated to completion refresh — ConfigHubPane vs ConfigPane TUI, missing sase-xprompt-lsp, runner-slot parking, contract_manifest budget, artifact doctor, skills inventory, fakey e2e timeout; none in tests/completion or update refresh.

[2026-08-21T16:43:41Z · sase-ru.7] Verified completion_refresh_on_update retirement: soak evidence on sase-qg (sase-ru.2, file:explicit:247001ef31ee220528ea9398). Removed Off early-return; successful sase update now always refreshes installed completions. Preserved chezmoi skips, per-shell isolation, nonfatal fallback, stamps, zcompile. Registry/schema/docs retired; sase-qg closed. Focused pytest 72 passed (install, soak, update eligibility/failure, consumers, schema). just check red only on pre-existing unrelated _lint-flags/_lint-symvision/_lint-toobig. Escalated suite 35641 passed; 62 failures unrelated. No --epic-symbol leftovers.

## Dependencies

- **Blocks:** [sase-ru.12](sase-ru.12.md) ◐ · ⧖ 2026-08-21
- **Depends on:** [sase-ru.2](sase-ru.2.md) ✓ · ⧖ 2026-08-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ru.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ru.7/README.md) | [sase-ru.7](sase-ru.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8143f4c`](https://github.com/sase-org/sase/commit/8143f4c61071d819883e9309d7e8ead70767a4e3) | feat(completion): refresh installed completions after every successful update | [sase-ru.7](sase-ru.7.md) | 2026-08-21 12:47:41 EDT |
