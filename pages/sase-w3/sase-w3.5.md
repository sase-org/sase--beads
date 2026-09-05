# Bead: sase-w3.5 — Identity query fields and the identity-reveal rung

[Bead Pages](../README.md) / [sase-w3](README.md) / sase-w3.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.b](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.b.md) · **Assignee:** `sase-w3.5` · **Size:** medium
**Created:** 2026-09-03 12:48:33 EDT · **Closed:** 2026-09-04 13:24:58 EDT
**Plan:** [202609/link\_follow\_reliability.md](https://github.com/sase-org/sase--plans/blob/main/202609/link_follow_reliability.md)

## Description

identity-queries: add closed identity fields to the bead, stitch, file, and plan dialects, handle profile-digest churn, build build_identity_reveal_query and slot it in as the rung before minimal widening, and add per-rung outcome counters to debug logging.

## Notes

[2026-09-04T17:24:58Z · sase-w3.5--1] Verified identity-queries for sase-w3.5: closed identity fields (beads id, stitches sha prefix, files id, plans/providers path; agents/patches reuse name), SHA prefix matching in Python profile evaluator and sase-core query evaluator, build_identity_reveal_query as ladder rung 5 before minimal widening, QueryRecord digest refusal for stale saved/history queries, and per-rung debug outcome counters. just check passed (lint + scoped 740/3520 tests). sase bead epic-symbols sase-w3.5 was empty.

## Dependencies

- **Depends on:** [sase-w3.4](sase-w3.4.md) ✓ · ⧖ 2026-09-03

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-w3.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-w3.5.md) | [sase-w3.5](sase-w3.5.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`df465e0`](https://github.com/sase-org/sase/commit/df465e063ad94af3e01aa9db964d931fbc1891f6) | feat(ace): add identity query fields and identity-reveal rung (sase-w3.5) | [sase-w3.5](sase-w3.5.md) | 2026-09-04 19:31:03 EDT |
| sase-core | [`sase-core@3e99850`](https://github.com/sase-org/sase-core/commit/3e99850e17d6ee555dc35974b6b7f7ff6325b1ad) | feat(query): prefix-match sha field values in the evaluator | [sase-w3.5](sase-w3.5.md) | 2026-09-04 21:42:50 EDT |
