# Bead: sase-zr.2 — Separate durable decision acceptance from slow execution

[Bead Pages](../README.md) / [sase-zr](README.md) / sase-zr.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.athena.0js` · **Assignee:** `sase-zr.2` · **Size:** medium
**Created:** 2026-09-12 05:06:14 EDT
**Plan:** [202609/prompt\_gate\_approval.md](https://github.com/sase-org/sase--plans/blob/main/202609/prompt_gate_approval.md)

## Description

durable-approval-publication: Implement shared acceptance and execution policy in sase-core with thin sase orchestration. Validate and durably reserve one decision and its supervised proc before publishing approval and dismissing the notification. Keep response.json's existing execution-complete contract and required host archive receipts; project accepted plan decisions separately from terminal shell state. Route ACE-facing plan APIs, CLI, mobile, and auto approval through the same policy. Move archive/network/launch work behind the acceptance boundary, publish terminal shell state before follow-up, and make crash recovery and retry ownership explicit. Preserve branch inputs, source, archive protocol, wait and coder choices, cancellation, and partial attempts. Prove acceptance remains visible while archive/launch barriers are blocked, and prove duplicate or racing submissions cannot duplicate work.

## Dependencies

- **Depends on:** [sase-zr.1](sase-zr.1.md) ✓ · ⧖ 2026-09-12
- **Blocks:** [sase-zr.3](sase-zr.3.md) ◐ · ⧖ 2026-09-12
- **Blocks:** [sase-zr.4](sase-zr.4.md) ◐ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-zr.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-zr.2/README.md) | [sase-zr.2](sase-zr.2.md) | 0 |
