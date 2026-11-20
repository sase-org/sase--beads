# Bead: sase-1tz.3.1.9 — Compact oversize provider root bundles at compile time until they fit

[Bead Pages](../README.md) / [sase-1tz.3.1](sase-1tz.3.1.md) / sase-1tz.3.1.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.3.md) · **Assignee:** `sase-1tz.3.1.9` · **Size:** medium
**Created:** 2026-11-20 09:19:07 EST · **Closed:** 2026-11-20 11:20:44 EST
**Plan:** [202611/defects\_wire\_swap\_telegram\_bundles\_triage.md](https://github.com/sase-org/sase--plans/blob/main/202611/defects_wire_swap_telegram_bundles_triage.md)

## Description

bundle_trim: when a provider declares max_bytes and the delivered bundle would exceed it, compile applies a deterministic compaction ladder. Step one drops summaries from superseded list-roster entries. Step two compacts whole list rosters, largest first. Bundles that already fit stay byte-identical, and no memory file changes.

## Notes

[2026-11-20T16:19:47Z · sase-1tz.3.1.9] MEASUREMENT (bundle_trim, read-only, this workspace .venv, 2026-11-20). BEFORE: `sase instructions render -f provider=codex -j --no-cache` from bob-cli (external checkout d15432aa) = 36,225 bytes (proj.web.decisions 24,900; 75 strands, 31 superseded = 4 superseded + 27 superseded-in-part); sase codex = 22,099 bytes (sha 9624f715edcc); sase grok = 22,166 (f5786d615030); sase claude = 21,905 (823f6c2f3218). AFTER: bob-cli codex = 30,097 bytes (delivered ~30,192 <= 32,768), bundle.compaction = {step: superseded_summaries, uncompacted_bytes: 36225, max_bytes: 32768}, proj.web.decisions 24,900 -> 18,772; sase codex/grok/claude byte-identical (same shas). REPEAT AFTER INSTALL: `cd <bob-cli checkout> && sase instructions render -f provider=codex -j --no-cache | jq ".bundle | {bytes, compaction}"` (expect bytes <= ~32,670 and compaction.step superseded_summaries), plus `sase instructions render -f provider=codex -j --no-cache | jq ".bundle.compaction"` in sase (expect null). Live confirmation that bob-cli Codex launches deliver explicitly: their run manifests show delivery.status explicit with bundle.compaction set instead of fallback.reason oversize.

[2026-11-20T16:20:06Z · sase-1tz.3.1.9] HANDOFF FOR bundle_gate (sase-1tz.3.1.10): compile_bundle(..., max_bytes=N) runs the ladder; sase.llm_provider.instruction_delivery.provider_root_max_bytes(name) returns the explicit root cap with flag gating applied (None when the channel is disabled), and `sase instructions render` already passes it for actor sase_root/runtime. CompiledBundle.compaction / manifest bundle.compaction = {step, max_bytes, uncompacted_bytes} (absent when no step changed bytes); sections[].compaction = {step, uncompacted_length}. Steps: superseded_summaries, list_rosters (Rust CompactionStepWire in sase-core instruction_manifest, optional fields, deny_unknown_fields). When nothing fits, compile returns the most-compacted bundle and the launch still falls back oversize, so ERROR = delivered bytes (bundle + ~95-byte marker line) > max_bytes; the delivered-size helper is private (_delivered_bytes in sase.instructions.compaction) because symvision rejected a test-only public symbol, so re-publicize it once the doctor check calls it. Docs pages named in bundle_gate (instruction-bundles.md, instruction-bundle-internals.md, providers/codex.md:31-32) are untouched here and should also document the new manifest compaction fields.

[2026-11-20T16:20:16Z · sase-1tz.3.1.9] PROPOSED FOLLOW-UP: corroborate flake sase-1kr (git index-lock recovery under load) — `sase tool run check` 648244243dac escalated to the full lane (62,292 passed) and failed tests/test_git_lock_recovery_integration.py::test_git_checkout_with_lock_recovery and tests/llm_provider/test_commit_finalizer_auto_sdd_status.py::test_auto_commit_git_runner_recovers_stale_index_lock; both passed in isolation on the same tree; this phase does not touch git-lock recovery.

[2026-11-20T16:20:22Z · sase-1tz.3.1.9] PROPOSED FOLLOW-UP: tests/main/test_init_skills_formatting.py::test_handler_output_passes_prettier_check fails when run with bare pytest outside `just` on the clean base tree (prettier --check), but passed inside `sase tool run check`; likely a test-environment dependency on the just-provisioned prettier, not a product bug — triage whether it should skip or self-provision.

[2026-11-20T16:20:44Z · sase-1tz.3.1.9] Compile-time compaction ladder landed: compile_bundle(max_bytes=...) applies superseded_summaries then list_rosters (largest web first) only when the delivered text exceeds the provider cap; under-cap bundles stay byte-identical (sase codex/grok/claude shas unchanged; committed AGENTS.md parity passed). Step and uncompacted size are recorded in CompiledBundle/section table and the manifest via new optional sase-core wire fields (bundle.compaction, sections[].compaction) with invariants; cap is in the render-cache key. Boundary passes the explicit root cap; render resolves it per provider with flag gating unchanged. Verified: 18 new focused tests (roster styles; step a, step b largest-first, oversize core note still falls back, under-cap identical, Claude unaffected, cache, manifest, launches), sase-core `sase tool run check` green, sase `sase tool run check` lint/validation green and full lane 62,292 passed with 2 load flakes in the sase-1kr git-lock family (both pass in isolation). bob-cli Codex bundle 36,225 -> 30,097 bytes after step a.

## Dependencies

- **Blocks:** [sase-1tz.3.1.10](sase-1tz.3.1.10.md) ◐ · ⧖ 2026-11-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.3.1.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.9/README.md) | [sase-1tz.3.1.9](sase-1tz.3.1.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@142ed42`](https://github.com/sase-org/sase-core/commit/142ed4212dcb61b2b08a1f487d057681fae32c43) | feat(instruction\_manifest): record compile-time bundle compaction | [sase-1tz.3.1.9](sase-1tz.3.1.9.md) | 2026-11-20 11:22:05 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.3.1.9][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.9/README.md

<!-- sase:referenced-by:end -->
