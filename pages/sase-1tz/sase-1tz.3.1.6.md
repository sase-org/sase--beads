# Bead: sase-1tz.3.1.6 — Fall back to plain text only on entity-parse errors and retry per chunk

[Bead Pages](../README.md) / [sase-1tz.3.1](sase-1tz.3.1.md) / sase-1tz.3.1.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.3.md) · **Assignee:** `sase-1tz.3.1.6` · **Size:** medium
**Created:** 2026-11-20 09:19:06 EST · **Closed:** 2026-11-20 09:56:02 EST
**Plan:** [202611/defects\_wire\_swap\_telegram\_bundles\_triage.md](https://github.com/sase-org/sase--plans/blob/main/202611/defects_wire_swap_telegram_bundles_triage.md)

## Description

tg_transport: in sase-telegram, plain-text fallback fires only for an entity-parse BadRequest. Timeouts, network errors, rate limits, and credential errors reach the retry wrapper unchanged. Retries wrap each chunk, so delivered chunks are never resent, and the outbound job resumes a partly delivered notification at its first undelivered chunk.

## Notes

[2026-11-20T14:55:40Z · sase-1tz.3.1.6] PROPOSED FOLLOW-UP: sase-telegram tests patch a removed sase symbol — tests/test_formatting.py:169 and tests/test_inbound.py:2878 patch sase.project_display_names._project_display_name_map_cached, which sase commit 19f497f82d (Nov 6, split project_display_names into _project_display_* private modules) removed from the facade. 4 tests (TestBuildForkCopyText::test_tag_prompt_renders_tag_form, TestBeadProjectContext x3) ERROR identically on the clean sase-telegram base against current sase master, so `sase tool run check` stays red; retarget the patches at sase._project_display_cache. No existing bead found by search.

[2026-11-20T14:55:47Z · sase-1tz.3.1.6] COORDINATION: tg_degraded (sase-1tz.3.1.7) edits the same outbound except-block in scripts/sase_tg_outbound.py. send_message failures keep their original exception type (TelegramCredentialError, TimedOut, NetworkError, etc. are never wrapped); the delivered-chunk count rides on the exception and is read with telegram_client.delivered_chunks(exc), so type-based state classification works unchanged.

[2026-11-20T14:56:02Z · sase-1tz.3.1.6] tg_transport landed in sase-telegram (uncommitted working tree in the linked checkout; host finalizer commits). telegram_client: plain-text fallback fires only for an entity-parse BadRequest (can't parse entities / message text); _get_bot() is outside the guarded block; TimedOut, NetworkError/Bad Gateway, RetryAfter, Forbidden, InvalidToken, TelegramCredentialError and non-parse BadRequests propagate unchanged. The fallback sticks across retry attempts, and edit_message_text follows the same rule (not-modified, including after a fallback, returns True). send_message retries each chunk on its own (4 attempts max per chunk, reply_markup only on the last chunk), accepts start_chunk, and a failure keeps its exception type with the delivered count attached (delivered_chunks(exc) plus a PEP 678 note). Outbound stores that count in ~/.sase/telegram/partial_delivery.json, keyed by notification id, activity cursor and a text sha256. The next tick resumes at the first undelivered chunk, starts over if the text changed, and clears the record on success. Tests in tests/test_telegram_client.py and tests/test_outbound.py cover parse fallback, no fallback on non-parse BadRequest, TimedOut retry without fallback, exact sends per failing chunk ([c0]+[c1]*4), and resume on the next tick ([c1,c2], chunk 0 never resent). conftest isolates the record file. Docs updated: README state files, docs/outbound.md, docs/architecture.md. Verified: ruff, ruff format, mypy clean; sase tool run check: 817 passed, plus 4 ERRORs that reproduce identically on the clean base (stale _project_display_name_map_cached patch, recorded as PROPOSED FOLLOW-UP).

## Dependencies

- **Blocks:** [sase-1tz.3.1.7](sase-1tz.3.1.7.md) ✓ · ⧖ 2026-11-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.3.1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.6/README.md) | [sase-1tz.3.1.6](sase-1tz.3.1.6.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.3.1.6][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1tz.3.1.7][2] | Need tg_transport notes as dependency | 1 |
| read-by | [agent:sase-1tz.3.1.land][3] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.6/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.7/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.land/README.md

<!-- sase:referenced-by:end -->
