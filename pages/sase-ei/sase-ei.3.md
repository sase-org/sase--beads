# Bead: sase-ei.3 — Historical agent identity and chat migration

[Bead Pages](../README.md) / [sase-ei](README.md) / sase-ei.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-eh](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-eh/README.md) · **Assignee:** `sase-ei.3` · **Size:** large
**Created:** 2026-08-03 08:48:07 UTC · **Closed:** 2026-08-03 13:27:22 UTC
**Plan:** [202608/historical\_bead\_reprefix.md](https://github.com/sase-org/sase--plans/blob/main/202608/historical_bead_reprefix.md)

## Description

agent-history: migrate derived bead-named agents, structured run artifacts, chats, registries, and agents-sidecar bundles while preserving old hosted agent links through explicit compatibility aliases.

## Notes

[2026-08-03T13:27:22Z · sase-ei.3] Implemented historical agent identity migration preview/apply API, agents-sidecar compatibility aliases, alias-aware regeneration planning, and focused audit/tests. Verified with just install, focused migration/sidecar/audit tests, and just check through all non-test gates; the only full-suite failure was the known flaky bead contention test, which passed on focused rerun and was corroborated on sase-e2.

## Dependencies

- **Depends on:** [sase-ei.1](sase-ei.1.md) ✓
- **Blocks:** [sase-ei.4](sase-ei.4.md) ◐
