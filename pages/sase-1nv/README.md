# Bead: sase-1nv — Unblock the stalled sase-1nf epic

[Bead Pages](../README.md) / sase-1nv

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.13m](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.13m.md) · **Assignee:** `sase-1nv.land`
**Created:** 2026-10-24 07:01:32 EDT
**Plan:** [202610/unblock\_sase\_1nf.md](https://github.com/sase-org/sase--plans/blob/main/202610/unblock_sase_1nf.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/unblock_sase_1nf.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/unblock_sase_1nf.md

<!-- sase:links:end -->

## Description

Both stalled sase-1nf tracks move again without anyone waiting on a question. gc-measure closes, so the waiting gc-fix agent starts. Agent-run Apollo pushes authenticate as bbugyi200. Publication requests name the commit their agent actually created, and existing stale-revision rows are repaired explicitly. recovery-proof (sase-1nf.10.1.9) closes with evidence, so the waiting sase-1nf.10.1 land agent and then pub-recover (sase-1nf.11) resume on a backlog that can drain.

## Notes

[2026-10-25T02:14:49Z · sase-1nn.8.4.3.land] DISCOVERED ISSUE: Post-release-epic-start commit 87827788c25c826b46e9c76f70b105a1ce624313 by phase sase-1nv.5 tracked 99 .sase-evidence files (17,317,023 bytes); 38 legacy terminology occurrences in 15 files now enter tests/_macro_terminology_common.py iter_scope_files. Master Gate 40149338072 attempt 2 job 121044125086, Full CI 40138926091 attempt 2 all Python legs, and release PR321 floor smoke 40140631901 job 121011445621 fail test_macro_resources_avoid_xprompt_terms. Actual 0.42.5 binding validation passes 879/879; the floor smoke fails on this audit. Release remaining-work plan will retain these historical bytes as immutable artifacts before removing the scratch evidence from tracked source, without weakening the terminology guard. Evidence file:explicit:eca15519850917b7992759fe. No duplicate task.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1nv.1](sase-1nv.1.md) | Close gc-measure and hand its findings to gc-fix | ◐ in_progress | medium | 2026-10-24 | 1 | 0 |
| [sase-1nv.2](sase-1nv.2.md) | Apollo GitHub pushes authenticate as bbugyi200 | ✓ closed | small | 2026-10-24 | 1 | 0 |
| [sase-1nv.3](sase-1nv.3.md) | Publication requests name the committed revision | ✓ closed | medium | 2026-10-24 | 1 | 2 |
| [sase-1nv.4](sase-1nv.4.md) | Explicit repair for existing stale-revision outbox rows | ✓ closed | medium | 2026-10-24 | 1 | 2 |
| [sase-1nv.5](sase-1nv.5.md) | Prove recovery on both hosts and close recovery-proof | ◐ in_progress | medium | 2026-10-24 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1nv: Unblock the stalled sase-1nf epic [in_progress]"]
    n1["sase-1nv.1: Close gc-measure and hand its findings to gc-fix [in_progress]"]
    n2["sase-1nv.2: Apollo GitHub pushes authenticate as bbugyi200 [closed]"]
    n3["sase-1nv.3: Publication requests name the committed revision [closed]"]
    n4["sase-1nv.4: Explicit repair for existing stale-revision outbox rows [closed]"]
    n5["sase-1nv.5: Prove recovery on both hosts and close recovery-proof [in_progress]"]
    n6["sase-1nv.5.1: Finish the remaining publication recovery proof [in_progress]"]
    n7["sase-1nv.5.1.1: Add exact-request selection to the Rust publication policy [closed]"]
    n8["sase-1nv.5.1.2: Expose exact publication retries through the existing CLI [closed]"]
    n9["sase-1nv.5.1.3: Verify host readiness and identify three publishable stopped requests [in_progress]"]
    n10["sase-1nv.5.1.4: Prove one formerly failing Athena timeout request [in_progress]"]
    n11["sase-1nv.5.1.5: Prove one formerly failing Apollo bob-cli request [in_progress]"]
    n12["sase-1nv.5.1.6: Prove one formerly failing Apollo SASE request [in_progress]"]
    n13["sase-1nv.5.1.7: Publish the final recovery acceptance and downstream handoff [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n5 --> n6
    n6 --> n7
    n6 --> n8
    n6 --> n9
    n6 --> n10
    n6 --> n11
    n6 --> n12
    n6 --> n13
    n2 -.-> n5
    n3 -.-> n4
    n4 -.-> n5
    n7 -.-> n8
    n8 -.-> n9
    n9 -.-> n10
    n10 -.-> n11
    n11 -.-> n12
    n12 -.-> n13
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nv.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nv.1/README.md) | [sase-1nv.1](sase-1nv.1.md) | 0 |
| [bbugyi200.athena.sase-1nv.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nv.2/README.md) | [sase-1nv.2](sase-1nv.2.md) | 0 |
| [bbugyi200.athena.sase-1nv.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nv.3.md) | [sase-1nv.3](sase-1nv.3.md) | 2 |
| [bbugyi200.athena.sase-1nv.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nv.4.md) | [sase-1nv.4](sase-1nv.4.md) | 2 |
| [bbugyi200.athena.sase-1nv.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nv.5.md) | [sase-1nv.5](sase-1nv.5.md) | 0 |
| [bbugyi200.athena.sase-1nv.5.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nv.5.1.1/README.md) | [sase-1nv.5.1.1](sase-1nv.5.1.1.md) | 1 |
| [bbugyi200.athena.sase-1nv.5.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nv.5.1.2/README.md) | [sase-1nv.5.1.2](sase-1nv.5.1.2.md) | 1 |
| [bbugyi200.athena.sase-1nv.5.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nv.5.1.3/README.md) | [sase-1nv.5.1.3](sase-1nv.5.1.3.md) | 0 |
| [bbugyi200.athena.sase-1nv.5.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nv.5.1.4/README.md) | [sase-1nv.5.1.4](sase-1nv.5.1.4.md) | 0 |
| [bbugyi200.athena.sase-1nv.5.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nv.5.1.5/README.md) | [sase-1nv.5.1.5](sase-1nv.5.1.5.md) | 0 |
| [bbugyi200.athena.sase-1nv.5.1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nv.5.1.6/README.md) | [sase-1nv.5.1.6](sase-1nv.5.1.6.md) | 0 |
| [bbugyi200.athena.sase-1nv.5.1.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nv.5.1.7/README.md) | [sase-1nv.5.1.7](sase-1nv.5.1.7.md) | 0 |
| [bbugyi200.athena.sase-1nv.5.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nv.5.1.land/README.md) | [sase-1nv.5.1](sase-1nv.5.1.md) | 0 |
| [bbugyi200.athena.sase-1nv.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nv.land/README.md) | [sase-1nv](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@e80f08d`](https://github.com/sase-org/sase-core/commit/e80f08dae98224ccc192a569d97fc13177a6d76f) | feat(publication): fulfill linked-scope rows when the page exists | [sase-1nv.3](sase-1nv.3.md) | 2026-10-24 09:22:13 EDT |
| sase | [`02cd3b3`](https://github.com/sase-org/sase/commit/02cd3b39b64358f37b2fa097f0ebfa1db2960e53) | feat(agents-sync): name publications with the post-commit SHA | [sase-1nv.3](sase-1nv.3.md) | 2026-10-24 09:25:19 EDT |
| sase-core | [`sase-core@7ec12d2`](https://github.com/sase-org/sase-core/commit/7ec12d2d7ad8e670abe26aa396259a512f330391) | feat(core): classify stale publication requests for revision repair (sase-1nv.4) | [sase-1nv.4](sase-1nv.4.md) | 2026-10-24 11:45:47 EDT |
| sase | [`7b1b437`](https://github.com/sase-org/sase/commit/7b1b43755821fb4b6fe9ab8f51d09fcff0e46879) | feat(agents-sync): add report-first repair for stale publication revision rows (sase-1nv.4) | [sase-1nv.4](sase-1nv.4.md) | 2026-10-24 11:48:49 EDT |
| sase-core | [`sase-core@ae38a60`](https://github.com/sase-org/sase-core/commit/ae38a60e8324214a60248df2286bd6963484676e) | feat(publication-recovery): add exact-key constraint to drain selection | [sase-1nv.5.1.1](sase-1nv.5.1.1.md) | 2026-10-26 18:31:53 EDT |
| sase | [`aa97e54`](https://github.com/sase-org/sase/commit/aa97e544b0e68c0f1c0211bdfb75cf1b0b3e48d1) | feat(agents-sync): add --retry-key for exact publication retries | [sase-1nv.5.1.2](sase-1nv.5.1.2.md) | 2026-10-26 19:53:11 EDT |
