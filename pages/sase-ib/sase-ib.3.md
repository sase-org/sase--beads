# Bead: sase-ib.3 — Amortize ACE app startup across tests

[Bead Pages](../README.md) / [sase-ib](README.md) / sase-ib.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wk](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wk/README.md) · **Assignee:** `sase-ib.3` · **Size:** large
**Created:** 2026-08-09 10:31:44 EDT · **Closed:** 2026-08-09 14:33:55 EDT
**Plan:** [202608/fast\_test\_suite\_1.md](https://github.com/sase-org/sase--plans/blob/main/202608/fast_test_suite_1.md)

## Description

boot: cut the cost of one ACE app boot and add a supported way for a group of tests to share one booted app, then migrate the heaviest TUI files onto it without weakening isolation.

## Notes

[2026-08-09T18:33:55Z · sase-ib.3] Implemented ACE app boot amortization. Verified: just lint, just validate, just validate-committed-plans, focused contract tests (130 passed), migrated file normal shared mode (45 passed), and forced isolation lane (45 passed). just check remains blocked by protected memory Markdown formatting issue; filed follow-up bead sase-ih.

## Dependencies

- **Depends on:** [sase-ib.1](sase-ib.1.md) ✓ · ⧖ 2026-08-09
- **Depends on:** [sase-ib.2](sase-ib.2.md) ✓ · ⧖ 2026-08-09
- **Blocks:** [sase-ib.7](sase-ib.7.md) ✓ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ib.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ib.3.md) | [sase-ib.3](sase-ib.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`44bf25f`](https://github.com/sase-org/sase/commit/44bf25f84fecc2ee32c0c6fc8cf58a642f0f632b) | perf(ace): amortize ACE test app startup | [sase-ib.3](sase-ib.3.md) | 2026-08-09 14:35:04 EDT |
