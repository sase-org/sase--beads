# Bead: sase-1sb.2.1.4 — Enforce trust for local macro workflows and finish integration

[Bead Pages](../README.md) / [sase-1sb.2.1](sase-1sb.2.1.md) / sase-1sb.2.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1sb.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1sb.2.md) · **Assignee:** `sase-1sb.2.1.4` · **Size:** medium
**Created:** 2026-11-11 20:34:38 EST · **Closed:** 2026-11-12 05:13:10 EST
**Plan:** [202611/local\_config\_digest\_trust.md](https://github.com/sase-org/sase--plans/blob/main/202611/local_config_digest_trust.md)

## Description

macro-enforcement: Apply the shared policy to config macro sources and the
direct load_project_local_macros path, preserve provenance through parsing
and namespacing, and revalidate executable local definitions before their
bash/python steps run. Cover nested steps, references, inherited executable
definitions, revocation and content changes. Finish runtime diagnostics,
migration docs and the combined acceptance matrix. Run the required checks
and leave completion evidence for this child epic's land agent; do not close
sase-1sb.2 or any ancestor from a child phase.

## Notes

[2026-11-12T10:13:10Z · sase-1sb.2.1.4] Applied digest-pinned local-command trust to config and project-local macro loaders: untrusted executables are omitted, prompt-only still load, explicit blocked names raise LocalMacroTrustError rather than unknown/namesake, trusted config bash/python convert to workflows with retained descriptors, and bash/python steps revalidate. Nested parallel, sparse override, inherited use:, revoke, and content-change cases covered. 12 tests in test_config_local_trust_macro_enforcement.py passed; sase tool run check 0cc92bbe51275a2fb82cc59ce59ec010 green; no leftover --epic-symbol entries for this phase.

## Dependencies

- **Depends on:** [sase-1sb.2.1.3](sase-1sb.2.1.3.md) ✓ · ⧖ 2026-11-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1sb.2.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1sb.2.1.4/README.md) | [sase-1sb.2.1.4](sase-1sb.2.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ea41213`](https://github.com/sase-org/sase/commit/ea4121387b21bf727b021eb80e746a6054811ff4) | feat(config): enforce local-command trust for config macros | [sase-1sb.2.1.4](sase-1sb.2.1.4.md) | 2026-11-12 05:14:43 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1sb.2.1.4][1] | Need remaining notes, design, DECISIONS, and remaining work | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1sb.2.1.4/README.md

<!-- sase:referenced-by:end -->
