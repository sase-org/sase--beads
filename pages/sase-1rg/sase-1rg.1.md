# Bead: sase-1rg.1 — Core rebase-conflict policy for agent publication

[Bead Pages](../README.md) / [sase-1rg](README.md) / sase-1rg.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.cp--5` · **Assignee:** `sase-1rg.1` · **Size:** small
**Created:** 2026-11-06 05:46:48 EST · **Closed:** 2026-11-06 08:19:19 EST
**Plan:** [202611/agent\_health\_watch\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_health_watch_fixes.md)

## Description

pub-policy: add a sase-core decision that says whether a publication rebase's conflicted paths are regenerable index pages that can take the upstream side, or must escalate, and expose it through the Python binding.

## Notes

[2026-11-06T13:19:19Z · sase-1rg.1] pub-policy done and verified. sase-core (linked checkout, working tree only): decide_publication_rebase_conflict in agent_publication_recovery/replay.rs (resolve_upstream iff every path is a regenerable index page: root README.md, schema.json, sessions/families pages, agents/*/README.md, users/machine/hood README.md; escalate with per-path reasons for prompts/**, artifacts/**, owner content, archive objects, unknown) plus wire types, facade exports, sase_core_py binding, and Rust tests incl. the exact apollo conflict set (README.md + users/bbugyi200/README.md) as resolve_upstream and a mixed set as escalate. Python: adapter + PublicationRebaseConflictDecision + umbrella re-export in sase/core, 2 new tests in tests/core/test_agent_publication_recovery.py, and --epic-symbol sase-1rg.2(decide_publication_rebase_conflict) in Justfile for the pub-heal consumer. Verified: sase_core replay tests (4 new pass, 57-file suite pass), sase_core_py binding test passes, sase pytest file 22/22 pass, rebuilt extension returns resolve_upstream for the apollo paths, sase-core clippy/cargo-check/fmt clean, sase check full run verdict no_new_failures (60240 passed; 2 failures are pre-triaged KNOWN+FLAKY in unrelated tests/test_pytest_isolation_guards.py). PENDING LAND AGENT (no history-write authorization this turn): commit+push the sase-core working tree, then move sase-core-revision.txt past that commit (ratchet-core-revision or six-hourly ratchet); sase CI builds core from the pin so the Python adapter stays red there until the pin moves.

## Dependencies

- **Blocks:** [sase-1rg.2](sase-1rg.2.md) ◐ · ⧖ 2026-11-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rg.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rg.1/README.md) | [sase-1rg.1](sase-1rg.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@e9c0a99`](https://github.com/sase-org/sase-core/commit/e9c0a99f6be21da7adeef77b14f52e83c59ef7c0) | feat(publication): add core rebase-conflict policy for agent publication | [sase-1rg.1](sase-1rg.1.md) | 2026-11-06 08:20:24 EST |
| sase | [`2072bd6`](https://github.com/sase-org/sase/commit/2072bd6d2ef993f1dfaf02be70b97eade7a7a1ca) | feat(publication): add core rebase-conflict policy for agent publication | [sase-1rg.1](sase-1rg.1.md) | 2026-11-06 08:21:46 EST |
