# Bead: sase-s1.4 — Recalibrate the persistent-query absolute performance floor

[Bead Pages](../README.md) / [sase-s1](README.md) / sase-s1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0al](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0al.md) · **Assignee:** `sase-s1.4` · **Size:** small
**Created:** 2026-08-22 12:30:21 UTC · **Closed:** 2026-08-22 13:00:12 UTC
**Plan:** [202608/restore\_github\_actions.md](https://github.com/sase-org/sase--plans/blob/main/202608/restore_github_actions.md)

## Description

query-perf-floor: add an evidence-backed per-anchor ceiling while preserving the hardware-independent Rust-versus-Python gate.

## Notes

[2026-08-22T12:59:56Z · sase-s1.4] PROPOSED FOLLOW-UP: just check fails at sase validate / init memory --check because chezmoi home memory files and provider shims are stale versus this workspace; the query-perf-floor diff did not touch memory files and lint plus test-scoped both passed.

[2026-08-22T13:00:12Z · sase-s1.4] Added a 2.90x per-anchor rust_slowdown_factor for evaluate_query_many.synthetic_1000_specs.persistent_query_keystroke from eight consecutive hosted perf-floors reports (runs 32532695452-32568874089, 178.28-184.36us) plus the 147.07us local reproduction, yielding a 193.44us ceiling (~4.9% above the hosted max) while leaving must_beat_python true. just phase7-perf-check passed (rust 157.37us vs python 4424.24us, ~28x). Tests pin the override evidence and that 184.36us passes, 2x the hosted max fails the absolute floor, and a slower-than-Python rust median still fails. just check lint gates passed; test-scoped selected 54 files / 571 passed. sase validate init memory --check is red for unrelated chezmoi home memory drift.

## Dependencies

- **Blocks:** [sase-s1.6](sase-s1.6.md) ◐ · ⧖ 2026-08-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-s1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-s1.4/README.md) | [sase-s1.4](sase-s1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0438e70`](https://github.com/sase-org/sase/commit/0438e70e702480279e4a9b40b309e695cc65f009) | test(perf): recalibrate persistent-query absolute floor | [sase-s1.4](sase-s1.4.md) | 2026-08-22 13:06:45 UTC |
