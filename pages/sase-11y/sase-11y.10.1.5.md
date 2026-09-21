# Bead: sase-11y.10.1.5 — Update the documentation for the service host

[Bead Pages](../README.md) / [sase-11y.10.1](sase-11y.10.1.md) / sase-11y.10.1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.10](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.10.md) · **Assignee:** `sase-11y.10.1.5` · **Size:** medium
**Created:** 2026-09-20 13:56:16 EDT · **Closed:** 2026-09-21 03:26:18 EDT
**Plan:** [202609/service\_host\_sunset.md](https://github.com/sase-org/sase--plans/blob/main/202609/service_host_sunset.md)

## Description

docs: rewrite docs/axe.md around the scheduler/host split, update ace, cli, configuration, plugins, remote_dispatch, and mobile_gateway for `sase service`, and retitle the mkdocs nav entry.

## Notes

[2026-09-21T07:24:40Z · sase-11y.10.1.5] PROPOSED FOLLOW-UP: symvision flags AxeDesiredState, lifecycle_journal_path, read_recent_successful_starts as unused on HEAD (axe-cli leftovers, reproduced on clean tree)

[2026-09-21T07:25:11Z · sase-11y.10.1.5] PROPOSED FOLLOW-UP: docs/init.md still documents the service_host flag gate for service init (out of scope for this bead)

[2026-09-21T07:25:42Z · sase-11y.10.1.5] PROPOSED FOLLOW-UP: test_update_json_schema_version_is_pinned_to_dev_schema and test_dev_extension_exposes_every_collected_name fail on clean HEAD

[2026-09-21T07:26:18Z · sase-11y.10.1.5] Docs rewritten around scheduler/host split (axe, ace, cli, configuration, plugins, remote_dispatch, mobile_gateway, mkdocs nav) plus stale beta drop in parser_service help. Verified: just fmt clean; all lint gates pass except symvision which fails identically on clean HEAD; diff-scoped lane shows only 2 failures that reproduce on clean HEAD; 31 parser help tests pass; no epic-symbols.

## Dependencies

- **Depends on:** [sase-11y.10.1.3](sase-11y.10.1.3.md) ✓ · ⧖ 2026-09-20
- **Depends on:** [sase-11y.10.1.4](sase-11y.10.1.4.md) ✓ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.10.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.10.1.5/README.md) | [sase-11y.10.1.5](sase-11y.10.1.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0ea0f5a`](https://github.com/sase-org/sase/commit/0ea0f5a7b3102b717228d32bdd974f870e57b19b) | docs(service-host): rewrite docs around the scheduler/host split | [sase-11y.10.1.5](sase-11y.10.1.5.md) | 2026-09-21 03:28:21 EDT |
