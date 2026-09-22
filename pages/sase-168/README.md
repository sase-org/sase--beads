# Bead: sase-168 — Make remote-attention notifications dismissable and unfreeze apollo's attention feed

[Bead Pages](../README.md) / sase-168

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pa](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pa.md) · **Assignee:** `sase-168.land`
**Created:** 2026-09-22 10:05:56 EDT · **Closed:** 2026-09-22 11:17:05 EDT
**Plan:** [202609/remote\_attention\_dismissal\_fix.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_attention_dismissal_fix.md)

## Description

A user dismissal of a remote-attention notification sticks for that revision; the gateway attention inventory works on hosts with more than 200 visible notifications; and on athena the fix is installed, the 8 stuck apollo rows are dismissed and stay dismissed, and a fresh sase screenshot no longer shows `?8` at the top right.

## Notes

[2026-09-22T15:17:05Z · sase-168.land] Verified: sase-168.1 (sase 54d19bee6) — reconciler preserves user read/dismissed for same revision, marks and reverses only its own auto-dismissals via REMOTE_ATTENTION_AUTO_DISMISSED_ACTION_DATA_KEY, treats has_more/next_cursor pages as incomplete; 34/34 tests pass (tests/test_dispatch_attention_inbox.py + tests/ace/tui/test_remote_lifecycle_actions.py). sase-168.2 (sase-core 19ee7a0 on origin/master) — project_attention_entries helper drops the 200 raw-row cap for the inventory, project_fleet_attention keeps its reject-201 contract, gateway pre-filters to actionable rows, with core+route tests. sase does not call the inventory binding, so no sase-core-revision.txt pin move needed. sase-168.3 — installed on athena, TUI restarted, 8 apollo rows dismissed and stayed dismissed after 120s, screenshot shows no ? chip. Integration: post-start commits (772f3f199, 529d7d325, 7c763a2e7) touch no attention/notification code; nothing to integrate. Follow-ups (each proposed by .1, .2, .3): (1) follow inventory next_cursor per host -> DISCOVERED ISSUE note on active epic sase-xe.16.11.7 (owns the attention inbox's first-page-only fetch); (2) cache-only federation reads report status ok after network failure -> DISCOVERED ISSUE note on active epic sase-xe.16.11.7.14 (honest-freshness scope); no new task beads. Caveat: apollo still needs sase update + gateway restart to serve live inventory (out of scope by plan). epic-symbols: none.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-168.1](sase-168.1.md) | Honor local dismissal in the remote-attention reconciler | ✓ closed | small | 2026-09-22 | 1 | 1 |
| [sase-168.2](sase-168.2.md) | Gateway attention inventory must not fail on busy hosts | ✓ closed | small | 2026-09-22 | 1 | 1 |
| [sase-168.3](sase-168.3.md) | Install on athena, dismiss the 8 rows, and verify | ✓ closed | small | 2026-09-22 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-168: Make remote-attention notifications dismissable and unfreeze apollo's attention feed [closed]"]
    n1["sase-168.1: Honor local dismissal in the remote-attention reconciler [closed]"]
    n2["sase-168.2: Gateway attention inventory must not fail on busy hosts [closed]"]
    n3["sase-168.3: Install on athena, dismiss the 8 rows, and verify [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n1 -.-> n3
    n2 -.-> n3
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-168.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-168.1.md) | [sase-168.1](sase-168.1.md) | 1 |
| [bbugyi200.athena.sase-168.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-168.2/README.md) | [sase-168.2](sase-168.2.md) | 1 |
| [bbugyi200.athena.sase-168.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-168.3/README.md) | [sase-168.3](sase-168.3.md) | 0 |
| [bbugyi200.athena.sase-168.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-168.land/README.md) | [sase-168](README.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@19ee7a0`](https://github.com/sase-org/sase-core/commit/19ee7a09fc0687daec0f336ae2798c96866486c1) | fix(fleet-attention): lift 200-row cap from attention inventory, pre-filter gateway rows | [sase-168.2](sase-168.2.md) | 2026-09-22 10:19:08 EDT |
| sase | [`54d19be`](https://github.com/sase-org/sase/commit/54d19bee61104cd15265ffcb0b2b89855e509a0e) | fix(dispatch): honor local dismissal in remote-attention reconciler | [sase-168.1](sase-168.1.md) | 2026-09-22 10:51:24 EDT |
| sase--plans | [`sase--plans@4a87cff`](https://github.com/sase-org/sase--plans/commit/4a87cff4aee5c8ce524217b52c069a98f688f20e) | chore(plans): mark remote\_attention\_dismissal\_fix plan done after sase-168 landed | [sase-168](README.md) | 2026-09-22 11:33:25 EDT |
