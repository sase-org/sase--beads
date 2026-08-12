# Bead: sase-k2.2 — Configurable bug and pull-request filters

[Bead Pages](../README.md) / [sase-k2](README.md) / sase-k2.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.yn](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.yn/README.md) · **Assignee:** `sase-k2.2` · **Size:** large
**Created:** 2026-08-12 11:29:07 EDT
**Plan:** [202608/external\_mirror\_refinement.md](https://github.com/sase-org/sase--plans/blob/main/202608/external_mirror_refinement.md)

## Description

filters: add external_mirror.issues.filters and external_mirror.pull_requests.filters as glob criterion lists with "!"-prefixed exclusions, default the PR head-ref criterion to drop release-please and release-plz branches, and migrate exclude_labels and pr_authors onto the new surface as deprecated aliases.

## Dependencies

- **Blocks:** [sase-k2.4](sase-k2.4.md) ◐ · ⧖ 2026-08-12
- **Blocks:** [sase-k2.5](sase-k2.5.md) ◐ · ⧖ 2026-08-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-k2.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-k2.2.md) | [sase-k2.2](sase-k2.2.md) | 0 |
