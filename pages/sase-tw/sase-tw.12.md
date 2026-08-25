# Bead: sase-tw.12 — ACE stops flattening the relation type

[Bead Pages](../README.md) / [sase-tw](README.md) / sase-tw.12

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-tj.land.w3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-tj.land.w3.md) · **Assignee:** `sase-tw.12` · **Size:** medium
**Created:** 2026-08-25 15:34:43 EDT · **Closed:** 2026-08-25 17:32:23 EDT
**Plan:** [202608/artifact\_link\_durability\_and\_derivation.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_link_durability_and_derivation.md)

## Description

ace-fidelity: carry relation slug, directional label, description, origin, and use count from the aggregate row into ACE's relation rail instead of collapsing every edge to `links`/`linked_by`, and add a typed link action with a required reason.

## Notes

[2026-08-25T20:11:26Z · 0ds] INTEGRATION: this phase updates relation snapshot tests and the relation rail's
rendering under src/sase/ace/tui/widgets/artifacts/. Two other efforts touch the same
goldens in the same window: sase-tj.10.3 rebaselines every artifacts_* PNG golden and
adds six new Agent-pane snapshots, and sase-tt.3 of epic sase-tt may add an "index still
building" affordance to the Agent pane. Rebaseline against master after those land, and
hold this phase's own rule — updated deliberately, not force-accepted. That rule is the
only thing keeping three concurrent rebaselines from silently dropping each other's
changes.

One seam between the two epics: sase-tt.3 lists "relation-panel targets" among the
behaviors that must not regress when the Agent pane paints from a bounded head slice. If
this phase changes what a relation edge carries, the bounded-pass answer for relation
targets belongs to both epics. Verify it after both land rather than assuming either
side covered it.

[2026-08-25T21:31:50Z · sase-tw.12] PROPOSED FOLLOW-UP: agent-name registry stale-proof tests fail outside this phase -- just check full-suite selection reports tests/test_agent_name_registry_rebuild.py::test_stale_proof_memo_invalidated_by_mutation and tests/test_agent_names_auto_name.py::TestGetNextAutoName::test_dotted_suffix_reserves_prefix, and both fail in isolation on the current tree.

[2026-08-25T21:32:23Z · sase-tw.12] Verified focused artifact-link relation/action tests, git diff --check, and just check static gates; just check full-suite selection passed 37046 tests with 2 unrelated agent-name registry failures recorded as a PROPOSED FOLLOW-UP on this phase.

## Dependencies

- **Blocks:** [sase-tw.13](sase-tw.13.md) ◐ · ⧖ 2026-08-25
- **Depends on:** [sase-tw.5](sase-tw.5.md) ✓ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-tw.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.12/README.md) | [sase-tw.12](sase-tw.12.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2730cfe`](https://github.com/sase-org/sase/commit/2730cfedca0d162646a69d9d4b1e262ef8cc6a1b) | feat(artifact): preserve typed link relations in ACE | [sase-tw.12](sase-tw.12.md) | 2026-08-25 18:24:19 EDT |
