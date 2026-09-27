# Bead: sase-1aq.10.7.5.1 — Prove healthy-beside-hung host and real-locator fencing

[Bead Pages](../README.md) / [sase-1aq.10.7.5](sase-1aq.10.7.5.md) / sase-1aq.10.7.5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1aq.10.7.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1aq.10.7.land.md) · **Assignee:** `sase-1aq.10.7.5.1` · **Size:** medium
**Created:** 2026-09-26 21:57:09 EDT · **Closed:** 2026-09-26 22:36:55 EDT
**Plan:** [202609/1aq\_close\_original\_gates.md](https://github.com/sase-org/sase--plans/blob/main/202609/1aq_close_original_gates.md)

## Description

fencing_proof: finish sase-xe.16.11.3 in sase-core (TLS-honoring RemoteHost, successful healthy host beside a hung host, captured-locator rejection) and close it normally.

## Notes

[2026-09-27T02:36:31Z · sase-1aq.10.7.5.1--1] PROPOSED FOLLOW-UP: just check mypy red on clean base tree (unrelated to fencing_proof): _tree.py:622 prefix_key no-redef + :623/:629 GroupKey arg-type, _agent_display_hint_sections.py:74 LEGACY_NAMED_PROC_SECTION_ID name-defined (leftover of named_proc rename d4c7b5ca9a). sase tree clean so failure reproduces identically on base; plan Known-clean-base-reds attributes rename/proc reds to sase-1ab/sase-th, not dispatch work.

[2026-09-27T02:36:55Z · sase-1aq.10.7.5.1--1] fencing_proof done: sase-xe.16.11.3 closed normally 02:18:23Z with TLS-honoring RemoteHost, real pinned-CA HTTPS healthy-beside-hung proof, captured-locator 409 rejection, cargo 221/221 green (note #5 there). just check: all stages green except 4 mypy errors that reproduce on the clean sase tree (tree clean, unrelated TUI files) — recorded as PROPOSED FOLLOW-UP per clean-base-red rule. No epic-symbol leftovers.

## Dependencies

- **Blocks:** [sase-1aq.10.7.5.3](sase-1aq.10.7.5.3.md) ◐ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1aq.10.7.5.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1aq.10.7.5.1.md) | [sase-1aq.10.7.5.1](sase-1aq.10.7.5.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@37a4dd8`](https://github.com/sase-org/sase-core/commit/37a4dd822e4a34ca4d57098ef107cc3b1cd44bad) | test(sase-gateway): prove healthy-beside-hung host and captured-locator fencing | [sase-1aq.10.7.5.1](sase-1aq.10.7.5.1.md) | 2026-09-26 22:38:33 EDT |
