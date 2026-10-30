# Bead: sase-1pu.1 — Scan and safely recover prompt migrations into the agents sidecar (sase-1os)

[Bead Pages](../README.md) / [sase-1pu](README.md) / sase-1pu.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pn.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pn.land.md) · **Assignee:** `sase-1pu.1` · **Size:** medium
**Created:** 2026-10-29 19:19:00 EDT
**Plan:** [202610/task\_backlog\_epic\_3.md](https://github.com/sase-org/sase--plans/blob/main/202610/task_backlog_epic_3.md)

## Description

prompt-migration-protection: route the one-time legacy prompt migration through the shared publication-protection scanner before staging, and stop recommending a raw push after a GH013 rejection. Preserve the existing private/quarantine behavior and sanitized diagnostics. Add regression coverage for clean migration, a detected secret, and a rejected push; ensure no secret value is emitted or replayed.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pu.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pu.1/README.md) | [sase-1pu.1](sase-1pu.1.md) | 0 |
