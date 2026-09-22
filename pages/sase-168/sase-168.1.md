# Bead: sase-168.1 — Honor local dismissal in the remote-attention reconciler

[Bead Pages](../README.md) / [sase-168](README.md) / sase-168.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pa](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pa.md) · **Assignee:** `sase-168.1` · **Size:** small
**Created:** 2026-09-22 10:05:57 EDT · **Closed:** 2026-09-22 10:49:11 EDT
**Plan:** [202609/remote\_attention\_dismissal\_fix.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_attention_dismissal_fix.md)

## Description

inbox-dismissal: stop reconcile_remote_attention_inbox from un-dismissing same-revision rows, mark and reverse only its own auto-dismissals, and treat has_more pages as incomplete, with regression tests.

## Notes

[2026-09-22T14:48:14Z · sase-168.1--1] PROPOSED FOLLOW-UP: follow inventory next_cursor per host so hosts with 100+ pending requests are fully mirrored

[2026-09-22T14:48:43Z · sase-168.1--1] PROPOSED FOLLOW-UP: after a failed network read, cache-only federation reads should carry stale status/error instead of status ok

[2026-09-22T14:49:11Z · sase-168.1--1] 12/12 focused pytest pass, ruff check/format and mypy clean on both touched files, no epic-symbols left; just check's only failure is pre-existing unrelated _lint-pyscripts Rule 2 (tools/ vs tests/ace/tui/visual+tools), untouched by this phase

## Dependencies

- **Blocks:** [sase-168.3](sase-168.3.md) ◐ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-168.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-168.1.md) | [sase-168.1](sase-168.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`54d19be`](https://github.com/sase-org/sase/commit/54d19bee61104cd15265ffcb0b2b89855e509a0e) | fix(dispatch): honor local dismissal in remote-attention reconciler | [sase-168.1](sase-168.1.md) | 2026-09-22 10:51:24 EDT |
