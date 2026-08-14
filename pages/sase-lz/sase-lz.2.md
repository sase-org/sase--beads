# Bead: sase-lz.2 — Parse-based selector detection and prefilled custom input

[Bead Pages](../README.md) / [sase-lz](README.md) / sase-lz.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.014](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.014.md) · **Assignee:** `sase-lz.2` · **Size:** small
**Created:** 2026-08-14 10:49:30 EDT · **Closed:** 2026-08-14 11:41:57 EDT
**Plan:** [202608/models\_panel\_pool\_authoring.md](https://github.com/sase-org/sase--plans/blob/main/202608/models_panel_pool_authoring.md)

## Description

selector-edit-plumbing: add a shared TUI selector helper module over the existing llm_provider API, replace the substring selector sniffing in the alias Edit flow with real parsing plus per-member safety checks, and give the custom-model input an initial value so editing an existing selector no longer means retyping it.

## Notes

[2026-08-14T15:41:57Z · sase-lz.2] Added shared models_panel_selector.py helper wrapping llm_provider parsing; replaced substring selector sniffing in the alias Edit flow with real parse-based detection plus per-member cycle/unknown-alias checks; CustomModelInputModal now accepts initial= to prefill on edit. just install succeeded; just check ran twice (full lint gates + scoped test suite, ~30k tests) — lint gates clean both runs, only failures were 3 then 1 differing, unrelated atomic-replace-style tests (monitor_supervise, history/test_prompt, config_center_state) that each pass in isolation, confirming pre-existing flakiness under parallel load, not a regression. tests/test_models_panel_edit.py (19 tests, including 4 new ones for this phase) pass standalone.

## Dependencies

- **Depends on:** [sase-lz.1](sase-lz.1.md) ✓ · ⧖ 2026-08-14
- **Blocks:** [sase-lz.3](sase-lz.3.md) ◐ · ⧖ 2026-08-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-lz.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-lz.2/README.md) | [sase-lz.2](sase-lz.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a605d5c`](https://github.com/sase-org/sase/commit/a605d5c09e4e43007d8a019c34aaab233d078fac) | refactor(ace): parse selector expressions instead of sniffing substrings in alias Edit | [sase-lz.2](sase-lz.2.md) | 2026-08-14 11:43:11 EDT |
