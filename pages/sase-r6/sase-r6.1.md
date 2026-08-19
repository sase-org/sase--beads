# Bead: sase-r6.1 — Page-size config and shared limit helpers

[Bead Pages](../README.md) / [sase-r6](README.md) / sase-r6.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.086](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.086.md) · **Assignee:** `sase-r6.1` · **Size:** small
**Created:** 2026-08-19 17:09:39 EDT · **Closed:** 2026-08-19 18:24:04 EDT
**Plan:** [202608/load\_more\_ctrl\_j.md](https://github.com/sase-org/sase--plans/blob/main/202608/load_more_ctrl_j.md)

## Description

config: add ace.page_size (default 100) and the shared limit-token helpers every later phase uses.

## Notes

[2026-08-19T22:09:09Z · sase-r6.1] PROPOSED FOLLOW-UP: tests/test_global_state_leak_detector.py::test_snapshot_includes_live_config_token_refresh_threads failed once in a 10-worker full suite (live-thread global missing from snapshot) and passed in isolation — likely an xdist flake, not caused by this phase.

[2026-08-19T22:24:04Z · sase-r6.1--1] just check passed (lint + scoped tests escalated to full suite). ace.page_size default 100 is in default_config.yml and sase.schema.json; get_ace_page_size() and limit-token helpers (extract/ensure/replace/adjust_limit, LimitTokenError) are in tree with tests in test_limit_token.py, test_ace_page_size.py, and test_config_schema_ace.py. epic-symbols sase-r6.1 reports none; unused helpers remain whitelisted on still-open sase-r6.2/r6.3/r6.4. Prior contract-manifest failure was fixed by moving schema tests out of the contract-marked file. Isolation-only leak-detector flake recorded as PROPOSED FOLLOW-UP.

[2026-08-19T22:26:19Z · sase-r6.1--1] just check passed (lint + scoped tests escalated to full suite). ace.page_size default 100 is in default_config.yml and sase.schema.json; get_ace_page_size() and limit-token helpers (extract/ensure/replace/adjust_limit, LimitTokenError) are in tree with tests in test_limit_token.py, test_ace_page_size.py, and test_config_schema_ace.py. epic-symbols sase-r6.1 reports none; unused helpers remain whitelisted on still-open sase-r6.2/r6.3/r6.4. Prior contract-manifest failure was fixed by moving schema tests out of the contract-marked file. Isolation-only leak-detector flake recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Blocks:** [sase-r6.2](sase-r6.2.md) ✓ · ⧖ 2026-08-19
- **Blocks:** [sase-r6.3](sase-r6.3.md) ◐ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-r6.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-r6.1.md) | [sase-r6.1](sase-r6.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`35ba42c`](https://github.com/sase-org/sase/commit/35ba42ce77d39ad9974bac8b4ab8869f0b30ff41) | feat(ace): add page\_size config and shared limit-token helpers | [sase-r6.1](sase-r6.1.md) | 2026-08-19 18:27:42 EDT |
