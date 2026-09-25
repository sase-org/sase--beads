# Bead: sase-198 — Allow zero-load agents with %queue(weight=0)

[Bead Pages](../README.md) / sase-198

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.1n](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.1n.md) · **Assignee:** `sase-198.land`
**Created:** 2026-09-25 09:48:59 EDT · **Closed:** 2026-09-25 13:44:38 EDT
**Plan:** [202609/queue\_zero\_weight.md](https://github.com/sase-org/sase--plans/blob/main/202609/queue_zero_weight.md)

## Description

A user can author `%queue(weight=0)` or `%q(w=0)` to launch a sase agent that adds no weighted load to runner capacity. The directive round-trips through every re-authoring path, the agent and its user-authored lineage run at weight 0 end to end, and the epic-launch monitor's host-set zero weight still never gives its successors a free ride.

## Notes

[2026-09-25T17:44:38Z · sase-198.land] Verified all three closed phases against plan and source: Rust c31b8cf accepts, normalizes and formats authored zero, preserves capacity positivity, zero drain and queue admission; Python 4e18680d3d preserves explicit zero through validators, records, lineage/monitor/gate successors and w0 display; 0607f7a083 pins c31b8cf and covers directive extraction/editing/typed dispatch plus docs. Reviewed post-start sase commits and later core f55c63b multiplier change; no conflicting or missing integration found. Focused Rust queue-directive tests passed (24); after refreshing this workspace's stale Rust extension, focused Python tests passed (142). sase bead epic-symbols found no entries. FOLLOW-UP: sase-198.3 note #1 prompt-archive validation failure is pre-existing, unrelated, duplicates ready task sase-17u (+1 recorded), and is within active recovery epic sase-196.6 (DISCOVERED ISSUE noted); no new task. Phase .3's generated-skill sync warning is unrelated to these changes: no skill template changed, and its init skills check passed, so no deploy is part of this epic.

[2026-09-25T17:45:49Z · sase-198.land] POST-CLOSE DRIFT RECHECK: linked sase-core fast-forwarded to 96e42d9 (sase-19f.2, multiplier admission) during post-close Symvision setup. Reviewed its queue_directive normalization, waiter admission, records, and tests: authored zero weight continues through the multiplier branch and existing zero-drain logic; no integration change needed for sase-198. The multiplier epic sase-19f remains responsible for its own additional coverage.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-198.1](sase-198.1.md) | Rust queue contract accepts authored zero weight | ✓ closed | medium | 2026-09-25 | 1 | 1 |
| [sase-198.2](sase-198.2.md) | Python runtime honors explicit zero weight | ✓ closed | medium | 2026-09-25 | 1 | 1 |
| [sase-198.3](sase-198.3.md) | Core pin bump, end-to-end directive tests, and docs | ✓ closed | small | 2026-09-25 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-198: Allow zero-load agents with %queue(weight=0) [closed]"]
    n1["sase-198.1: Rust queue contract accepts authored zero weight [closed]"]
    n2["sase-198.2: Python runtime honors explicit zero weight [closed]"]
    n3["sase-198.3: Core pin bump, end-to-end directive tests, and docs [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n1 -.-> n3
    n2 -.-> n3
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-198.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-198.1.md) | [sase-198.1](sase-198.1.md) | 0 |
| [bbugyi200.apollo.sase-198.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-198.2.md) | [sase-198.2](sase-198.2.md) | 0 |
| [bbugyi200.apollo.sase-198.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-198.3.md) | [sase-198.3](sase-198.3.md) | 1 |
| [bbugyi200.apollo.sase-198.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-198.land/README.md) | [sase-198](README.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@c31b8cf`](https://github.com/sase-org/sase-core/commit/c31b8cf4bad8ea8c5b058a959bb69270ee2d5b30) | feat: Rust queue contract accepts authored zero weight (sase-198.1) | [sase-198.1](sase-198.1.md) | 2026-09-25 12:19:36 EDT |
| sase | [`4e18680`](https://github.com/sase-org/sase/commit/4e18680d3d98c3d82cef1b026edd9bf9b3590bf9) | feat: Python runtime honors explicit zero weight (sase-198.2) | [sase-198.2](sase-198.2.md) | 2026-09-25 12:20:11 EDT |
| sase | [`0607f7a`](https://github.com/sase-org/sase/commit/0607f7a083d80a96d3b1e9e0b5d6174417a6ce4e) | feat(queue): allow zero-load agents with %queue(weight=0) (sase-198.3) | [sase-198.3](sase-198.3.md) | 2026-09-25 13:12:21 EDT |
| sase--plans | [`sase--plans@35018ba`](https://github.com/sase-org/sase--plans/commit/35018ba8f841927e3d18541af40555856f40a17f) | docs(plan): mark zero-weight queue epic done | [sase-198](README.md) | 2026-09-25 14:08:33 EDT |
