# Bead: sase-b9.4 — Docs, skill, and ledger reference

[Bead Pages](../README.md) / [sase-b9](README.md) / sase-b9.4

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b9.4` · **Size:** small
**Created:** 2026-07-30 14:36:48 UTC · **Closed:** 2026-07-30 16:36:33 UTC
**Plan:** [202607/artifact\_consumption\_ledger.md](https://github.com/sase-org/sase--plans/blob/main/202607/artifact_consumption_ledger.md)

## Description

docs-and-ledger-reference: document the ledger file, its record shape, the role vocabulary, and the new read surfaces in the artifact documentation and the `sase_artifact_file` skill source, and regenerate the deployed skill.

## Notes

[2026-07-30T16:36:33Z · sase-b9.4] Updated artifact docs, CLI docs, artifact show help text, and the sase_artifact_file source/deployed skill for the consumption ledger; repaired missing SDD PROMPT links that blocked validation; verified with .venv/bin/sase skill init --check, artifact list/show help checks, plan links validate -q, and just check.

## Dependencies

- **Depends on:** [sase-b9.3](sase-b9.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-b9.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b9.4/README.md) | [sase-b9.4](sase-b9.4.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`0d01edb`](https://github.com/sase-org/sase/commit/0d01edb911a117c69515ba1947c8d0f904e3c458) | docs(artifacts): document artifact consumption ledger | [sase-b9.4](sase-b9.4.md) | 2026-07-30 16:39:50 |
| sase--plans | [`sase--plans@99dadd3`](https://github.com/sase-org/sase--plans/commit/99dadd3b3eb33be38a7b405fb43efa9b607427a7) | docs(plans): repair prompt links for artifact plans | [sase-b9.4](sase-b9.4.md) | 2026-07-30 16:46:57 |
