# Bead: sase-wn.8 — Small ace I/O fixes (agents-sync reads, bead N+1)

[Bead Pages](../README.md) / [sase-wn](README.md) / sase-wn.8

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.o.f0` · **Assignee:** `sase-wn.8` · **Size:** small
**Created:** 2026-09-04 12:11:14 EDT
**Plan:** [202609/sase\_idle\_cpu\_diet.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_idle_cpu_diet.md)

## Description

ace-io-hygiene: replace the byte-at-a-time _read_until_nul in agents_sync git blob reads with buffered reads, and batch the per-bead show() N+1 in the prompt-panel detail header summary.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-wn.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-wn.8/README.md) | [sase-wn.8](sase-wn.8.md) | 0 |
