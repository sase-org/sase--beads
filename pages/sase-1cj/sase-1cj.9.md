# Bead: sase-1cj.9 — Prequential replay harness and preset calibration

[Bead Pages](../README.md) / [sase-1cj](README.md) / sase-1cj.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.2x` · **Assignee:** `sase-1cj.9` · **Size:** medium
**Created:** 2026-09-29 07:14:36 EDT · **Closed:** 2026-09-29 14:19:22 EDT
**Plan:** [202609/prompt\_next\_word\_prediction.md](https://github.com/sase-org/sase--plans/blob/main/202609/prompt_next_word_prediction.md)

## Description

replay-harness: a Rust prequential replay evaluator plus a tools/prompt_prediction_replay script that prints aggregate-only accuracy, coverage, precision, keystroke-savings, run-length, latency, and memory tables by cohort, then calibrate the confidence presets.

## Notes

[2026-09-29T18:18:45Z · sase-1cj.9--1] PROPOSED FOLLOW-UP: _lint-patch-stitch-terminology fails on 14 pre-existing defects in committed sase-core fixture crates/sase_core/tests/fixtures/note_attachment/at_bearing_notes.jsonl (last touched by 39324ac, file git-clean, reproduces identically on clean base); needs land-agent triage, not phase work

[2026-09-29T18:19:03Z · sase-1cj.9--1] PROPOSED FOLLOW-UP: ratchet sase-core-revision.txt past the sase-core replay commit once it lands (core changes are uncommitted in sase/repos/linked/sase-core; agents never commit)

[2026-09-29T18:19:22Z · sase-1cj.9--1] Replay harness calibrated and verified: extended Rust sweep with per-point novel coverage/precision (wire.rs, replay.rs + unit tests), mirrored in Python wire dataclass and replay tool table; sase-core check green; wheel rebuilt; replay over 11500 rows (4275 typed, 188134 positions) meets all targets — balanced overall 89.4pct/novel 65.7pct (preset moved to min_p 0.75/min_support 4), cautious 89.4pct, eager 75.2pct; aggregate table+method recorded in docs/rust_backend.md; 76 prompt-prediction tests pass; ruff/mypy/symvision/validate/plans green. Pre-existing _lint-patch-stitch-terminology failure (14 defects in committed sase-core note_attachment fixture, clean-base identical) recorded as follow-up; Justfile stale sase-1cj.7 exemptions re-keyed to open epic sase-1cj.

## Dependencies

- **Blocks:** [sase-1cj.10](sase-1cj.10.md) ◐ · ⧖ 2026-09-29
- **Depends on:** [sase-1cj.4](sase-1cj.4.md) ✓ · ⧖ 2026-09-29
- **Depends on:** [sase-1cj.5](sase-1cj.5.md) ✓ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1cj.9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1cj.9.md) | [sase-1cj.9](sase-1cj.9.md) | 0 |
