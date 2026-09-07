# Bead: sase-y3.2 — Authorize before mutating, with honest machine origin

[Bead Pages](../README.md) / [sase-y3](README.md) / sase-y3.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.04n](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04n.md) · **Assignee:** `sase-y3.2` · **Size:** medium
**Created:** 2026-09-07 15:14:46 EDT · **Closed:** 2026-09-07 17:14:05 EDT
**Plan:** [202609/machine\_link\_mutations\_off\_primary.md](https://github.com/sase-org/sase--plans/blob/main/202609/machine_link_mutations_off_primary.md)

## Description

authorize-before-mutate: gate every background link-maintenance writer (rename repair, backfill sweep, outbox drain, referenced-by refresh) on machine writability of each sidecar root before any worktree write, skip unauthorized roots with diagnostics, and replace defaulted user mutation origins with explicit machine origin on background commit paths.

## Notes

[2026-09-07T21:14:05Z · sase-y3.2] Background link writers now probe machine writability before any sidecar worktree write and skip unauthorized roots with a diagnostic (e.g. 'research root not machine-writable: resolves to primary #0'). Sweep persist, outbox drain, rename repair via reconcile, and referenced-by refresh leave a primary-#0 sidecar byte-identical with no commit; persist_artifact_link_graph_mutation forwards mutation_origin (interactive default user; sweep/drain/refresh pass machine). Interactive doctor --fix and plan-propose derivation stay user-origin. just check passed (full suite after Justfile re-key of stale sase-xz.4 epic-symbols onto open parent sase-xz).

## Dependencies

- **Depends on:** [sase-y3.1](sase-y3.1.md) ✓ · ⧖ 2026-09-07
- **Blocks:** [sase-y3.3](sase-y3.3.md) ◐ · ⧖ 2026-09-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-y3.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-y3.2/README.md) | [sase-y3.2](sase-y3.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`87f4cf1`](https://github.com/sase-org/sase/commit/87f4cf1416da9963e599e4e3fc0e04eeef64b6b5) | fix(sdd): gate background artifact-link writers on machine writability | [sase-y3.2](sase-y3.2.md) | 2026-09-07 18:09:28 EDT |
