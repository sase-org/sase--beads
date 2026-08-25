# Bead: sase-tw — Artifact links that survive, derive themselves, and pay for the turn

[Bead Pages](../README.md) / sase-tw

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-tj.land.w3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-tj.land.w3.md) · **Assignee:** `sase-tw.land`
**Created:** 2026-08-25 15:34:34 EDT
**Plan:** [202608/artifact\_link\_durability\_and\_derivation.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_link_durability_and_derivation.md)

## Description

The artifact-link graph stops losing durable rows, grows to ~1,600 edges derived from facts SASE already owns without adding one token to the average agent's context, and becomes load-bearing: every audited read shows its neighborhood, ACE carries the relation type, and the Artifacts Agent pane filters on `relation:`, `linked:`, and `artifact:`.

## Notes

[2026-08-25T20:10:46Z · 0ds] INTEGRATION: the plan's "Sequencing note: the Agent pane is still landing" is
incomplete. It names sase-tj.10 only. A second in-flight epic, sase-tt ("Make Artifacts
sub-tab queries fast, starting with the Agent pane",
plan:202608/artifacts_query_performance.md, created 2026-08-25 14:59, 35 minutes before
this epic), rewrites the Agent pane harder than sase-tj.10 does:

- sase-tt.3 (agent-paint) gives load_agents_snapshot a limit parameter and
  AgentsSnapshot a complete flag, paints from a bounded head slice, and moves the
  full-corpus query-index build into a background extension worker.
- sase-tt.5 (entry-projection) rewrites agent_catalog_query_entry and
  compile_artifact_query_index's marshalling, and lands a golden test on the
  agent-catalog wire dict.
- sase-tt.4 (core-corpus) changes how sase-core consumes that wire, and releases
  sase-core.

Read that sequencing note as covering sase-tt as well. sase-tw.13 (agent-pane-filters)
must not start until sase-tj.10 and epic sase-tt have both landed on master; its own
bead carries what changes as a result. sase-tw.3 and sase-tw.5 are not blocked by
sase-tt, but they share sase-core releases with sase-tt.4 — see the note on sase-tw.3.

Nothing else in this epic conflicts with sase-tt. The durability, derivation, citation,
read-payoff, and migration phases touch disjoint code.

[2026-08-25T20:48:03Z · 0dt] DISCOVERED ISSUE: just lint (symvision, _lint-symvision) fails on master at commit 1282c7a8c (phase sase-tw.5, 'feat(artifact-cli): add artifact link relation subcommand'): handle_link_relation_list and handle_link_relation_show in src/sase/artifact_cli/link_relations.py are reported as unused public functions/classes. Found while running just lint for an unrelated prompt-panel Ctrl+J/Ctrl+K change; confirmed pre-existing and unrelated to that change by stashing it and re-running symvision directly against a clean master tree (same failure). Likely these two CLI handlers need to be wired into a subcommand registry/dispatcher that sase-tw.5 did not finish connecting, or made private if they are only meant to be called from within link_relations.py.

[2026-08-25T21:09:54Z · research.14.cdx] DISCOVERED ISSUE CORROBORATION: While verifying the unrelated direct-agent-CLI compatibility research report, just check independently failed deterministically at lint (symvision) on HEAD 446e9a43c359fc8ed943f29ab4eb24c91601dd21. The only reported symbols were handle_link_relation_list and handle_link_relation_show in src/sase/artifact_cli/link_relations.py. All preceding gates passed (Python/Markdown formatting, keep-sorted, Ruff, mypy, feature flags, pyscripts, test waits, changelog, and patch/stitch terminology). This is the same phase-caused failure already recorded in note #2; no standalone task was created.

[2026-08-25T22:10:50Z · sase-tt.land] DISCOVERED ISSUE (sase-tt.land, master f56cf4333): phase sase-tw.5's commit 1282c7a8c ('feat(artifact-cli): add artifact link relation subcommand') added the 'sase artifact link relation' subparser and its 'list' child without updating two derived expectations, leaving three nodes red on clean master:

  - tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift
  - tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot
  - tests/main/test_artifact_handler.py::test_public_long_options_are_alphabetical_and_have_short_aliases

REPRODUCTION: .venv/bin/python -m pytest -q -p no:randomly tests/completion/test_snapshot.py tests/main/test_artifact_handler.py -> 3 failed, deterministic in isolation (not a parallel-lane flake). Diffing current_structural_view() against tests/completion/snapshots/cli_spec.json shows the whole delta is the new .root.subcommands[artifact].subcommands[link].subcommands[relation] subtree; nothing else drifted. test_artifact_handler asserts list(link_subcommands.choices) == ['add','list','migrate-notes','rm'], which 'relation' now breaks.

FIX: run 'just sync-completion-spec' and add 'relation' to that assertion. Routed to this epic rather than a new task bead because sase-tw owns the causing commit and phases sase-tw.13/sase-tw.14 are still in flight on the same CLI surface; the completion-snapshot half is also corroborated on task sase-pr (+1 by sase-tt.land). Found while landing epic sase-tt and originally recorded as a PROPOSED FOLLOW-UP on bead sase-tt.8; verified NOT caused by sase-tt.

[2026-08-25T22:42:11Z · 0dv] DISCOVERED ISSUE CORROBORATION: During bead_show_paging_and_multi_id verification on 2026-08-25, just check escalated to the governed full pytest lane and failed tests/main/test_artifact_handler.py::test_public_long_options_are_alphabetical_and_have_short_aliases. A focused rerun reproduced deterministically: the artifact link subcommands now include relation, but the test still expects ['add', 'list', 'migrate-notes', 'rm']. The local diff is bead show paging/multi-ID/parser/docs/tests work and does not touch artifact link relation parsing. This corroborates note #4 on this active epic rather than creating a standalone task bead.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-tw.1](sase-tw.1.md) | A rebuild may delete only what it can prove was deleted | ✓ closed | medium | 2026-08-25 | 1 | 1 |
| [sase-tw.10](sase-tw.10.md) | Finish the \`links:\` frontmatter inlet as an authoring path | ✓ closed | medium | 2026-08-25 | 1 | 2 |
| [sase-tw.11](sase-tw.11.md) | Make every audited read a discovery moment | ✓ closed | medium | 2026-08-25 | 1 | 1 |
| [sase-tw.12](sase-tw.12.md) | ACE stops flattening the relation type | ✓ closed | medium | 2026-08-25 | 1 | 1 |
| [sase-tw.13](sase-tw.13.md) | \`relation:\`, \`linked:\`, and \`artifact:\` on the Agent pane | ✓ closed | medium | 2026-08-25 | 1 | 1 |
| [sase-tw.14](sase-tw.14.md) | The judgment tier, the flag removal, and the two workflow lines | ◐ in_progress | medium | 2026-08-25 | 1 | 0 |
| [sase-tw.2](sase-tw.2.md) | Audited reads become durable and publish with the agent's commits | ✓ closed | medium | 2026-08-25 | 1 | 1 |
| [sase-tw.3](sase-tw.3.md) | A bead in either endpoint position gets its event | ✓ closed | medium | 2026-08-25 | 1 | 2 |
| [sase-tw.4](sase-tw.4.md) | Links follow renames instead of dangling | ✓ closed | medium | 2026-08-25 | 1 | 1 |
| [sase-tw.5](sase-tw.5.md) | Relation semantics, \`derived\` projection class, and a way to read them | ✓ closed | medium | 2026-08-25 | 1 | 2 |
| [sase-tw.6](sase-tw.6.md) | One derivation module behind one flag | ✓ closed | medium | 2026-08-25 | 1 | 1 |
| [sase-tw.7](sase-tw.7.md) | Derive at creation, on sidecar commit, and in the hourly sweep | ◐ in_progress | medium | 2026-08-25 | 1 | 1 |
| [sase-tw.8](sase-tw.8.md) | The citation channel stops starving | ◐ in_progress | medium | 2026-08-25 | 1 | 0 |
| [sase-tw.9](sase-tw.9.md) | Run the RELATED: note backfill | ✓ closed | small | 2026-08-25 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-tw: Artifact links that survive, derive themselves, and pay for the turn [in_progress]"]
    n1["sase-tw.1: A rebuild may delete only what it can prove was deleted [closed]"]
    n2["sase-tw.10: Finish the `links:` frontmatter inlet as an authoring path [closed]"]
    n3["sase-tw.11: Make every audited read a discovery moment [closed]"]
    n4["sase-tw.12: ACE stops flattening the relation type [closed]"]
    n5["sase-tw.13: `relation:`, `linked:`, and `artifact:` on the Agent pane [closed]"]
    n6["sase-tw.14: The judgment tier, the flag removal, and the two workflow lines [in_progress]"]
    n7["sase-tw.2: Audited reads become durable and publish with the agent's commits [closed]"]
    n8["sase-tw.3: A bead in either endpoint position gets its event [closed]"]
    n9["sase-tw.4: Links follow renames instead of dangling [closed]"]
    n10["sase-tw.5: Relation semantics, `derived` projection class, and a way to read them [closed]"]
    n11["sase-tw.6: One derivation module behind one flag [closed]"]
    n12["sase-tw.7: Derive at creation, on sidecar commit, and in the hourly sweep [in_progress]"]
    n13["sase-tw.8: The citation channel stops starving [in_progress]"]
    n14["sase-tw.9: Run the RELATED: note backfill [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n0 --> n9
    n0 --> n10
    n0 --> n11
    n0 --> n12
    n0 --> n13
    n0 --> n14
    n1 -.-> n3
    n1 -.-> n5
    n1 -.-> n7
    n1 -.-> n8
    n1 -.-> n9
    n2 -.-> n6
    n3 -.-> n6
    n4 -.-> n5
    n5 -.-> n6
    n7 -.-> n12
    n8 -.-> n11
    n8 -.-> n14
    n9 -.-> n12
    n10 -.-> n3
    n10 -.-> n4
    n10 -.-> n11
    n11 -.-> n2
    n11 -.-> n12
    n12 -.-> n13
    n13 -.-> n6
    n14 -.-> n6
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-tw.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.1/README.md) | [sase-tw.1](sase-tw.1.md) | 1 |
| [bbugyi200.athena.sase-tw.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.10/README.md) | [sase-tw.10](sase-tw.10.md) | 2 |
| [bbugyi200.athena.sase-tw.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.11/README.md) | [sase-tw.11](sase-tw.11.md) | 1 |
| [bbugyi200.athena.sase-tw.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.12/README.md) | [sase-tw.12](sase-tw.12.md) | 1 |
| [bbugyi200.athena.sase-tw.13](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.13/README.md) | [sase-tw.13](sase-tw.13.md) | 1 |
| [bbugyi200.athena.sase-tw.14](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.14/README.md) | [sase-tw.14](sase-tw.14.md) | 0 |
| [bbugyi200.athena.sase-tw.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.2/README.md) | [sase-tw.2](sase-tw.2.md) | 1 |
| [bbugyi200.athena.sase-tw.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.3/README.md) | [sase-tw.3](sase-tw.3.md) | 2 |
| [bbugyi200.athena.sase-tw.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.4/README.md) | [sase-tw.4](sase-tw.4.md) | 1 |
| [bbugyi200.athena.sase-tw.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.5/README.md) | [sase-tw.5](sase-tw.5.md) | 2 |
| [bbugyi200.athena.sase-tw.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.6/README.md) | [sase-tw.6](sase-tw.6.md) | 1 |
| [bbugyi200.athena.sase-tw.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.7/README.md) | [sase-tw.7](sase-tw.7.md) | 1 |
| [bbugyi200.athena.sase-tw.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.8/README.md) | [sase-tw.8](sase-tw.8.md) | 0 |
| [bbugyi200.athena.sase-tw.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.9/README.md) | [sase-tw.9](sase-tw.9.md) | 1 |
| [bbugyi200.athena.sase-tw.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.land/README.md) | [sase-tw](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e46adb7`](https://github.com/sase-org/sase/commit/e46adb77f14965dd49d680f35618e1b92b36a1cf) | fix(artifact-links): preserve aggregate rows across workspace rebuilds | [sase-tw.1](sase-tw.1.md) | 2026-08-25 16:02:32 EDT |
| sase | [`1282c7a`](https://github.com/sase-org/sase/commit/1282c7a8c7ff02b328b87bdbe33e28616f9e2020) | feat(artifact-cli): add artifact link relation subcommand | [sase-tw.5](sase-tw.5.md) | 2026-08-25 16:04:13 EDT |
| sase-core | [`sase-core@498077f`](https://github.com/sase-org/sase-core/commit/498077f19fdf4fed951b4b4f62369483a67e0d42) | feat(artifact-link): add relation module for link relation queries | [sase-tw.5](sase-tw.5.md) | 2026-08-25 16:06:33 EDT |
| sase | [`b2a0c68`](https://github.com/sase-org/sase/commit/b2a0c68a3ff0e497b007f6455e225fb80ccdb6fd) | feat(artifact-refs): expand artifact link neighborhoods in prompt rendering | [sase-tw.11](sase-tw.11.md) | 2026-08-25 16:47:48 EDT |
| sase | [`5d36fef`](https://github.com/sase-org/sase/commit/5d36fef263c6f44f7421487056ed5a12db6cc0d3) | feat(artifacts): add durable read-link outbox | [sase-tw.2](sase-tw.2.md) | 2026-08-25 17:14:12 EDT |
| sase | [`79e51b5`](https://github.com/sase-org/sase/commit/79e51b564ec987540a8a9954603fbd0a5ca2a5ec) | feat(bead-links): thread link direction and uses count through Python bead link facade | [sase-tw.3](sase-tw.3.md) | 2026-08-25 17:17:10 EDT |
| sase-core | [`sase-core@4b1f2d6`](https://github.com/sase-org/sase-core/commit/4b1f2d64a3ed2769160893efdc201ff14a7c9319) | feat(bead-links): track link direction and uses count in bead-owned link events | [sase-tw.3](sase-tw.3.md) | 2026-08-25 17:19:56 EDT |
| sase | [`2730cfe`](https://github.com/sase-org/sase/commit/2730cfedca0d162646a69d9d4b1e262ef8cc6a1b) | feat(artifact): preserve typed link relations in ACE | [sase-tw.12](sase-tw.12.md) | 2026-08-25 18:24:19 EDT |
| sase | [`7015c79`](https://github.com/sase-org/sase/commit/7015c7938d984037447ed7de29ff952b5aab0650) | feat(artifact-links): add Textual-free derivation module behind a beta flag | [sase-tw.6](sase-tw.6.md) | 2026-08-25 18:28:07 EDT |
| sase | [`012a66a`](https://github.com/sase-org/sase/commit/012a66a659853bae9bd27e0c47b0f75178794a80) | fix(artifact-links): make related note migration safe | [sase-tw.9](sase-tw.9.md) | 2026-08-25 18:30:46 EDT |
| sase | [`678988d`](https://github.com/sase-org/sase/commit/678988da73439c5c552fcf26a4007f6fcd6a27f6) | fix(artifact-links): follow sidecar renames | [sase-tw.4](sase-tw.4.md) | 2026-08-25 18:33:35 EDT |
| sase | [`ad2032c`](https://github.com/sase-org/sase/commit/ad2032c878bc1ee62007a1edf41efc7140a03592) | feat(agent-catalog): filter agents by artifact link facets | [sase-tw.13](sase-tw.13.md) | 2026-08-25 19:21:47 EDT |
| sase | [`b250011`](https://github.com/sase-org/sase/commit/b25001124a8bf49f2f0011cecdb417350a720436) | feat(artifact-links): consume plan links frontmatter | [sase-tw.10](sase-tw.10.md) | 2026-08-25 19:22:22 EDT |
| sase-core | [`sase-core@2664e20`](https://github.com/sase-org/sase-core/commit/2664e20e94979e81ec729f620e500f8fea07a9cb) | feat(plan): allow transient links frontmatter | [sase-tw.10](sase-tw.10.md) | 2026-08-25 19:23:13 EDT |
| sase | [`9606947`](https://github.com/sase-org/sase/commit/960694738960861c480229edcbd7087767d6f827) | feat(artifact-links): derive links from commits and backfill existing artifacts | [sase-tw.7](sase-tw.7.md) | 2026-08-25 19:33:07 EDT |
