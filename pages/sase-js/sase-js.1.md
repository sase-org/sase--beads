# Bead: sase-js.1 — Ref contract wire types in sase-core

[Bead Pages](../README.md) / [sase-js](README.md) / sase-js.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.y2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.y2/README.md) · **Assignee:** `sase-js.1` · **Size:** large
**Created:** 2026-08-11 13:21:00 EDT
**Plan:** [202608/artifact\_ref\_contract.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_ref_contract.md)

## Description

core: define the versioned provider/entry/resolution/use wire types, the closed expansion formatter, quoted-argument grammar, the `@stitch`/`@patch`/path-`@file` kinds with permanent legacy aliases, the shared numeric Markdown-link allocator, and the `Referenced By` footer block; release the binding.

## Notes

[2026-08-11T17:42:52Z · sase-js.1] PLAN HANDOFF: proposed tale plan "Ref contract wire types in sase-core" (size medium). Verified constraints that shaped it: (1) sase CI builds sase-core from master, so core must keep sase master green alone; (2) Python check_record_schema/_require_artifact_ref_schema hard-gate ONE constant for parse+scan+resolution wires, so ARTIFACT_REF_PARSE/RESOLUTION_WIRE_SCHEMA_VERSION 4->5 needs a lockstep 5-file bump in the sase repo; (3) Python allow-lists kind/payload/status strings, so new kinds need that bump and no new resolution status may be added (new kinds return the existing unknown_kind); (4) phase retire (sase-js.2) is editing artifact_ref_prompt_rendering.py, the ref xprompt surface, xprompt_catalog.rs and sase_xprompt_lsp concurrently. DECISION: the commit:->stitch: and plans:->plan: aliases ship as an explicit opt-in core API (parse_artifact_ref_canonical + kind registry) with the default parse_artifact_ref byte-identical; phase builtins (sase-js.4) flips the Python callers. DEVIATION: the parse payload is Patch{name} rather than Patch{project,name} because a Patch name has no reserved separator and a qualified spelling would not round-trip; project qualification lives on ArtifactEntryWire and in ambiguous-resolution candidates.

## Dependencies

- **Blocks:** [sase-js.3](sase-js.3.md) ◐ · ⧖ 2026-08-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-js.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-js.1.md) | [sase-js.1](sase-js.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@3cc5af7`](https://github.com/sase-org/sase-core/commit/3cc5af750182a7b54bb3b61dae6e2465794f0bf7) | feat(artifact-ref)!: add ref contract wire types, quoted arguments, link allocator, and Referenced By block | [sase-js.1](sase-js.1.md) | 2026-08-11 14:30:55 EDT |
