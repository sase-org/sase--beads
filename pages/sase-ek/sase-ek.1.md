# Bead: sase-ek.1 — Repository kind on the wire, sidecars skipped in commit enumeration

[Bead Pages](../README.md) / [sase-ek](README.md) / sase-ek.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.si](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.si/README.md) · **Assignee:** `sase-ek.1` · **Size:** small
**Created:** 2026-08-03 10:32:38 UTC · **Closed:** 2026-08-03 10:45:00 UTC
**Plan:** [202608/commit\_completion\_excludes\_sidecars.md](https://github.com/sase-org/sase--plans/blob/main/202608/commit_completion_excludes_sidecars.md)

## Description

core_kind_filter: add a defaulted `kind` field to `ArtifactRefRepositoryWire` and skip `kind == "sidecar"` repositories in `append_commit_candidates` before spawning `git log`, leaving `resolve_commit` and every other kind untouched.

## Notes

[2026-08-03T10:45:00Z · sase-ek.1] Implemented core repository kind wire field and sidecar commit-inventory filter in linked sase-core; verified cargo fmt --all --check and cargo test -p sase_core.

## Dependencies

- **Blocks:** [sase-ek.2](sase-ek.2.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ek.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ek.1/README.md) | [sase-ek.1](sase-ek.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase-core | [`sase-core@3aa9d2a`](https://github.com/sase-org/sase-core/commit/3aa9d2a111b9cf0fe33fa1813b19491ce8bf8821) | fix(editor): exclude sidecar commits from artifact inventory | [sase-ek.1](sase-ek.1.md) | 2026-08-03 10:51:44 |
