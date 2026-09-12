# Bead: sase-zs.6 — Migrate ad-hoc GitHub call sites onto the shared runners

[Bead Pages](../README.md) / [sase-zs](README.md) / sase-zs.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0k6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0k6.md) · **Assignee:** `sase-zs.6` · **Size:** medium
**Created:** 2026-09-12 09:44:54 EDT · **Closed:** 2026-09-12 15:46:48 EDT
**Plan:** [202609/github\_network\_resilience.md](https://github.com/sase-org/sase--plans/blob/main/202609/github_network_resilience.md)

## Description

adoption: move the scattered direct `gh` subprocess calls and the remaining network git paths in agents sync and bead sync onto the shared retrying runners so resilience is uniform rather than per-call-site.

## Notes

[2026-09-12T19:46:48Z · sase-zs.6] Migrated GitHub and network git call sites to shared retry-aware runners; verified focused pytest for GitHub/plugin/doctor/agents-sync coverage passed and just check passed (including full scoped tests); sase bead epic-symbols sase-zs.6 reports no entries.

## Dependencies

- **Depends on:** [sase-zs.3](sase-zs.3.md) ✓ · ⧖ 2026-09-12
- **Depends on:** [sase-zs.5](sase-zs.5.md) ✓ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zs.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zs.6/README.md) | [sase-zs.6](sase-zs.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`072d657`](https://github.com/sase-org/sase/commit/072d657ab75d67d4b613393933474176a86d3a29) | fix(github): route network calls through shared runners | [sase-zs.6](sase-zs.6.md) | 2026-09-12 16:12:08 EDT |
