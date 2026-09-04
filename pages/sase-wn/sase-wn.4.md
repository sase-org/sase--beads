# Bead: sase-wn.4 — Make wait\_checks and bead\_claim\_checks incremental

[Bead Pages](../README.md) / [sase-wn](README.md) / sase-wn.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.o.f0` · **Assignee:** `sase-wn.4` · **Size:** medium
**Created:** 2026-09-04 12:11:05 EDT
**Plan:** [202609/sase\_idle\_cpu\_diet.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_idle_cpu_diet.md)

## Description

chop-incremental-scans: invert both scan chops so their cheap short-circuit runs before the full O(all-artifacts) walk - wait_checks consults waiting markers first and resolves only referenced dependencies (via the agent artifact index where it suffices), bead_claim_checks runs its owner pre-pass before scanning; identical outputs on the non-skip path.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-wn.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-wn.4/README.md) | [sase-wn.4](sase-wn.4.md) | 0 |
