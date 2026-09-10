# Bead: sase-z8.1 — Detect stale scripts and make local installation and refresh reliable

[Bead Pages](../README.md) / [sase-z8](README.md) / sase-z8.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0i9](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0i9.md) · **Assignee:** `sase-z8.1` · **Size:** medium
**Created:** 2026-09-10 09:46:04 EDT · **Closed:** 2026-09-10 10:28:06 EDT
**Plan:** [202609/completion\_freshness.md](https://github.com/sase-org/sase--plans/blob/main/202609/completion_freshness.md)

## Description

completion_freshness: add content-based diagnostics, reliable installation, explicit refresh, and refresh from the updated executable.

## Notes

[2026-09-10T14:28:06Z · sase-z8.1] Implemented content-based completion freshness diagnostics, explicit completion refresh, staged zsh publication, bounded post-update child refresh, and zsh registration shadow checks. Verified with focused pytest suites, update-command tests, just _lint-symvision, just check, git diff --check, and sase bead epic-symbols sase-z8.1.

## Dependencies

- **Blocks:** [sase-z8.2](sase-z8.2.md) ◐ · ⧖ 2026-09-10
- **Blocks:** [sase-z8.3](sase-z8.3.md) ◐ · ⧖ 2026-09-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-z8.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-z8.1/README.md) | [sase-z8.1](sase-z8.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`25266f2`](https://github.com/sase-org/sase/commit/25266f215dd16b12da78f0aed9cf2a02b3c245c0) | feat(completion): refresh stale shell scripts reliably | [sase-z8.1](sase-z8.1.md) | 2026-09-10 10:29:48 EDT |
