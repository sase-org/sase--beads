# Bead: sase-js.1 — Ref contract wire types in sase-core

[Bead Pages](../README.md) / [sase-js](README.md) / sase-js.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.y2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.y2/README.md) · **Assignee:** `sase-js.1` · **Size:** large
**Created:** 2026-08-11 13:21:00 EDT · **Closed:** 2026-08-11 15:15:24 EDT
**Plan:** [202608/artifact\_ref\_contract.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_ref_contract.md)

## Description

core: define the versioned provider/entry/resolution/use wire types, the closed expansion formatter, quoted-argument grammar, the `@stitch`/`@patch`/path-`@file` kinds with permanent legacy aliases, the shared numeric Markdown-link allocator, and the `Referenced By` footer block; release the binding.

## Notes

[2026-08-11T17:42:52Z · sase-js.1] PLAN HANDOFF: proposed tale plan "Ref contract wire types in sase-core" (size medium). Verified constraints that shaped it: (1) sase CI builds sase-core from master, so core must keep sase master green alone; (2) Python check_record_schema/_require_artifact_ref_schema hard-gate ONE constant for parse+scan+resolution wires, so ARTIFACT_REF_PARSE/RESOLUTION_WIRE_SCHEMA_VERSION 4->5 needs a lockstep 5-file bump in the sase repo; (3) Python allow-lists kind/payload/status strings, so new kinds need that bump and no new resolution status may be added (new kinds return the existing unknown_kind); (4) phase retire (sase-js.2) is editing artifact_ref_prompt_rendering.py, the ref xprompt surface, xprompt_catalog.rs and sase_xprompt_lsp concurrently. DECISION: the commit:->stitch: and plans:->plan: aliases ship as an explicit opt-in core API (parse_artifact_ref_canonical + kind registry) with the default parse_artifact_ref byte-identical; phase builtins (sase-js.4) flips the Python callers. DEVIATION: the parse payload is Patch{name} rather than Patch{project,name} because a Patch name has no reserved separator and a qualified spelling would not round-trip; project qualification lives on ArtifactEntryWire and in ambiguous-resolution candidates.

[2026-08-11T19:15:24Z · sase-js.1] Verified end to end: sase-core commit 3cc5af7 (feat(artifact-ref)!: add ref contract wire types, quoted arguments, link allocator, and Referenced By block) is on origin/master (local linked checkout is a fast-forwardable ancestor of origin/master a71794c). The rebuilt sase_core_rs extension in this workspace's .venv reports artifact_ref_wire_schema_version()==5 and exposes all 25 new bindings listed in plan §7 (verified via hasattr). This repo's coordinated 5-file bump (src/sase/artifact_ref_models.py, tools/validate_sase_core_rs, tests/test_validate_sase_core_rs_tool.py, tests/artifact_refs/test_parsing.py, tests/artifact_refs/test_lists.py) matches plan §7 exactly. Ran just check-full twice: first pass failed one test (tests/artifact_refs/test_parsing.py::test_record_schema_rejects_schema_one) on a stale ARTIFACT_REF_WIRE_SCHEMA_VERSION==4 sanity assertion at line 112 that plan §7 did not call out (it only named line 54) -- fixed to ==5. Second pass: every lint gate, SASE validation, committed-plans validation, and the full pytest test-cost lane passed clean (28946 passed, 10 skipped). The run's only remaining failure was the unrelated selection-health flake-baseline gate (test_contract_manifest.py + test_core_vcs_log.py nodes, none touched by this diff), which is pre-existing shared-host flake noise -- corroborated onto existing duplicate task sase-jq rather than filing new.

## Dependencies

- **Blocks:** [sase-js.3](sase-js.3.md) ◐ · ⧖ 2026-08-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-js.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-js.1.md) | [sase-js.1](sase-js.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@3cc5af7`](https://github.com/sase-org/sase-core/commit/3cc5af750182a7b54bb3b61dae6e2465794f0bf7) | feat(artifact-ref)!: add ref contract wire types, quoted arguments, link allocator, and Referenced By block | [sase-js.1](sase-js.1.md) | 2026-08-11 14:30:55 EDT |
| sase | [`cb453a5`](https://github.com/sase-org/sase/commit/cb453a529e483d4237afdfab66fd2be9e1caadeb) | feat(artifact-ref)!: bump wire schema to 5 for stitch/patch/file-path kinds | [sase-js.1](sase-js.1.md) | 2026-08-11 15:16:10 EDT |
