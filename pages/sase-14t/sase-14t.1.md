# Bead: sase-14t.1 — Provider-disabled Jinja predicate

[Bead Pages](../README.md) / [sase-14t](README.md) / sase-14t.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0oi](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0oi.md) · **Assignee:** `sase-14t.1` · **Size:** small
**Created:** 2026-09-20 20:51:30 EDT · **Closed:** 2026-09-20 21:28:25 EDT
**Plan:** [202609/research\_swarm\_providers.md](https://github.com/sase-org/sase--plans/blob/main/202609/research_swarm_providers.md)

## Description

predicate: add `provider_disabled` / `provider_enabled` prompt-body Jinja filters over the existing Rust-backed provider-disable state, with tests and xprompt docs, so `%if(should_run=...)` can gate a segment on provider availability.

## Notes

[2026-09-21T01:28:25Z · sase-14t.1] provider_disabled/provider_enabled Jinja filters added with 16 passing tests in tests/test_xprompt_jinja_provider_filters.py, docs in docs/xprompt.md, sase tool run check exit 0, no epic-symbol leftovers

## Dependencies

- **Blocks:** [sase-14t.2](sase-14t.2.md) ✓ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-14t.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14t.1/README.md) | [sase-14t.1](sase-14t.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a34db56`](https://github.com/sase-org/sase/commit/a34db565b62246700733658a77937daffe5451f5) | feat(xprompt): add provider\_disabled/provider\_enabled Jinja filters | [sase-14t.1](sase-14t.1.md) | 2026-09-20 21:30:42 EDT |
