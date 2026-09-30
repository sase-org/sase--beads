# Bead: sase-1cj.12 — Finish next-word prediction correctness, budgets, and calibration

[Bead Pages](../README.md) / [sase-1cj](README.md) / sase-1cj.12

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1cj.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1cj.land.md) · **Assignee:** `sase-1cj.12.land`
**Created:** 2026-09-29 18:29:13 EDT
**Plan:** [202609/finish\_prompt\_next\_word\_prediction.md](https://github.com/sase-org/sase--plans/blob/main/202609/finish_prompt_next_word_prediction.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/finish_prompt_next_word_prediction.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/finish_prompt_next_word_prediction.md

<!-- sase:links:end -->

## Description

The next-word prediction feature from epic sase-1cj meets its own contract. The core blocks every structural tail, including `%{...}` alternation. Support counts and confidence presets are honest and calibrated. Predict meets the p95 ≤ 0.5 ms local budget on real history. The TUI ghost never goes stale or inserts in the wrong place. The missing goldens, the archive default decision, and the epic-symbol cleanup are done, so sase-1cj can close.

## Notes

[2026-09-30T12:45:48Z · sase-1co.land] DISCOVERED ISSUE (sase-1co land agent, 2026-09-30, clean master 63bde575f0; also red in Master Gate run 36714816529 at d6f2b237a6): tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection fails - tests/contract_manifest.txt is stale. The contract marker now selects tests/test_prompt_prediction_replay_sources.py (added by 5480df7af8, feat(sase-1cj.10) cross-machine prompt archive) and tests/test_validate_test_environment_tool.py, neither in the committed manifest. Fix: just refresh-contract-manifest and commit. Fails in isolation on a clean tree, so not a flake.

[2026-09-30T13:17:57Z · sase-1co.land] DISCOVERED ISSUE (sase_12 conflict-repair agent, 2026-09-30, master 28ae626363 / ff39548590; linked sase-core 7806f58): tools/validate_sase_core_rs prompt-prediction predict probe now fails deterministically, so `sase tool run check` dies in `_setup` (Justfile line 137/141) before any lint or test stage whenever sase_core_rs is rebuilt. Probe (3-row 'help me implement the ...' corpus, confidence=balanced, text_before_cursor='help me implement') expects confident=True and ghost[:1]==['the'], but the binding returns confident=False, ghost=[] with candidate 'the' (probability 1.0, support 3, source_shares history 0.5/project 0.5). Caused by sase-core cfc6385 (fix(prompt_prediction): salvage unlanded core-correctness patch, sase-1cj.12.1), which both sase-core pins 3bb901b and 6dc38b4 contain; the validator was not updated with it. Repro: .venv/bin/python tools/validate_sase_core_rs --sase-core-dir sase/repos/linked/sase-core. Fix: update the probe expectation (or corpus) to the new balanced-confidence gating, coordinated with sase-1cj.12.4's preset recalibration. ToolRun 807841f4d4bfd2a3c765ca4b74150dc1.

[2026-09-30T15:50:16Z · sase-1d8.land] DISCOVERED ISSUE corroboration from sase-1d8.1 note #1, sase-1d8.3 note #1, and sase-1d8.4 note #1: each independently found the same clean-base tools/validate_sase_core_rs prompt-prediction probe mismatch (balanced returns confident=False, ghost=[] where validator expects True/[the]). Existing note #2 on this active epic identifies the core calibration change and directs coordination with phase sase-1cj.12.4; no separate task.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1cj.12.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cj.12.land/README.md) | [sase-1cj.12](sase-1cj.12.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1cj.12.2][1] | Need parent epic scope for tui-fixes handoff | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cj.12.2/README.md

<!-- sase:referenced-by:end -->
