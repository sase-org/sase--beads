# Bead: sase-jo.2 — Tracked-commit provenance invariant

[Bead Pages](../README.md) / [sase-jo](README.md) / sase-jo.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.xv](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.xv/README.md) · **Assignee:** `sase-jo.2` · **Size:** medium
**Created:** 2026-08-11 06:58:28 EDT · **Closed:** 2026-08-11 08:22:29 EDT
**Plan:** [202608/stitch\_origin\_badges.md](https://github.com/sase-org/sase--plans/blob/main/202608/stitch_origin_badges.md)

## Description

invariant: stamp `SASE_TYPE=stitch` on every commit created through the tracked `sase stitch create` workflow, audit every remaining commit-creating call site so each stamps a `SASE_TYPE=` value, and add a contract test that keeps new call sites from regressing the invariant.

## Notes

[2026-08-11T12:22:11Z · sase-jo.2] PROPOSED FOLLOW-UP: vcs_amend (src/sase/vcs_provider/plugins/_git_core_ops.py) replaces HEAD message with whatever the caller supplies, with no SASE_TYPE preservation of its own — current reword/rewind/accept callers happen to round-trip the existing (tagged) message, but any future caller that builds a fresh message instead of round-tripping would silently drop the footer with no test catching it. Consider adding an assertion/helper in vcs_amend itself, or a contract check on its callers.

[2026-08-11T12:22:29Z · sase-jo.2] Added apply_tracked_commit_tags to stamp SASE_TYPE=stitch (plus runtime tags) on the create_commit dispatch branch of the tracked stitch-create workflow; audited every remaining git-commit-creating call site under src/ and tagged the untagged ones (revert, agents_sync x3, beads) via apply_auto_commit_type_tag; added tests/test_commit_type_tag_contract.py, a structural AST-scan contract test (with a substring-"commit" pre-filter, 8.6s -> 0.46s) that fails on any future untagged commit-creating call site, and re-curated the contract manifest budget from 40->41 entries (measured 24.0s serial, under the 30s hard budget) to admit it. Verified: three full 'just check' runs — first two runs' scoped-lane failures were a stale contract manifest (fixed) and two unrelated pre-existing flakes (tests/ace/tui/test_loader_cleanup_decoupling.py and tests/ace/tui/test_logs_pane.py, each confirmed passing 3/3 in isolation); third run passed clean end-to-end (all lint gates + full-suite-escalated scoped test lane, 0 failures).

## Dependencies

- **Blocks:** [sase-jo.6](sase-jo.6.md) ◐ · ⧖ 2026-08-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-jo.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-jo.2/README.md) | [sase-jo.2](sase-jo.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`050264c`](https://github.com/sase-org/sase/commit/050264c7c98f4e2efbb93efb15db10924b8e52bd) | feat(vcs): stamp SASE\_TYPE on every commit-creating call site | [sase-jo.2](sase-jo.2.md) | 2026-08-11 08:23:21 EDT |
