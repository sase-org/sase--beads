# Bead: sase-1tz.3.1.7 — Collapse repeated Telegram credential and network failures into degraded states

[Bead Pages](../README.md) / [sase-1tz.3.1](sase-1tz.3.1.md) / sase-1tz.3.1.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.3.md) · **Assignee:** `sase-1tz.3.1.7` · **Size:** medium
**Created:** 2026-11-20 09:19:07 EST · **Closed:** 2026-11-20 11:04:38 EST
**Plan:** [202611/defects\_wire\_swap\_telegram\_bundles\_triage.md](https://github.com/sase-org/sase--plans/blob/main/202611/defects_wire_swap_telegram_bundles_triage.md)

## Description

tg_degraded: outbound and receiver track a persisted credential_unavailable or network_degraded state. Each logs one line on entering a state, rate-limited summaries while degraded, and one line on recovery, with no tracebacks for transient errors. One SASE notice fires per transition. Credential lookups are negatively cached for a short window.

## Notes

[2026-11-20T16:03:59Z · sase-1tz.3.1.7] MEASURE (tg_degraded, read-only, 2026-11-20). BEFORE: athena ~/.sase/axe/logs/lumberjack-telegram.log (truncated; window 2026-11-16 10:44 to 2026-11-20 10:09, so the audit Nov 14-15 outage with 408 TelegramCredentialError tracebacks has rotated out): TelegramCredentialError=0, telegram.error.TimedOut=456 (452 on Nov 18 + 4 on Nov 19), telegram.error.NetworkError=20, "Traceback (most recent"=700, outbound "Failed to send notification"=232 (one ~4h outage Nov 18 20:05 to Nov 19 00:xx at ~1/min, plus one on Nov 20 08:xx). athena ~/.sase/service/procs/telegram_receiver/output.log (untimestamped, whole file): TimedOut=153, NetworkError=193, Traceback=653, "Receiver poll failed"=238, "credentials unavailable; receiver retrying"=59. apollo lumberjack-telegram.log (2026-09-02 to 2026-11-20): TelegramCredentialError=0, TimedOut=0, NetworkError=0; apollo has no receiver log. AFTER INSTALL (read-only; set S to the install-date prefix, e.g. 2026-11-2; receiver log has no timestamps, so compare its counts as deltas against the totals above): for h in athena apollo; do ssh $h 'S=2026-11-2; L=~/.sase/axe/logs/lumberjack-telegram.log; R=~/.sase/service/procs/telegram_receiver/output.log; echo "== $(hostname)"; for p in TelegramCredentialError telegram.error.TimedOut "Traceback (most recent" "credentials unavailable; receiver retrying" sase_telegram.degraded:; do echo "$p: lumberjack=$(sed "s/\x1b\[[0-9;]*m//g" $L | grep -F "$p" | grep -c "^\[$S") receiver=$(grep -cF "$p" $R 2>/dev/null)"; done; cat ~/.sase/telegram/degraded_*.json 2>/dev/null; true'; done. Expect TelegramCredentialError/TimedOut traceback lines to stop growing; an outage instead shows one "sase_telegram.degraded: Telegram outbound|receiver entered <state>" line, at most one "still <state>" summary per 15 min, one "recovered from" line, and one telegram-degraded:<component>:<state> notification.

[2026-11-20T16:04:16Z · sase-1tz.3.1.7] PROPOSED FOLLOW-UP: sase-telegram check stays red on 4 pre-existing ERRORs — tests/test_formatting.py::TestBuildForkCopyText::test_tag_prompt_renders_tag_form and 3 tests/test_inbound.py::TestBeadProjectContext tests patch the removed sase.project_display_names._project_display_name_map_cached; they reproduce identically on the clean sase-telegram base (verified with git stash) and are already recorded as a PROPOSED FOLLOW-UP on sase-1tz.3.1.6 (retarget the patches at sase._project_display_cache).

[2026-11-20T16:04:21Z · sase-1tz.3.1.7] PROPOSED FOLLOW-UP: sase-telegram AGENTS.md architecture list does not mention the new src/sase_telegram/degraded.py (persisted credential/network outage states) or the 60 s bot-token negative cache in credentials.py — the list is incomplete, not false, and this epic authorizes no AGENTS.md edits; add a one-line entry.

[2026-11-20T16:04:38Z · sase-1tz.3.1.7] tg_degraded landed in sase-telegram (uncommitted working tree in the linked checkout; host finalizer commits). New src/sase_telegram/degraded.py: classify_failure maps TelegramCredentialError to credential_unavailable and TimedOut/NetworkError (incl. 5xx Bad Gateway, never BadRequest) to network_degraded; DegradedTracker persists per-component state (~/.sase/telegram/degraded_outbound.json, degraded_receiver.json: state, entered_at, last_seen, count, last_summary_at, suppressed, notice_id) under a flock. Entering logs one WARNING with no traceback and raises one SASE notice (sender telegram, dedup key telegram-degraded:<component>:<state>; a settled earlier episode gets a fresh row); repeats log at most one summary per 15 min with the suppressed count; recovery logs one INFO line with duration and count and settles the notice (+1 note, then dismissed); a state change settles the old notice and raises a new one. Outbound: send and chat-id credential failures feed the tracker (chat-id failure exits 0 with reason=credential_unavailable instead of the per-tick stderr line via _run_cleanly), success clears it, its own degraded notices are never delivered and settled receiver notices are skipped, transient attachment/media failures log one line, unexpected errors keep tracebacks. Receiver: token failure records credential_unavailable and keeps exit 75; a resolved token clears only credential_unavailable; poll TimedOut/NetworkError feed the tracker and a successful poll clears any state; transient housekeeping failures log one line without becoming a state. telegram_client retry attempts for TimedOut/NetworkError log at DEBUG. credentials.get_bot_token remembers a failed pass lookup for 60 s in ~/.sase/telegram/bot_token_unavailable.json (env var and token file still checked every call; future-dated or malformed records ignored; success clears it). Tests: tests/test_degraded.py, tests/test_receiver_degraded.py, new classes in tests/test_outbound.py and tests/test_credentials.py cover one notice and bounded log lines for 1440 credential failures, no tracebacks for transient errors, recovery logging once and settling, negative-cache expiry, exit 75 kept; conftest isolates state files and records notices. Docs: README credentials and state files, docs/outbound.md Degraded States, docs/inbound.md, docs/architecture.md. Verified: ruff, ruff format, mypy clean; sase tool run check: 876 passed plus the same 4 ERRORs that reproduce on the clean base (stale _project_display_name_map_cached patch, PROPOSED FOLLOW-UP). Before-numbers and the after-install command are in a note on this bead; summary note on sase-1tz.3.

## Dependencies

- **Depends on:** [sase-1tz.3.1.6](sase-1tz.3.1.6.md) ✓ · ⧖ 2026-11-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.3.1.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.7/README.md) | [sase-1tz.3.1.7](sase-1tz.3.1.7.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.3.1.7][1] | Need the phase scope and design file | 2 |
| read-by | [agent:sase-1tz.3.1.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.7/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.land/README.md

<!-- sase:referenced-by:end -->
