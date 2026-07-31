# Bead: sase-cp — Migrate the sase\_beads skill into generated Tier 2 memory

[Bead Pages](../README.md) / sase-cp

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.qn](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.qn/README.md) · **Assignee:** `sase-cp.land`
**Created:** 2026-07-31 19:00:51 UTC · **Closed:** 2026-07-31 20:12:47 UTC
**Plan:** [202607/sase\_beads\_memory.md](https://github.com/sase-org/sase--plans/blob/main/202607/sase_beads_memory.md)

## Description

`sase bead` guidance lives in a concise, auto-generated `sase/memory/sase_beads.md` long-term memory note that every sase-managed project and the home root receive automatically, and no copy of the `/sase_beads` skill remains in the sase repo, the chezmoi repo, or the home directory.

## Notes

[2026-07-31T20:12:47Z · sase-cp.land] Closed after landing audit. Verified phase commits: primary d6a2cce1f and 642b4f490, linked chezmoi 67b58a6f, and visual-golden repair 7404e4ab1; all three child phases were already closed. Integrated 50988fe7f semantics into generated Tier 2 bead memory: bead update now documents multi-ID atomic common-field updates, unchanged no-op reporting, and whole-batch descendant-close validation. Verification passed: focused memory asset/parity/audited-read/idempotency/example-parse checks, just test-visual (393 passed, 1 skipped), and just check after rebuilding the refreshed local sase-core binding and regenerating home memory. Rollout evidence: primary and linked chezmoi scans contain no generated /sase_beads skill source/copy, broad home scan found no deployed */skills/sase_beads directory outside excluded workspace/cache paths, and only the generated sase/memory/sase_beads.md notes remain. Filed follow-up task sase-cr for pruning retired generated skill targets and stale editable sources, citing sase-cp.3. Did not file the missing-backlink proposal because the plan and prompt already link to each other, and did not file the visual-golden proposal because commit 7404e4ab1 already repaired the named ACE PNG goldens and the visual suite is green.

[2026-07-31T20:24:01Z · sase-cp.land] Implemented the approved memory integration, regenerated memory outputs, created ready follow-up task sase-cr, verified source/copy rollout evidence, ran just test-visual, just symvision, and final just check successfully.

## Phases

| Bead | Title | Status | Size | Agents | Commits |
|---|---|---|---|---:|---:|
| [sase-cp.1](sase-cp.1.md) | Generated Tier 2 bead memory note | ✓ closed | medium | 1 | 1 |
| [sase-cp.2](sase-cp.2.md) | Retire the sase\_beads skill source | ✓ closed | small | 1 | 2 |
| [sase-cp.3](sase-cp.3.md) | Remove deployed skill copies and verify rollout | ✓ closed | small | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-cp: Migrate the sase_beads skill into generated Tier 2 memory [closed]"]
    n1["sase-cp.1: Generated Tier 2 bead memory note [closed]"]
    n2["sase-cp.2: Retire the sase_beads skill source [closed]"]
    n3["sase-cp.3: Remove deployed skill copies and verify rollout [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n1 -.-> n2
    n2 -.-> n3
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-cp.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-cp.1/README.md) | [sase-cp.1](sase-cp.1.md) | 1 |
| [bbugyi200.athena.sase-cp.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-cp.2/README.md) | [sase-cp.2](sase-cp.2.md) | 2 |
| [bbugyi200.athena.sase-cp.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-cp.3/README.md) | [sase-cp.3](sase-cp.3.md) | 1 |
| [bbugyi200.athena.sase-cp.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-cp.land.md) | [sase-cp](README.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`d6a2cce`](https://github.com/sase-org/sase/commit/d6a2cce1f0e7464aa36dd3e22b77b95e57bef298) | feat(memory): generate Tier 2 bead workflow note | [sase-cp.1](sase-cp.1.md) | 2026-07-31 19:25:30 |
| sase | [`642b4f4`](https://github.com/sase-org/sase/commit/642b4f490b302311ce5b737ac76d3720f4404f01) | feat(memory): retire bundled sase\_beads skill source | [sase-cp.2](sase-cp.2.md) | 2026-07-31 19:43:03 |
| sase--plans | [`sase--plans@5aa2ae3`](https://github.com/sase-org/sase--plans/commit/5aa2ae3710264aa1f1e9f88c2ed0716c41869c93) | docs: link sase\_beads\_memory prompt provenance | [sase-cp.2](sase-cp.2.md) | 2026-07-31 19:44:06 |
| chezmoi | [`chezmoi@67b58a6`](https://github.com/bbugyi200/dotfiles/commit/67b58a6f6e5eee2bef7d3e9ccd39f4f5598bbab2) | chore(skills): remove deployed sase\_beads skill copies | [sase-cp.3](sase-cp.3.md) | 2026-07-31 19:46:33 |
| sase | [`33c6311`](https://github.com/sase-org/sase/commit/33c63112c911958e5a3c6111eb4f01caeb945794) | docs(memory): document bulk bead update semantics | [sase-cp](README.md) | 2026-07-31 20:25:18 |
| sase--plans | [`sase--plans@6d40abb`](https://github.com/sase-org/sase--plans/commit/6d40abb49235501243e564e15e4f16d90fb8172b) | chore(plans): mark bead memory epic done | [sase-cp](README.md) | 2026-07-31 20:26:46 |
