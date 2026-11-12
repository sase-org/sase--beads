# Bead: sase-1sb — Security and robustness audit fixes

[Bead Pages](../README.md) / sase-1sb

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1bk](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1bk.md) · **Assignee:** `sase-1sb.land`
**Created:** 2026-11-11 17:38:52 EST
**Plan:** [202611/security\_bug\_audit\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202611/security_bug_audit_fixes.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202611/security_bug_audit_fixes.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/security_bug_audit_fixes.md

<!-- sase:links:end -->

## Description

Verified injection, traversal, privilege-gap, and state-corruption bugs from the codebase audit are fixed with regression tests

## Notes

[2026-11-12T10:30:31Z · sase-1sb.2.1.land] DISCOVERED ISSUE: Triaged PROPOSED FOLLOW-UP from sase-1sb.2.1.3 note #1 through /sase_new_task. The reported test_concurrent_edit_lock_acquisition_has_one_owner flake has a deterministic production race in phase sase-1sb.5's acquire_edit_lock: O_EXCL publishes an empty inode before os.write fills PID/token; a second contender reads None, treats that in-flight publication as stale, unlinks it, and acquires its own inode. Delaying only the first writer until the second acquisition returns yields ['first:owner', 'second:owner'] on ea4121387b. No real project state touched. Reproduction source/output: file:explicit:f7ff68994727a64108f4cdd2. Same-type and all-type searches and last-week task sweeps found no duplicate. This active epic has a direct causal link via .5, so no standalone task was created. Reject quarantine/retry as the remedy; fix atomic ownership publication/stale reclamation and cover the deterministic interleaving. The trust child .2.1 does not own this lock repair; leave it for this security epic's landing.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1sb.1](sase-1sb.1.md) | Stop $(cmd) execution in agent-authored prompt text | ✓ closed | medium | 2026-11-11 | 1 | 1 |
| [sase-1sb.2](sase-1sb.2.md) | Trust-gate command-bearing project-local config | ◐ in_progress | large | 2026-11-11 | 1 | 0 |
| [sase-1sb.3](sase-1sb.3.md) | Path-component validation for repo clone dirs and project log paths | ✓ closed | medium | 2026-11-11 | 1 | 1 |
| [sase-1sb.4](sase-1sb.4.md) | Shell-quote workflow interpolations, validate git refs, fix agent-guard parity | ✓ closed | medium | 2026-11-11 | 1 | 1 |
| [sase-1sb.5](sase-1sb.5.md) | Fix patch-lock fd double close and edit-lock acquisition races | ✓ closed | small | 2026-11-11 | 1 | 1 |
| [sase-1sb.6](sase-1sb.6.md) | Atomic writes and locking for MRU, history, and axe error state | ✓ closed | medium | 2026-11-11 | 1 | 1 |
| [sase-1sb.7](sase-1sb.7.md) | Chat-catalog cache lock handling and bead migration idempotency | ✓ closed | small | 2026-11-11 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1sb: Security and robustness audit fixes [in_progress]"]
    n1["sase-1sb.1: Stop $(cmd) execution in agent-authored prompt text [closed]"]
    n2["sase-1sb.2: Trust-gate command-bearing project-local config [in_progress]"]
    n3["sase-1sb.2.1: Digest-pinned trust for project-local commands [in_progress]"]
    n4["sase-1sb.2.1.1: Define the Rust local-command trust contract [closed]"]
    n5["sase-1sb.2.1.2: Persist trust and add human acknowledgment commands [closed]"]
    n6["sase-1sb.2.1.3: Enforce trust for merged config and file hooks [closed]"]
    n7["sase-1sb.2.1.4: Enforce trust for local macro workflows and finish integration [closed]"]
    n8["sase-1sb.3: Path-component validation for repo clone dirs and project log paths [closed]"]
    n9["sase-1sb.4: Shell-quote workflow interpolations, validate git refs, fix agent-guard parity [closed]"]
    n10["sase-1sb.5: Fix patch-lock fd double close and edit-lock acquisition races [closed]"]
    n11["sase-1sb.6: Atomic writes and locking for MRU, history, and axe error state [closed]"]
    n12["sase-1sb.7: Chat-catalog cache lock handling and bead migration idempotency [closed]"]
    n0 --> n1
    n0 --> n2
    n2 --> n3
    n3 --> n4
    n3 --> n5
    n3 --> n6
    n3 --> n7
    n0 --> n8
    n0 --> n9
    n0 --> n10
    n0 --> n11
    n0 --> n12
    n4 -.-> n5
    n5 -.-> n6
    n6 -.-> n7
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1sb.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1sb.1/README.md) | [sase-1sb.1](sase-1sb.1.md) | 1 |
| [bbugyi200.athena.sase-1sb.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1sb.2.md) | [sase-1sb.2](sase-1sb.2.md) | 0 |
| [bbugyi200.athena.sase-1sb.2.1.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1sb.2.1.1.md) | [sase-1sb.2.1.1](sase-1sb.2.1.1.md) | 3 |
| [bbugyi200.athena.sase-1sb.2.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1sb.2.1.2/README.md) | [sase-1sb.2.1.2](sase-1sb.2.1.2.md) | 2 |
| [bbugyi200.athena.sase-1sb.2.1.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1sb.2.1.3.md) | [sase-1sb.2.1.3](sase-1sb.2.1.3.md) | 1 |
| [bbugyi200.athena.sase-1sb.2.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1sb.2.1.4/README.md) | [sase-1sb.2.1.4](sase-1sb.2.1.4.md) | 1 |
| [bbugyi200.athena.sase-1sb.2.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1sb.2.1.land.md) | [sase-1sb.2.1](sase-1sb.2.1.md) | 1 |
| [bbugyi200.athena.sase-1sb.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1sb.3/README.md) | [sase-1sb.3](sase-1sb.3.md) | 1 |
| [bbugyi200.athena.sase-1sb.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1sb.4.md) | [sase-1sb.4](sase-1sb.4.md) | 1 |
| [bbugyi200.athena.sase-1sb.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1sb.5/README.md) | [sase-1sb.5](sase-1sb.5.md) | 1 |
| [bbugyi200.athena.sase-1sb.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1sb.6/README.md) | [sase-1sb.6](sase-1sb.6.md) | 1 |
| [bbugyi200.athena.sase-1sb.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1sb.7.md) | [sase-1sb.7](sase-1sb.7.md) | 1 |
| [bbugyi200.athena.sase-1sb.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1sb.land/README.md) | [sase-1sb](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6cdb74c`](https://github.com/sase-org/sase/commit/6cdb74c3e673c786a5d345985b1a9e9816e270d2) | fix(ace): make patch and edit locks race-safe | [sase-1sb.5](sase-1sb.5.md) | 2026-11-11 20:53:32 EST |
| sase | [`6a6549c`](https://github.com/sase-org/sase/commit/6a6549cf65140a1aac54083c45836ff0bcc1a33c) | fix(state): make history and axe JSON writes atomic | [sase-1sb.6](sase-1sb.6.md) | 2026-11-11 20:54:47 EST |
| sase | [`b9572a8`](https://github.com/sase-org/sase/commit/b9572a8d59b73123199c256c7da7be473bf41ccb) | fix(history): keep catalog cache on lock and make bead type migration restartable | [sase-1sb.7](sase-1sb.7.md) | 2026-11-11 21:18:13 EST |
| sase | [`22e1ef1`](https://github.com/sase-org/sase/commit/22e1ef1249059503a29749c548564dbf01da0825) | fix(sase-1sb.4): repair shell-arg-hardening regressions found by check | [sase-1sb.4](sase-1sb.4.md) | 2026-11-11 21:33:39 EST |
| sase | [`b366ab0`](https://github.com/sase-org/sase/commit/b366ab0b60bedce6fc2147f2dfd16c4d40b89801) | fix(paths): contain clone dirs and project log paths | [sase-1sb.3](sase-1sb.3.md) | 2026-11-11 21:57:03 EST |
| sase-core | [`sase-core@e7647bf`](https://github.com/sase-org/sase-core/commit/e7647bf7a37c53ddce11726024c69a55ec877760) | feat(config): add digest-pinned local-command trust contract and bindings | [sase-1sb.2.1.1](sase-1sb.2.1.1.md) | 2026-11-11 22:01:54 EST |
| sase | [`2e7ce5c`](https://github.com/sase-org/sase/commit/2e7ce5cea11b8cd5509d3b90e5567be7a1356852) | feat(config): add local-command trust projection adapter and contract tests | [sase-1sb.2.1.1](sase-1sb.2.1.1.md) | 2026-11-11 22:03:16 EST |
| sase | [`181b213`](https://github.com/sase-org/sase/commit/181b213e8c58f8c90357d1e56cf910b5c727c0ea) | fix(trust-policy): whitelist local-trust adapter in symvision and terminology guard | [sase-1sb.2.1.1](sase-1sb.2.1.1.md) | 2026-11-11 22:53:14 EST |
| sase | [`d0dc942`](https://github.com/sase-org/sase/commit/d0dc942c16b2da6cb3ddb6a38abee394ef1d10a3) | fix(prompts): prevent command substitution in agent text | [sase-1sb.1](sase-1sb.1.md) | 2026-11-12 01:03:32 EST |
| sase-core | [`sase-core@233cb41`](https://github.com/sase-org/sase-core/commit/233cb41d6bb7186a711e75999394570e9ad9943e) | feat(config): persist digest-pinned local command trust | [sase-1sb.2.1.2](sase-1sb.2.1.2.md) | 2026-11-12 01:29:04 EST |
| sase | [`7710dd0`](https://github.com/sase-org/sase/commit/7710dd0bc61b2b079886b0c8d8f632a18aba0b7d) | feat(config): add human-reviewed local command trust CLI | [sase-1sb.2.1.2](sase-1sb.2.1.2.md) | 2026-11-12 01:30:27 EST |
| sase | [`021cd73`](https://github.com/sase-org/sase/commit/021cd73021b62e9f92ccd6829c9ded59c80ed7cd) | feat(config): enforce trust for merged config and file hooks | [sase-1sb.2.1.3](sase-1sb.2.1.3.md) | 2026-11-12 04:21:44 EST |
| sase | [`ea41213`](https://github.com/sase-org/sase/commit/ea4121387b21bf727b021eb80e746a6054811ff4) | feat(config): enforce local-command trust for config macros | [sase-1sb.2.1.4](sase-1sb.2.1.4.md) | 2026-11-12 05:14:43 EST |
| sase | [`681de35`](https://github.com/sase-org/sase/commit/681de3542bdd024f8aa3ccfe247a9f1aa4b42ef2) | fix(config): enforce local command trust provenance | [sase-1sb.2.1](sase-1sb.2.1.md) | 2026-11-12 11:06:29 EST |
