# Bead: sase-ix.1 — Observation-window freshness rule in the bead core

[Bead Pages](../README.md) / [sase-ix](README.md) / sase-ix.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.x9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.x9/README.md) · **Assignee:** `sase-ix.1` · **Size:** medium
**Created:** 2026-08-10 10:50:00 EDT · **Closed:** 2026-08-10 11:10:33 EDT
**Plan:** [202608/plus\_one\_post\_close\_reopen\_race.md](https://github.com/sase-org/sase--plans/blob/main/202608/plus_one_post_close_reopen_race.md)

## Description

core: carry each +1 reporter's observation-window start on the evidence wire, and reopen a closed task only when that window starts after the close, in both the mutation path and the event reducer.

## Notes

[2026-08-10T15:08:42Z · sase-ix.1] PROPOSED FOLLOW-UP: reconcile the sase-core version-bump handoff — the epic plan asks phase workers to bump the core version, but the linked sase-core AGENTS.md forbids manual Cargo version edits during normal feature work and delegates versions to release-plz/manual-version approval.

[2026-08-10T15:10:33Z · sase-ix.1] Implemented observed_since on +1 evidence, timestamp-aware closed-task reopen withholding, assignee clearing on real +1 reopens, reducer parity, and optional PyO3 binding parameter. Verified with cargo test -p sase_core and cargo test -p sase_core_py.

[2026-08-10T15:12:44Z · sase-ix.1] Verified cargo test -p sase_core and cargo test -p sase_core_py passed after implementing timestamp-aware +1 reopen handling and PyO3 binding support.

## Dependencies

- **Blocks:** [sase-ix.2](sase-ix.2.md) ✓ · ⧖ 2026-08-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ix.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ix.1/README.md) | [sase-ix.1](sase-ix.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@d1a19d5`](https://github.com/sase-org/sase-core/commit/d1a19d566a6606aac78b961bf7008003e9b8f25f) | fix(bead): avoid stale plus-one reopens after close | [sase-ix.1](sase-ix.1.md) | 2026-08-10 11:25:04 EDT |
