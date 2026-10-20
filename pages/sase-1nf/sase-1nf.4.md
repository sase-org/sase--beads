# Bead: sase-1nf.4 — Lossless EpicFollowView encoding for bundles and cleanup payloads

[Bead Pages](../README.md) / [sase-1nf](README.md) / sase-1nf.4

**Status:** ○ open · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.12i](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.12i.md) · **Assignee:** `sase-1nf.4` · **Size:** medium
**Created:** 2026-10-20 13:36:14 EDT
**Plan:** [202610/athena\_apollo\_audit\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/athena_apollo_audit_fixes.md)

## Description

cleanup-encoding: encode wait_epic_follows explicitly in the shared agent bundle encoder, decode it back into EpicFollowView, guard against the next non-JSON field, and make the cleanup test harness round-trip payloads through JSON. Closes sase-1nb.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nf.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.4/README.md) | [sase-1nf.4](sase-1nf.4.md) | 0 |
