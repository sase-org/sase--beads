# Bead: sase-1tz.3.1.1 — Add the prompt\_prose artifact-link origin and a host-origin binding contract test

[Bead Pages](../README.md) / [sase-1tz.3.1](sase-1tz.3.1.md) / sase-1tz.3.1.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.3.md) · **Assignee:** `sase-1tz.3.1.1` · **Size:** medium
**Created:** 2026-11-20 09:19:05 EST
**Plan:** [202611/defects\_wire\_swap\_telegram\_bundles\_triage.md](https://github.com/sase-org/sase--plans/blob/main/202611/defects_wire_swap_telegram_bundles_triage.md)

## Description

prose_wire: add PromptProse to sase-core's ArtifactLinkOriginWire with the automatic, commit-scoped semantics sase already relies on, and move the pin. Give sase one constant listing every host-produced origin, and round-trip each through sase_core_rs.artifact_link_validate_row in a contract test. Record what the "wire is stale" skew message means.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.3.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.1/README.md) | [sase-1tz.3.1.1](sase-1tz.3.1.1.md) | 0 |
