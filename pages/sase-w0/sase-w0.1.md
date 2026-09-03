# Bead: sase-w0.1 — Row model and capability derivation behind the existing sub-tabs

[Bead Pages](../README.md) / [sase-w0](README.md) / sase-w0.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.5.md) · **Assignee:** `sase-w0.1` · **Size:** medium
**Created:** 2026-09-03 06:53:41 EDT
**Plan:** [202609/unified\_updates\_tab\_1.md](https://github.com/sase-org/sase--plans/blob/main/202609/unified_updates_tab_1.md)

## Description

rows: add the pure UpdateRow model, capability derivation, and shared version-label helpers; build rows once per load on the worker thread; re-point the action gates, hint builders, and agent-CLI mark predicates at the highlighted row while the sub-tab UI and every rendered pixel stay exactly as they are today.

## Dependencies

- **Blocks:** [sase-w0.2](sase-w0.2.md) ◐ · ⧖ 2026-09-03

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-w0.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-w0.1/README.md) | [sase-w0.1](sase-w0.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f67169e`](https://github.com/sase-org/sase/commit/f67169ea715310e8da8a8034bd1842f7bc051c88) | refactor(plugins-browser): extract row model and capability derivation into plugins\_browser\_rows | [sase-w0.1](sase-w0.1.md) | 2026-09-03 09:55:06 EDT |
