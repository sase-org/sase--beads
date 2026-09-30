# Bead: sase-1dq.1 — Gated current-word completion in the sase-core prediction engine

[Bead Pages](../README.md) / [sase-1dq](README.md) / sase-1dq.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u0.md) · **Assignee:** `sase-1dq.1` · **Size:** medium
**Created:** 2026-09-30 16:38:20 EDT
**Plan:** [202609/next\_word\_autosuggest.md](https://github.com/sase-org/sase--plans/blob/main/202609/next_word_autosuggest.md)

## Description

core-word-completion: add an opt-in complete_current_word request and a word_completion result to sase_core::prompt_prediction. It uses a prefix-restricted gate with a conservative denominator, per-preset min_prefix_chars, typed-case suffixes, and gated continuation after the completed word, with no wire schema bump.

## Dependencies

- **Blocks:** [sase-1dq.2](sase-1dq.2.md) ◐ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1dq.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1dq.1.md) | [sase-1dq.1](sase-1dq.1.md) | 0 |
