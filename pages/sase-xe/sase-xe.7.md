# Bead: sase-xe.7 — Dispatch provider plugin hooks, built-in providers, and config schema

[Bead Pages](../README.md) / [sase-xe](README.md) / sase-xe.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0gq](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0gq.md) · **Assignee:** `sase-xe.7` · **Size:** large
**Created:** 2026-09-06 14:06:44 EDT · **Closed:** 2026-09-06 18:00:29 EDT
**Plan:** [202609/remote\_dispatch\_fleet.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_fleet.md)

## Description

dispatch-plugins: add the sase_dispatch entry-point group with dispatch_provider_spec, dispatch_discover, and dispatch_connection_plan hooks following the metadata-only finalizers loading model, built-in tailnet and https providers, the dispatch: config section with schema and layer-aware parsing, mode-restricted credential storage, and the remote_dispatch beta feature flag.

## Notes

[2026-09-06T22:00:29Z · sase-xe.7] Implemented dispatch provider hooks/config, built-in Tailnet/HTTPS providers, credential refs, runtime isolation, and schema/default packaging. Verified with .venv/bin/python -m pytest tests/dispatch/test_dispatch.py -q, just _lint-symvision, just install, and just check (diff-scoped lane escalated to the full suite and passed).

## Dependencies

- **Blocks:** [sase-xe.10](sase-xe.10.md) ◐ · ⧖ 2026-09-06
- **Depends on:** [sase-xe.2](sase-xe.2.md) ✓ · ⧖ 2026-09-06
- **Blocks:** [sase-xe.8](sase-xe.8.md) ◐ · ⧖ 2026-09-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xe.7.md) | [sase-xe.7](sase-xe.7.md) | 0 |
