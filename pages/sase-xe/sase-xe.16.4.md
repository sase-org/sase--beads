# Bead: sase-xe.16.4 — Real builtin tailnet discovery with bounded probes and honest defaults

[Bead Pages](../README.md) / [sase-xe.16](sase-xe.16.md) / sase-xe.16.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08c](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08c.md) · **Assignee:** `sase-xe.16.4` · **Size:** medium
**Created:** 2026-09-08 10:21:35 EDT
**Plan:** [202609/remote\_dispatch\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_completion.md)

## Description

tailnet-discovery: implement `BuiltinDispatchProviders.dispatch_discover` for real. Run `tailscale status --json` without a shell under an enforced process deadline and output-size cap; parse the map-shaped Peer payload defensively (fixtures for missing/extra fields, self-exclusion, trailing-dot DNS, offline peers, missing CLI, malformed and oversized output); form default `https://<node-dns>` endpoints from validated MagicDNS names; probe candidates independently with per-peer and overall bounds, classifying compatibility from the public health response (its new `fleet` advertisement when present, `unknown` when absent, `incompatible` for unrelated services). Online state and OS are advisory hints with reasons, never exclusions. Return candidates plus structured diagnostics so a broken provider or absent binary never renders as an empty successful discovery, and stop swallowing provider exceptions silently. Enforce a real wall-clock bound on provider hook execution. Make the builtin@tailnet spec's supports_discovery claim true. Flip defaults: `builtin@tailnet.enabled: true` and `discovery.enabled_providers: [builtin@tailnet]`, honoring explicit disablement and explaining (not silently skipping) a disabled selection.

## Dependencies

- **Blocks:** [sase-xe.16.6](sase-xe.16.6.md) ◐ · ⧖ 2026-09-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.16.4/README.md) | [sase-xe.16.4](sase-xe.16.4.md) | 0 |
