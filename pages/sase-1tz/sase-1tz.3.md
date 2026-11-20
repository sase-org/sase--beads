# Bead: sase-1tz.3 — Targeted high-confidence defect fixes (items 6-10)

[Bead Pages](../README.md) / [sase-1tz](README.md) / sase-1tz.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1eb](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1eb.md) · **Assignee:** `sase-1tz.3` · **Size:** xlarge
**Created:** 2026-11-19 07:09:38 EST
**Plan:** [202611/notification\_log\_audit\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202611/notification_log_audit_fixes.md)

## Description

defects: add the prompt_prose artifact-link wire variant with a binding contract test, close the remaining runtime-update races, fix Telegram fallback, retry, and scope semantics, keep provider instruction bundles under their caps with a size gate, and advance bead_task_triage's generation on request_id_conflict.

## Notes

[2026-11-20T14:30:34Z · sase-1tz.3.1.8] tg_scope (sase-1tz.3.1.8): telegram outbound routine now athena-only in chezmoi source; apollo was wasting 12.7 tg_outbound ticks/min.

[2026-11-20T14:32:32Z · sase-1tz.3.1.5] prebuild_miss (sase-1tz.3.1.5): apollo baseline 23/45 prebuild attempts were commit-mismatch misses with nonzero consume rc (was 18/37 in the audit).

## Dependencies

- **Depends on:** [sase-1tz.2](sase-1tz.2.md) ✓ · ⧖ 2026-11-19
- **Blocks:** [sase-1tz.4](sase-1tz.4.md) ◐ · ⧖ 2026-11-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.3.md) | [sase-1tz.3](sase-1tz.3.md) | 0 |
