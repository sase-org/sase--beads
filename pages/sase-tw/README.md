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

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-tw.1](sase-tw.1.md) | A rebuild may delete only what it can prove was deleted | ✓ closed | medium | 2026-08-25 | 1 | 1 |
| [sase-tw.10](sase-tw.10.md) | Finish the \`links:\` frontmatter inlet as an authoring path | ◐ in_progress | medium | 2026-08-25 | 1 | 0 |
| [sase-tw.11](sase-tw.11.md) | Make every audited read a discovery moment | ✓ closed | medium | 2026-08-25 | 1 | 1 |
| [sase-tw.12](sase-tw.12.md) | ACE stops flattening the relation type | ◐ in_progress | medium | 2026-08-25 | 1 | 0 |
| [sase-tw.13](sase-tw.13.md) | \`relation:\`, \`linked:\`, and \`artifact:\` on the Agent pane | ◐ in_progress | medium | 2026-08-25 | 1 | 0 |
| [sase-tw.14](sase-tw.14.md) | The judgment tier, the flag removal, and the two workflow lines | ◐ in_progress | medium | 2026-08-25 | 1 | 0 |
| [sase-tw.2](sase-tw.2.md) | Audited reads become durable and publish with the agent's commits | ✓ closed | medium | 2026-08-25 | 1 | 1 |
| [sase-tw.3](sase-tw.3.md) | A bead in either endpoint position gets its event | ◐ in_progress | medium | 2026-08-25 | 1 | 0 |
| [sase-tw.4](sase-tw.4.md) | Links follow renames instead of dangling | ◐ in_progress | medium | 2026-08-25 | 1 | 0 |
| [sase-tw.5](sase-tw.5.md) | Relation semantics, \`derived\` projection class, and a way to read them | ✓ closed | medium | 2026-08-25 | 1 | 2 |
| [sase-tw.6](sase-tw.6.md) | One derivation module behind one flag | ◐ in_progress | medium | 2026-08-25 | 1 | 0 |
| [sase-tw.7](sase-tw.7.md) | Derive at creation, on sidecar commit, and in the hourly sweep | ◐ in_progress | medium | 2026-08-25 | 1 | 0 |
| [sase-tw.8](sase-tw.8.md) | The citation channel stops starving | ◐ in_progress | medium | 2026-08-25 | 1 | 0 |
| [sase-tw.9](sase-tw.9.md) | Run the RELATED: note backfill | ◐ in_progress | small | 2026-08-25 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-tw: Artifact links that survive, derive themselves, and pay for the turn [in_progress]"]
    n1["sase-tw.1: A rebuild may delete only what it can prove was deleted [closed]"]
    n2["sase-tw.10: Finish the `links:` frontmatter inlet as an authoring path [in_progress]"]
    n3["sase-tw.11: Make every audited read a discovery moment [closed]"]
    n4["sase-tw.12: ACE stops flattening the relation type [in_progress]"]
    n5["sase-tw.13: `relation:`, `linked:`, and `artifact:` on the Agent pane [in_progress]"]
    n6["sase-tw.14: The judgment tier, the flag removal, and the two workflow lines [in_progress]"]
    n7["sase-tw.2: Audited reads become durable and publish with the agent's commits [closed]"]
    n8["sase-tw.3: A bead in either endpoint position gets its event [in_progress]"]
    n9["sase-tw.4: Links follow renames instead of dangling [in_progress]"]
    n10["sase-tw.5: Relation semantics, `derived` projection class, and a way to read them [closed]"]
    n11["sase-tw.6: One derivation module behind one flag [in_progress]"]
    n12["sase-tw.7: Derive at creation, on sidecar commit, and in the hourly sweep [in_progress]"]
    n13["sase-tw.8: The citation channel stops starving [in_progress]"]
    n14["sase-tw.9: Run the RELATED: note backfill [in_progress]"]
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
| [bbugyi200.athena.sase-tw.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.10/README.md) | [sase-tw.10](sase-tw.10.md) | 0 |
| [bbugyi200.athena.sase-tw.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.11/README.md) | [sase-tw.11](sase-tw.11.md) | 1 |
| [bbugyi200.athena.sase-tw.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.12/README.md) | [sase-tw.12](sase-tw.12.md) | 0 |
| [bbugyi200.athena.sase-tw.13](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.13/README.md) | [sase-tw.13](sase-tw.13.md) | 0 |
| [bbugyi200.athena.sase-tw.14](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.14/README.md) | [sase-tw.14](sase-tw.14.md) | 0 |
| [bbugyi200.athena.sase-tw.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.2/README.md) | [sase-tw.2](sase-tw.2.md) | 1 |
| [bbugyi200.athena.sase-tw.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.3/README.md) | [sase-tw.3](sase-tw.3.md) | 0 |
| [bbugyi200.athena.sase-tw.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.4/README.md) | [sase-tw.4](sase-tw.4.md) | 0 |
| [bbugyi200.athena.sase-tw.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.5/README.md) | [sase-tw.5](sase-tw.5.md) | 2 |
| [bbugyi200.athena.sase-tw.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.6/README.md) | [sase-tw.6](sase-tw.6.md) | 0 |
| [bbugyi200.athena.sase-tw.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.7/README.md) | [sase-tw.7](sase-tw.7.md) | 0 |
| [bbugyi200.athena.sase-tw.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.8/README.md) | [sase-tw.8](sase-tw.8.md) | 0 |
| [bbugyi200.athena.sase-tw.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.9/README.md) | [sase-tw.9](sase-tw.9.md) | 0 |
| [bbugyi200.athena.sase-tw.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.land/README.md) | [sase-tw](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e46adb7`](https://github.com/sase-org/sase/commit/e46adb77f14965dd49d680f35618e1b92b36a1cf) | fix(artifact-links): preserve aggregate rows across workspace rebuilds | [sase-tw.1](sase-tw.1.md) | 2026-08-25 16:02:32 EDT |
| sase | [`1282c7a`](https://github.com/sase-org/sase/commit/1282c7a8c7ff02b328b87bdbe33e28616f9e2020) | feat(artifact-cli): add artifact link relation subcommand | [sase-tw.5](sase-tw.5.md) | 2026-08-25 16:04:13 EDT |
| sase-core | [`sase-core@498077f`](https://github.com/sase-org/sase-core/commit/498077f19fdf4fed951b4b4f62369483a67e0d42) | feat(artifact-link): add relation module for link relation queries | [sase-tw.5](sase-tw.5.md) | 2026-08-25 16:06:33 EDT |
| sase | [`b2a0c68`](https://github.com/sase-org/sase/commit/b2a0c68a3ff0e497b007f6455e225fb80ccdb6fd) | feat(artifact-refs): expand artifact link neighborhoods in prompt rendering | [sase-tw.11](sase-tw.11.md) | 2026-08-25 16:47:48 EDT |
| sase | [`5d36fef`](https://github.com/sase-org/sase/commit/5d36fef263c6f44f7421487056ed5a12db6cc0d3) | feat(artifacts): add durable read-link outbox | [sase-tw.2](sase-tw.2.md) | 2026-08-25 17:14:12 EDT |
