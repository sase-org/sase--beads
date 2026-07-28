# Bead: sase-ae.2 — Provenance manifest and monotonic overwrite guard

[Bead Pages](../README.md) / [sase-ae](README.md) / sase-ae.2

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ae.2` · **Size:** medium
**Created:** 2026-07-28 11:54:30 UTC · **Closed:** 2026-07-28 12:49:50 UTC
**Plan:** [202607/skill\_deploy\_thrash.md](https://github.com/sase-org/sase--plans/blob/main/202607/skill_deploy_thrash.md)

## Description

manifest: record the source commit and xprompt-set hash in a chezmoi-versioned JSON manifest, then refuse deploys whose source revision is a descendant of or unrelated to the recorded one, bootstrapping cleanly when the manifest is missing.

## Notes

[2026-07-28T12:49:35Z · sase-ae.2] Implemented chezmoi-versioned .sase-skills-manifest.json with source SHA, deterministic selected-xprompt SHA-256, stable deploy time, bootstrap recovery, and monotonic ancestry refusal for rollback/divergence; --force deliberately overrides and records incoming provenance. Integrated direct/deferred deploy path staging and identical-provenance no-op behavior. Verification: focused manifest/handler suite 20 passed; broader relevant suite 60 passed; formatting, ruff, mypy, Symvision, and toobig passed in just check. Full fast suite: 22,932 passed, 7 skipped, with one unrelated load-sensitive plan-launch concurrency timeout that passed immediately alone (1 passed). just check's SASE validation remains blocked by 229 pre-existing plan/prompt link errors in the shared SDD plans corpus.

## Dependencies

- **Depends on:** [sase-ae.1](sase-ae.1.md) ✓
- **Blocks:** [sase-ae.3](sase-ae.3.md) ✓
- **Blocks:** [sase-ae.5](sase-ae.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ae.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ae.2/README.md) | [sase-ae.2](sase-ae.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`046a92a`](https://github.com/sase-org/sase/commit/046a92a3b6ce4495d53f431bcca8008c895c8413) | feat(skills): enforce monotonic deploy provenance (sase-ae.2) | [sase-ae.2](sase-ae.2.md) | 2026-07-28 12:51:49 |
