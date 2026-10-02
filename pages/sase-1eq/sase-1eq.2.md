# Bead: sase-1eq.2 — Durable data, core wires, and LSP build tooling

[Bead Pages](../README.md) / [sase-1eq](README.md) / sase-1eq.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0v4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0v4.md) · **Assignee:** `sase-1eq.2` · **Size:** medium
**Created:** 2026-10-02 06:51:22 EDT · **Closed:** 2026-10-02 18:15:56 EDT
**Plan:** [202610/xprompts\_to\_macros.md](https://github.com/sase-org/sase--plans/blob/main/202610/xprompts_to_macros.md)

## Description

sase-durable: pin core-expand and call the new bindings. Route every durable sase-written name through permanent legacy readers that have legacy-input tests. Make the LSP build and launch tooling work with either crate name.

## Notes

[2026-10-02T19:56:12Z · sase-1eq.2] recording pre-existing failure PROPOSED FOLLOW-UP: tests/test_vcs_xprompt_mru_pruning.py::test_load_launchable_prunes_provider_mismatched_prefix fails identically on the clean base tree (result drops #git:otherproj); unrelated to the durable rename, needs triage as a possible flake or environment issue -r

[2026-10-02T20:05:54Z · sase-1eq.2] contract-flip readiness audit for core-flip Contract-flip readiness (for core-flip): hard-fail risks audited — tools/validate_sase_core_rs asserts payload.get("xprompts") rows and writes xprompts.json fixtures (must accept macros key after flip); XPROMPT_SKILL_DEFINITION_WIRE_SCHEMA_VERSION strict ==1 in xprompt_skill_definition_facade.from_wire; content_layout wire requires schema>=5; tests/test_launch_proc_runtime.py:189 asserts xprompt_proc_origin()=="xprompt-proc" (core will emit prompt-proc); SASE_AGENT_LOCAL_XPROMPTS fallback in multi_prompt_xprompts.read/take_local_macros_path slated for removal at flip; SASE_LAUNCH_SWARM_XPROMPTS dual-write in used_xprompts.launch_swarm_env_entries likewise; agent_scan wire schema 10 / index 34 (xprompts_sig column rename goes through migration path, never TUI startup). LSP refresh command has no Python sender (docs/editor.md only); sase-nvim cutover owns switching to sase.macroLsp.refreshCatalog. -r

[2026-10-02T20:08:13Z · sase-1eq.2] recording second pre-existing failure PROPOSED FOLLOW-UP: tests/test_agent_restart_cli.py::test_wipe_failed_exits_1_and_prints_recovery_dir fails identically on the clean base tree (recovery dirname line-wrapped in stderr); unrelated to the durable rename -r

[2026-10-02T22:15:56Z · sase-1eq.2] sase-durable done and verified: pin ratcheted to core-expand 29da6fb7 with just install; new legacy_xprompt_names.py dual-readers; four new core bindings + new catalog option keys; writers emit macros.json/raw_prompt.md/submitted_prompt.md/prompt_proc/macro keys with legacy-input tests (tests/test_legacy_xprompt_names.py, 15 tests); SASE_MACRO_* env transport; macro-first LSP resolution; dual-crate build tooling in Justfile/wheel-cache/prebuild/workflows/setup-action with end-to-end sase-macro-lsp 0.36.3 build proof. sase tool run check f24dd1c6 green (all lint gates + full suite after scoped escalation, exit 0). Two failures reproduce identically on base (mru prune provider-mismatch, restart wipe_recovery wrap) recorded as PROPOSED FOLLOW-UP notes; contract-flip audit recorded as bead note.

## Dependencies

- **Depends on:** [sase-1eq.1](sase-1eq.1.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1eq.3](sase-1eq.3.md) ◐ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.2/README.md) | [sase-1eq.2](sase-1eq.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`72dbae6`](https://github.com/sase-org/sase/commit/72dbae6a094ae8ceb751db3bb1376326f182d69a) | feat(xprompt): add permanent dual readers for legacy xprompt names with macro-first writers | [sase-1eq.2](sase-1eq.2.md) | 2026-10-02 18:18:37 EDT |
