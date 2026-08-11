# Bead: sase-jd.1 — external\_ref bead identity field

[Bead Pages](../README.md) / [sase-jd](README.md) / sase-jd.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.xp](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.xp/README.md) · **Assignee:** `sase-jd.1` · **Size:** large
**Created:** 2026-08-10 19:13:24 EDT · **Closed:** 2026-08-10 21:03:41 EDT
**Plan:** [202608/external\_artifact\_ingestion.md](https://github.com/sase-org/sase--plans/blob/main/202608/external_artifact_ingestion.md)

## Description

bead_ref: add the nullable, partially-unique external_ref column to the sase-core bead schema and thread it through wire, jsonl, events, read, mutation, CLI, history, and search plus the Python mirrors; add the project-qualified external ref normalizer and widen bug_links to task beads through it.

## Notes

[2026-08-11T01:03:41Z · sase-jd.1] Implemented external_ref bead identity plan; verified just install, just check, just check-full, cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, and cargo test --workspace.

## Dependencies

- **Blocks:** [sase-jd.4](sase-jd.4.md) ✓ · ⧖ 2026-08-10
- **Blocks:** [sase-jd.6](sase-jd.6.md) ✓ · ⧖ 2026-08-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-jd.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-jd.1.md) | [sase-jd.1](sase-jd.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@730a78f`](https://github.com/sase-org/sase-core/commit/730a78f005b10a2b2ed99892cfed2a1111f8215f) | feat(beads): add external ref identity field | [sase-jd.1](sase-jd.1.md) | 2026-08-10 21:06:12 EDT |
| sase | [`fd93aab`](https://github.com/sase-org/sase/commit/fd93aab1d4c850d10fddb13330108d4e0627a0a1) | feat(beads): surface external refs in Python workflows | [sase-jd.1](sase-jd.1.md) | 2026-08-10 21:12:20 EDT |
