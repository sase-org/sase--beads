# Bead: sase-14c.2 — Free echo-mint usage probe

[Bead Pages](../README.md) / [sase-14c](README.md) / sase-14c.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0o6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0o6.md) · **Assignee:** `sase-14c.2` · **Size:** medium
**Created:** 2026-09-20 12:41:10 EDT · **Closed:** 2026-09-20 14:40:12 EDT
**Plan:** [202609/muse\_usage\_windows.md](https://github.com/sase-org/sase--plans/blob/main/202609/muse_usage_windows.md)

## Description

collector: add the Python MSP probe that mints a Muse usage observation with no model call, wire the provider usage hooks, and move the pinned core revision and sase-core-rs floor forward so the new binding is guaranteed present.

## Notes

[2026-09-20T18:40:12Z · sase-14c.2] Added src/sase/llm_provider/usage/muse.py (collect_muse_usage): spawns 'muse serve --no-session-log --disable-shell' with MUSE_NO_AUTO_UPDATE=1 and runs the minimal MSP sequence (initialize, initialized notification, session/start providerId=echo with UUIDv7 commandId, turn/start, then polls usage/read every 250ms up to 8s or the probe deadline), and hands the usage/read result to the phase-1 binding provider_usage_normalize_muse_usage. Echo-session guard aborts to vendor_drift (muse_echo_session_guard_failed) before any turn/start when session.providerId != echo or modelId is not None; turn ack status/disposition is checked; schema fingerprint mismatch only warns. Status mapping: FileNotFoundError->not_installed, -32600/-32601/-32602->vendor_drift, other JSON-RPC errors and transport errors (incl. unsolicited_request)->probe_failed/timeout/parse_error, poll budget exhausted->core's authoritative-empty absence (never an error, never 0%). No logged-out mapping invented (shape never observed). Wired MuseProvider.llm_usage_capabilities ({probe: True, passive_events: False}) and llm_usage_probe (context.executable or _resolve_muse_executable, so SASE_MUSE_PATH is honoured). DECISION on the phase-1 follow-up: a poll-budget miss is knowingly accepted as the plan's authoritative-empty absence, so it clears stored Muse windows and can blank the header weekly indicator until the next tick (<=300s); mint lands 2.4-2.9s so the 8s budget makes this rare, and the alternative (error outcome) would trip collector health for logged-out hosts. Core floor: waited for sase-core release-plz v0.34.70 (contains the normalizer) to publish to PyPI, then 'just ratchet-core-window' moved pyproject sase-core-rs floor >=0.34.48 -> >=0.34.70 (upper bound kept, uv.lock refreshed) and 'just ratchet-core-revision' moved sase-core-revision.txt 39602c9 -> a4c4e65 (contains phase-1 commit 3cae8ef). Verified with tools/check_sase_core_rs_bindings in a clean venv: published 0.34.70 exposes all 677 required bindings; 0.34.69 fails on exactly provider_usage_normalize_muse_usage. Tests: new tests/llm_provider/test_muse_usage_probe.py (19 tests) against a scripted fake muse (tests/llm_provider/fixtures/usage_probe/muse_msp_cli.py) covering the happy echo-mint sequence and frame order, UUIDv7 ids, argv/env, over-100 percent preserved, never-minting host -> absence not error, malformed usage, the guard tests asserting NO turn/start frame is sent (mutation-checked: disabling the guard fails both), -32601 -> vendor_drift, missing executable, unsolicited request refusal, hang -> timeout, fingerprint drift warns and proceeds, SASE_MUSE_PATH resolution, capability dict, and a store test that 3 absent ticks keep collector health ok with no windows. Docs updated in docs/agent_providers.md (Muse subscription usage), docs/configuration.md and docs/llms.md; CHANGELOG untouched. Live: real Muse 1.3.0 via .venv/bin/sase usage refresh -p muse landed status=ok with session (Muse 5-hour session) and weekly (Muse weekly all models) windows, populated resets_at, source=probe, plan=None, ~3s, no model call; opaque tier id absent from ~/.sase/llm_provider_usage.json. NOTE the PATH 'sase' (uv tool install) is a released build without this hook and records muse as unsupported until updated. Verification honesty: 'sase tool run check' did NOT pass green. fmt, keep-sorted, ruff, mypy, feature flags, pyscripts, test waits, changelog, terminology all passed; lint (symvision) failed with 26 unused-public-symbol entries in sdd/_store_clone_*, ace/tui/models/_agent_runner_slot_capacity, service/host_* and completion/runtime_cache_generation - I reproduced the identical failure on a pristine HEAD worktree (tracked by sase-13s). Because check aborts at the first failure I then ran the remaining steps by hand: lint (toobig), just validate, just validate-committed-plans all exit 0; test-scoped escalated to the full suite (core-identity-changed, packaging-config): 43868 passed, 3 failed - test_capacity_gate_to_admission (2 tests, land queue_weight None vs 2.0, tracked by sase-13o/sase-13q) and test_lazy_tier2_reconcile_apply::test_changed_query_incomplete_load_after_reconcile_rearms (tracked by sase-13n); all 3 also fail identically on a pristine HEAD worktree, none touch this change. No epic symbols were left for this phase. Changes are uncommitted in the workspace for the host finalizer.

## Dependencies

- **Depends on:** [sase-14c.1](sase-14c.1.md) ✓ · ⧖ 2026-09-20
- **Blocks:** [sase-14c.3](sase-14c.3.md) ✓ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-14c.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14c.2/README.md) | [sase-14c.2](sase-14c.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6086402`](https://github.com/sase-org/sase/commit/608640272582a14cddb2d7c71a2e69af6ed36599) | feat(muse): collect subscription usage with a free echo-mint probe | [sase-14c.2](sase-14c.2.md) | 2026-09-20 15:11:40 EDT |
