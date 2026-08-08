# Bead: sase-b5.1 — Sidecar-aware primary checkout and owning-project resolver

[Bead Pages](../README.md) / [sase-b5](README.md) / sase-b5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b5.1` · **Size:** small
**Created:** 2026-07-30 11:20:06 UTC · **Closed:** 2026-07-30 12:03:46 UTC
**Plan:** [202607/bead\_page\_association\_anchors.md](https://github.com/sase-org/sase--plans/blob/main/202607/bead_page_association_anchors.md)

## Description

anchor: add a shared resolver that maps any path inside a managed checkout — including a sidecar or linked-repo clone nested under it — to that checkout's primary repository root and canonical project name, with marker-first resolution and explicit fallbacks.

## Notes

[2026-07-30T12:03:46Z · sase-b5.1] Verified checkout anchor tests, copy-as palette tests, artifact-ref completion tests, just validate, just _lint-symvision, and full just check.

## Dependencies

- **Blocks:** [sase-b5.2](sase-b5.2.md) ✓
- **Blocks:** [sase-b5.3](sase-b5.3.md) ✓
- **Blocks:** [sase-b5.4](sase-b5.4.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-b5.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b5.1/README.md) | [sase-b5.1](sase-b5.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`ad0f038`](https://github.com/sase-org/sase/commit/ad0f038a05e9b840247a5c97822c2ee3ebb05830) | feat(sdd): add checkout anchor resolver | [sase-b5.1](sase-b5.1.md) | 2026-07-30 12:08:28 |
| sase--plans | [`sase--plans@218e78c`](https://github.com/sase-org/sase--plans/commit/218e78c4d802c357276be9866ed89786795914c7) | docs: add missing prompt backlinks | [sase-b5.1](sase-b5.1.md) | 2026-07-30 12:09:38 |
