# Bead: sase-zr.7.1.1.4 — Failure results for requesters and deduped recovery notifications

[Bead Pages](../README.md) / [sase-zr.7.1.1](sase-zr.7.1.1.md) / sase-zr.7.1.1.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-zr.7.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-zr.7.1.md) · **Assignee:** `sase-zr.7.1.1.4` · **Size:** medium
**Created:** 2026-09-17 06:47:35 EDT
**Plan:** [202609/gate\_decision\_integrity\_1.md](https://github.com/sase-org/sase--plans/blob/main/202609/gate_decision_integrity_1.md)

## Description

failure_surfacing: in sase, give poll_gate a failed status, record owner_lost on the poll and reclaim paths, keep waiting requesters honest through their deadlines, update sase gate wait and the other requesters, publish one deduped GateExecutionFailed notification per failure with resume/restart/cancel recovery, dismiss it on success, supersede or cancel, add a minimal ACE fallback for the new action, and run the combined verification.

## Dependencies

- **Depends on:** [sase-zr.7.1.1.3](sase-zr.7.1.1.3.md) ◐ · ⧖ 2026-09-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-zr.7.1.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-zr.7.1.1.4/README.md) | [sase-zr.7.1.1.4](sase-zr.7.1.1.4.md) | 0 |
