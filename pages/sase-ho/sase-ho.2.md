# Bead: sase-ho.2 — Build the Python ref registry and sidecar configuration

[Bead Pages](../README.md) / [sase-ho](README.md) / sase-ho.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.vw](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.vw/README.md) · **Assignee:** `sase-ho.2` · **Size:** large
**Created:** 2026-08-08 13:32:55 EDT · **Closed:** 2026-08-08 16:57:33 EDT
**Plan:** [202608/artifact\_reference\_xprompts.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_reference_xprompts.md)

## Description

python-ref-registry: consume the new core contract, load `sase/refs`, synthesize sidecar ref xprompts, ship builtin renderers, and expose validated config and catalog metadata.

## Notes

[2026-08-08T18:47:27Z · sase-ho.2] PROPOSED FOLLOW-UP: publish the core artifact-reference contract before rerunning this phase — PyPI latest sase-core-rs is 0.20.1 at tag v0.20.1, while the required commit 4071bf0 (feat(core)!: add reference artifact contract) is only on linked core master; the installed 0.20.1 wheel lacks artifact_ref_context_wire_schema_version, artifact_ref_path_filter_wire_schema_version, artifact_ref_filter_path_payloads, and related schema-4/filter/ref APIs.

[2026-08-08T20:57:33Z · sase-ho.2] Implemented python_ref_registry_2: Python content layout refs/ref_sources wire parsing, sidecar ref policy config and doctor/schema validation, path-glob filtering through artifact ref context/core bindings, opt-in xprompt ref registry with packaged/file/plugin/sidecar renderer sources, ref metadata in show/catalog/mobile output, and LSP packaged/plugin ref environment wiring. Verified focused pytest coverage, tools/validate_sase_core_rs, just _lint-symvision, and just check. just check-full passed the full pytest lane and then failed only the known unrelated selection-health flake-baseline classifier issue on three historical bd/work_task nodes; routed through /sase_new_task as duplicate evidence on sase-hl and noted on sase-h8.

[2026-08-08T20:59:17Z · sase-ho.2] Implemented Python ref registry phase. Verification: focused pytest passed; tools/validate_sase_core_rs passed; just _lint-symvision passed; just check passed; just check-full full pytest passed, then failed only the known unrelated selection-health flake-baseline classifier issue on the three historical bd/work_task nodeids, routed to existing task sase-hl and epic sase-h8.

## Dependencies

- **Depends on:** [sase-ho.1](sase-ho.1.md) ✓ · ⧖ 2026-08-08
- **Blocks:** [sase-ho.3](sase-ho.3.md) ✓ · ⧖ 2026-08-08
- **Blocks:** [sase-ho.4](sase-ho.4.md) ◐ · ⧖ 2026-08-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ho.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ho.2.md) | [sase-ho.2](sase-ho.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e007352`](https://github.com/sase-org/sase/commit/e0073528f2055f39a9d634b7c3096563c50465ed) | feat: add Python ref registry | [sase-ho.2](sase-ho.2.md) | 2026-08-08 17:00:59 EDT |
