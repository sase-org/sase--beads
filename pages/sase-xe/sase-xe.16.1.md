# Bead: sase-xe.16.1 — Package the gateway, bind bootstrap issuance, advertise fleet protocol

[Bead Pages](../README.md) / [sase-xe.16](sase-xe.16.md) / sase-xe.16.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08c](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08c.md) · **Assignee:** `sase-xe.16.1` · **Size:** large
**Created:** 2026-09-08 10:21:32 EDT · **Closed:** 2026-09-08 11:16:58 EDT
**Plan:** [202609/remote\_dispatch\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_completion.md)

## Description

core-fleet-surface: in sase-core, make a normally installed wheel a usable dispatch target. Extract the gateway binary's startup into a reusable `run_gateway_cli(args)` library function and export a `sase_gateway` console script from sase_core_py using the exact `sase_federation_worker` packaging pattern (Python shim, PyO3 `py.allow_threads` wrapper, registered pyfunction), with argument handling, Tokio lifecycle, and clean shutdown preserved. Add a narrow dict-in/dict-out PyO3 binding over `FleetCredentialStore::issue_bootstrap` that keeps the default 600-second single-use TTL, installation-pin, and scope semantics, and never logs or echoes the secret. Extend the public health response with a `fleet` object advertising `supported_protocol_versions` derived from `FLEET_PROTOCOL_VERSION`, derive the contract snapshot's `protocol_negotiation.supported_versions` from the same constant, regenerate both committed contract snapshots, and update every full-body health assertion. Installed-wheel smoke tests for both console scripts.

## Notes

[2026-09-08T15:16:58Z · sase-xe.16.1] Implemented gateway wheel packaging, local fleet bootstrap binding, and health protocol advertisement in sase-core; verified cargo test -p sase_gateway, cargo test -p sase_core_py, PYO3_PYTHON=/home/bryan/.local/bin/python3.13 ./scripts/check.sh, and maturin installed-wheel smoke for both console scripts.

## Dependencies

- **Blocks:** [sase-xe.16.2](sase-xe.16.2.md) ◐ · ⧖ 2026-09-08
- **Blocks:** [sase-xe.16.3](sase-xe.16.3.md) ◐ · ⧖ 2026-09-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xe.16.1.md) | [sase-xe.16.1](sase-xe.16.1.md) | 0 |
