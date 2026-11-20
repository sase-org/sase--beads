# Bead: sase-1tz.3.1 — Targeted defect fixes for the prompt\_prose wire, update races, Telegram transport, bundle caps, and triage conflicts

[Bead Pages](../README.md) / [sase-1tz.3](sase-1tz.3.md) / sase-1tz.3.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.3.md) · **Assignee:** `sase-1tz.3.1.land`
**Created:** 2026-11-20 09:19:04 EST
**Plan:** [202611/defects\_wire\_swap\_telegram\_bundles\_triage.md](https://github.com/sase-org/sase--plans/blob/main/202611/defects_wire_swap_telegram_bundles_triage.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202611/defects_wire_swap_telegram_bundles_triage.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/defects_wire_swap_telegram_bundles_triage.md

<!-- sase:links:end -->

## Description

Host-produced artifact-link origins, including prompt_prose, round-trip through the real sase_core_rs binding, and a contract test fails on any future origin drift. Jobs and launches that overlap a code swap defer and retry instead of failing, an update-overlap reproducer guards that behavior, and a prebuilt-artifact cache miss is a miss rather than a failure. Telegram falls back to plain text only on entity-parse errors, retries per chunk without resending delivered chunks, reports credential and network outages once per state transition, and runs its outbound job only on the sending machine. Every provider root bundle fits its declared max_bytes through compile-time compaction, with a doctor check and a just-check test that catch growth. bead_task_triage recovers from request_id_conflict by advancing the generation.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.3.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.land/README.md) | [sase-1tz.3.1](sase-1tz.3.1.md) | 0 |
