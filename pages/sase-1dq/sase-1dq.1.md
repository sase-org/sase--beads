# Bead: sase-1dq.1 — Gated current-word completion in the sase-core prediction engine

[Bead Pages](../README.md) / [sase-1dq](README.md) / sase-1dq.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u0.md) · **Assignee:** `sase-1dq.1` · **Size:** medium
**Created:** 2026-09-30 16:38:20 EDT · **Closed:** 2026-09-30 22:36:17 EDT
**Plan:** [202609/next\_word\_autosuggest.md](https://github.com/sase-org/sase--plans/blob/main/202609/next_word_autosuggest.md)

## Description

core-word-completion: add an opt-in complete_current_word request and a word_completion result to sase_core::prompt_prediction. It uses a prefix-restricted gate with a conservative denominator, per-preset min_prefix_chars, typed-case suffixes, and gated continuation after the completed word, with no wire schema bump.

## Notes

[2026-10-01T02:36:17Z · sase-1dq.1] core-word-completion done in sase-core prompt_prediction: complete_current_word request + word_completion{prefix,word,suffix} result (schema stays v1, None omits the key so old readers see no change); split_partial_word detection; prefix-restricted gate with conservative denominator (restricted+dropped mass), per-preset min_prefix_chars (3/2/1), typed-case suffix incl. ALLCAPS + curly-apostrophe, gated continuation capped so max_words counts the completed word; excluded words never completed; invalid prefixes fall through to the identical boundary path. Verified: just test -p sase_core prompt_prediction 106 passed; just test -p sase_core_py prompt_prediction 6 passed; sase tool run check succeeded; epic-symbols clean. Ignored release perf test extended with prefix_p95 reporting but not executed (release build exceeds the single-turn command ceiling despite a warmed cache; rerun with a longer budget). Pin move left for word-completion-calibration per plan.

## Dependencies

- **Blocks:** [sase-1dq.2](sase-1dq.2.md) ◐ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1dq.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1dq.1/README.md) | [sase-1dq.1](sase-1dq.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@cd26011`](https://github.com/sase-org/sase-core/commit/cd260110a21a217c19de585584e7f83260d2986d) | feat(prompt\_prediction): gated current-word completion | [sase-1dq.1](sase-1dq.1.md) | 2026-09-30 22:39:26 EDT |
