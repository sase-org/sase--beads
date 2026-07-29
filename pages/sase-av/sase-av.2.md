# Bead: sase-av.2 — Python artifact-reference facade and context resolution

[Bead Pages](../README.md) / [sase-av](README.md) / sase-av.2

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-av.2` · **Size:** medium
**Created:** 2026-07-29 16:45:57 UTC · **Closed:** 2026-07-29 17:50:33 UTC
**Plan:** [202607/artifact\_refs\_and\_prompt\_bar.md](https://github.com/sase-org/sase--plans/blob/main/202607/artifact_refs_and_prompt_bar.md)

## Description

ref-facade: add the Python facade that builds per-project resolution context (document roles and roots, chats root, artifact index, repos, projects), wraps the new bindings behind schema gates, renders canonical references from ACE entry targets and rows, and bumps the sase-core-rs floor.

## Notes

[2026-07-29T17:50:33Z · sase-av.2] Implemented the typed Python artifact-reference facade, per-project context assembly, schema-gated binding wrappers, ACE target/row reference rendering, archive-role preservation, core binding validation, and the sase-core-rs 0.12.12 floor/lock update. Verified published and installed sase-core-rs 0.12.12 exposes all six bindings; uv lock --check; 52 focused facade/version/Artifacts Plans tests; existing 35-test Plans interaction/filter/render suite; and COLUMNS=200 just check (23,747 tests, format, Ruff, mypy, Symvision, validation, and visual snapshots all passed).

[2026-07-29T17:51:19Z · sase-av.2] Verified just check; 52 focused facade/version tests; 35 existing Artifacts Plans tests; all six Rust bindings; uv lock --check; sase-core-rs v0.12.12 dependency and lock consistency.

## Dependencies

- **Depends on:** [sase-av.1](sase-av.1.md) ✓
- **Blocks:** [sase-av.3](sase-av.3.md) ✓
- **Blocks:** [sase-av.4](sase-av.4.md) ✓
- **Blocks:** [sase-av.5](sase-av.5.md) ✓
- **Blocks:** [sase-av.6](sase-av.6.md) ◐
- **Blocks:** [sase-av.7](sase-av.7.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-av.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-av.2/README.md) | [sase-av.2](sase-av.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`9988b61`](https://github.com/sase-org/sase/commit/9988b6161c9b47b3a657b49981fb11b1bf3e0c98) | feat(artifacts): add artifact reference facade | [sase-av.2](sase-av.2.md) | 2026-07-29 17:52:13 |
