# Bead: sase-p3.2 — Task-type spec validation, digest, and body rendering in Rust

[Bead Pages](../README.md) / [sase-p3](README.md) / sase-p3.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.05c](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.05c.md) · **Assignee:** `sase-p3.2` · **Size:** medium
**Created:** 2026-08-17 18:50:03 EDT · **Closed:** 2026-08-17 19:50:56 EDT
**Plan:** [202608/task\_bead\_types.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_bead_types.md)

## Description

core-type-spec: add the task-type spec wire, its validators, its stable digest, field-value validation, body-template rendering, and the committed snapshot format to sase-core.

## Notes

[2026-08-17T23:50:40Z · sase-p3.2] Landed in sase-core as 82b10b5e43da7a1828e97554ae4a1416f3946e74 (feat(task_type): add spec validation, digest, and body rendering).

[2026-08-17T23:50:56Z · sase-p3.2] Added TaskTypeSpecWire and TaskTypeFieldSpecWire at schema_version 1, reusing the scalar subset of PROPERTY_TYPES. Verified reserved slugs, 120/400 caps, single-cell glyphs, #RRGGBB accents, unique snake_case fields, role subsets, per-type validator keys, compiling regex patterns, and template-placeholder membership. Digest is a stable sha256 over the normalized spec. Field-value validation returns one typed error per missing/unknown/invalid problem. Body rendering substitutes {{ name }} and is empty without a template. Snapshot parse/serialize is deterministic (types sorted by slug, no package version). Python bindings expose validate_task_type_spec, task_type_spec_digest, validate_task_type_field_values, render_task_type_body, parse_task_type_snapshot, and serialize_task_type_snapshot. sase-core just check (fmt, clippy, cargo test --workspace including sase_core_py) passed. Landed on sase-core master as 82b10b5e43da7a1828e97554ae4a1416f3946e74.

## Dependencies

- **Depends on:** [sase-p3.1](sase-p3.1.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-p3.5](sase-p3.5.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p3.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p3.2/README.md) | [sase-p3.2](sase-p3.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@82b10b5`](https://github.com/sase-org/sase-core/commit/82b10b5e43da7a1828e97554ae4a1416f3946e74) | feat(task\_type): add spec validation, digest, and body rendering | [sase-p3.2](sase-p3.2.md) | 2026-08-17 19:47:28 EDT |
