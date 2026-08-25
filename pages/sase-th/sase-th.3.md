# Bead: sase-th.3 — Re-review the split agent-chat marker-path sites

[Bead Pages](../README.md) / [sase-th](README.md) / sase-th.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0d8](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0d8.md) · **Assignee:** `sase-th.3` · **Size:** small
**Created:** 2026-08-25 07:32:01 EDT · **Closed:** 2026-08-25 07:48:45 EDT
**Plan:** [202608/repair\_red\_master\_ci.md](https://github.com/sase-org/sase--plans/blob/main/202608/repair_red_master_ci.md)

## Description

marker-audit: add the six agent-chat resolver call sites that the module split moved out of the reviewed marker-path allowlist, each with a real lifecycle or exemption rationale.

## Notes

[2026-08-25T11:47:00Z · sase-th.3] PROPOSED FOLLOW-UP: just check is blocked by unrelated Python formatting drift — ruff format --check reports src/sase/sdd/_store_link.py would be reformatted at line 291; this phase did not touch that file.

[2026-08-25T11:48:45Z · sase-th.3] Added six reviewed read-only marker-path passing exemptions for the split agent-chat resolver call sites. Verified uv run pytest tests/test_agent_artifact_marker_path_passing_audit.py -q and ruff format/check on that test file. Ran just install successfully; just check was attempted but stopped on unrelated ruff format drift in src/sase/sdd/_store_link.py:291, recorded as a PROPOSED FOLLOW-UP on this phase.

## Dependencies

- **Blocks:** [sase-th.7](sase-th.7.md) ◐ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-th.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-th.3/README.md) | [sase-th.3](sase-th.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`18ce1d6`](https://github.com/sase-org/sase/commit/18ce1d6e5056a25b75cde00fe3841b21be88ea8e) | test(agents): review split chat marker paths | [sase-th.3](sase-th.3.md) | 2026-08-25 07:49:59 EDT |
