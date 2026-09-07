# Bead: sase-xy — Reliable pager links

[Bead Pages](../README.md) / sase-xy

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.01q](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.01q.md) · **Assignee:** `sase-xy.land`
**Created:** 2026-09-07 10:02:18 EDT
**Plan:** [202609/pager\_link\_reliability.md](https://github.com/sase-org/sase--plans/blob/main/202609/pager_link_reliability.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/pager_link_reliability.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/pager_link_reliability.md

<!-- sase:links:end -->

## Description

Pager link presses land on the file or artifact the text's author meant: file paths and typed refs resolve against the workspace directory where the corresponding agent ran when knowable, fall back through reliable anchors, and spans carry :line suffixes faithfully.

## Notes

[2026-09-07T16:07:48Z · sase-xy.land] LAND AUDIT PAUSED FOR REMAINING EPIC WORK: all three phase commits and current entry-point wiring were reviewed; the focused pager/ACE/artifact/bead CLI suite passes (189 tests), and the sole child PROPOSED FOLLOW-UP from sase-xy.1 is already fixed on master by 777ec37dc (the exact lock test passes), so no task was filed. The three phase commits independently reproduce ready task sase-vh's stale SASE_PLAN provenance bug, so sase-vh was corroborated with +1 rather than duplicated. Post-start non-epic commits 777ec37dc and 287048d60 do not add a pager entry point or conflict with link contexts. Remaining epic-caused defects: a dead-end file press runs the git suffix search once in the background resolver and again synchronously from _apply_resolution/_unresolved_message to construct the toast (reproduction: git calls rise from 1 after resolve_ref to 2 after file_path_unresolved_message), violating one-search-per-anchor and the no-event-loop-I/O rule; merge_link_context also existence-checks/resolves anchors synchronously per label press; ACE _prepare_view_input constructs agent/patch contexts synchronously; and dangling-ref identity drops workspace_num even though typed-ref resolution depends on it. A child correction plan is being proposed; resume landing after it closes.

[2026-09-07T19:00:23Z · sase-xy.4.land--1] NESTED LANDING BLOCKER after sase-xy.4 closed: rechecked the parent landing note, every current descendant and note, plan:202609/pager_link_reliability.md, current origin/master drift through a9f95ca5e, and the parent epic-symbol ledger. The correction child sase-xy.4 is closed and its plan is done; post-close just symvision passes and sase-xy has no epic-symbol entries. Parent sase-xy cannot close yet because sibling child epic sase-xy.5 remains in_progress: only phase 5.1 is closed, while repository-resolution 5.2, pager-integration 5.3, and rendered-link-contract 5.4 are still in_progress. Its phase 5.1 also has a PROPOSED FOLLOW-UP for stale pending_actions Symvision URI pragmas that its own land agent must triage. The parent plan therefore remains active; resume its landing audit after sase-xy.5 closes.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-xy.1](sase-xy.1.md) | Context-aware hard search in the resolver | ✓ closed | medium | 2026-09-07 | 1 | 1 |
| [sase-xy.2](sase-xy.2.md) | Thread real contexts from every pager entry point | ✓ closed | medium | 2026-09-07 | 1 | 1 |
| [sase-xy.3](sase-xy.3.md) | Scanned spans carry line suffixes and shed trailing dots | ✓ closed | small | 2026-09-07 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-xy: Reliable pager links [in_progress]"]
    n1["sase-xy.1: Context-aware hard search in the resolver [closed]"]
    n2["sase-xy.2: Thread real contexts from every pager entry point [closed]"]
    n3["sase-xy.3: Scanned spans carry line suffixes and shed trailing dots [closed]"]
    n4["sase-xy.4: Finish reliable pager link landing [closed]"]
    n5["sase-xy.4.1: Resolve dead ends once off the event loop [closed]"]
    n6["sase-xy.4.2: Make pager context handling pure and identity-safe [closed]"]
    n7["sase-xy.5: Preserve pager link identity and resolve targets in their owning repositories [in_progress]"]
    n8["sase-xy.5.1: Parse document links into faithful semantic targets [closed]"]
    n9["sase-xy.5.2: Resolve targets using document ownership and repository identity [closed]"]
    n10["sase-xy.5.3: Carry semantic targets through every pager entry and action [closed]"]
    n11["sase-xy.5.4: Exercise every rendered link through real pager navigation [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n4 --> n5
    n4 --> n6
    n0 --> n7
    n7 --> n8
    n7 --> n9
    n7 --> n10
    n7 --> n11
    n1 -.-> n2
    n1 -.-> n3
    n5 -.-> n6
    n8 -.-> n9
    n8 -.-> n10
    n9 -.-> n10
    n10 -.-> n11
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xy.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xy.1/README.md) | [sase-xy.1](sase-xy.1.md) | 1 |
| [bbugyi200.athena.sase-xy.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xy.2/README.md) | [sase-xy.2](sase-xy.2.md) | 1 |
| [bbugyi200.athena.sase-xy.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xy.3/README.md) | [sase-xy.3](sase-xy.3.md) | 1 |
| [bbugyi200.athena.sase-xy.4.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xy.4.1/README.md) | [sase-xy.4.1](sase-xy.4.1.md) | 1 |
| [bbugyi200.athena.sase-xy.4.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xy.4.2/README.md) | [sase-xy.4.2](sase-xy.4.2.md) | 1 |
| [bbugyi200.athena.sase-xy.4.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xy.4.land.md) | [sase-xy.4](sase-xy.4.md) | 0 |
| [bbugyi200.athena.sase-xy.5.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xy.5.2/README.md) | [sase-xy.5.2](sase-xy.5.2.md) | 2 |
| [bbugyi200.athena.sase-xy.5.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xy.5.3/README.md) | [sase-xy.5.3](sase-xy.5.3.md) | 1 |
| [bbugyi200.athena.sase-xy.5.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xy.5.4/README.md) | [sase-xy.5.4](sase-xy.5.4.md) | 1 |
| [bbugyi200.athena.sase-xy.5.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xy.5.land/README.md) | [sase-xy.5](sase-xy.5.md) | 0 |
| [bbugyi200.athena.sase-xy.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xy.land.md) | [sase-xy](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4bb47fc`](https://github.com/sase-org/sase/commit/4bb47fc987541c33386ee508024a956c44cbb79d) | feat(pager): resolve links against ordered workspace anchors | [sase-xy.1](sase-xy.1.md) | 2026-09-07 10:44:14 EDT |
| sase | [`f6501e3`](https://github.com/sase-org/sase/commit/f6501e308fbf83d544501c724e201c54762361b6) | feat(pager): include :line suffixes in scanned file-path spans | [sase-xy.3](sase-xy.3.md) | 2026-09-07 11:08:47 EDT |
| sase | [`a0fcc5a`](https://github.com/sase-org/sase/commit/a0fcc5ade1600a815f1f250dcc15d95e67060aaf) | feat(pager): thread link context through entry points | [sase-xy.2](sase-xy.2.md) | 2026-09-07 11:46:36 EDT |
| sase | [`5144564`](https://github.com/sase-org/sase/commit/51445642c37303762ef7bb51be7c49c680c19ee4) | feat(pager): resolve dead ends in one background pass | [sase-xy.4.1](sase-xy.4.1.md) | 2026-09-07 13:03:05 EDT |
| sase | [`4b90cc9`](https://github.com/sase-org/sase/commit/4b90cc9ee824c14021e0b2239f28ff7e509fd97c) | fix(pager): keep context merge pure and dangling identity workspace-safe | [sase-xy.4.2](sase-xy.4.2.md) | 2026-09-07 13:49:34 EDT |
| sase | [`d8a299c`](https://github.com/sase-org/sase/commit/d8a299c2c3e401d9a08f5802849c15afb3eceb7b) | feat(pager-refs): add Python adapter for document-owned source-path resolution | [sase-xy.5.2](sase-xy.5.2.md) | 2026-09-07 17:56:02 EDT |
| sase-core | [`sase-core@0ec3050`](https://github.com/sase-org/sase-core/commit/0ec30508fc0baa339cec0d89b1c5b70c3d800538) | feat(artifact-ref): resolve document-owned source paths by repository identity | [sase-xy.5.2](sase-xy.5.2.md) | 2026-09-07 17:58:40 EDT |
| sase | [`2b08ca3`](https://github.com/sase-org/sase/commit/2b08ca3017aade6523ab8fcb16d36460f6ed8866) | feat(pager): carry semantic targets and owner provenance through every action | [sase-xy.5.3](sase-xy.5.3.md) | 2026-09-07 18:50:46 EDT |
| sase | [`2ba228d`](https://github.com/sase-org/sase/commit/2ba228da326eedba37e66c5b8eb73ed4525b2967) | test(pager): enforce rendered-link contract through real navigation | [sase-xy.5.4](sase-xy.5.4.md) | 2026-09-07 19:51:30 EDT |
