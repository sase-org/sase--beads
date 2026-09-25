# Bead: sase-18j.5 — Pin the core, gather triage inputs, and pass the precision backtest

[Bead Pages](../README.md) / [sase-18j](README.md) / sase-18j.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0rq](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0rq.md) · **Assignee:** `sase-18j.5` · **Size:** large
**Created:** 2026-09-24 19:07:08 EDT
**Plan:** [202609/tool\_e3\_failure\_triage.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_e3_failure_triage.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | file:explicit:88153ff59741b262232d81de | attached via sase artifact create --bead |

<!-- sase:links:end -->

## Description

bindings-and-backtest: move the core pin and add adapters and validators for every new binding, build the bounded input gatherers, write tools/tool_triage_backtest, and pass the at-least-95% hand-audited KNOWN precision gate on athena before any label is stored.

## Notes

[2026-09-25T02:43:39Z · sase-18j.5--3] PROPOSED FOLLOW-UP: Repair the precision backtest's KNOWN-on-added/untracked safeguard. The clean-witness replay (--sample 60 --min-witnesses 2 --touched-requires-clean-witness) produced 313 KNOWN items, 139 on added/untracked paths, and 0 KNOWN-but-touched; DoD-5 requires at least 95% hand-audited KNOWN precision and zero added-file KNOWN. Preserve and use file:explicit:88153ff59741b262232d81de (report) and file:explicit:959535d805b6acd19d053edb (audit worksheet), then rerun the backtest before changing final classifier constants or storing any labels.

## References

- file:explicit:88153ff59741b262232d81de
- file:explicit:959535d805b6acd19d053edb

## Dependencies

- **Depends on:** [sase-18j.1](sase-18j.1.md) ✓ · ⧖ 2026-09-24
- **Depends on:** [sase-18j.3](sase-18j.3.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-18j.6](sase-18j.6.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18j.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-18j.5.md) | [sase-18j.5](sase-18j.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`cdcbcdd`](https://github.com/sase-org/sase/commit/cdcbcdd9d3988359f1b4fc77d6d0454632a4e760) | feat(tool): add triage input backtest | [sase-18j.5](sase-18j.5.md) | 2026-09-24 22:45:15 EDT |
