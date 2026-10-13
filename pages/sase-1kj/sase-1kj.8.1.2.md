# Bead: sase-1kj.8.1.2 — Build the shared Rust artifact-link index and opaque binding

[Bead Pages](../README.md) / [sase-1kj.8.1](sase-1kj.8.1.md) / sase-1kj.8.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1kj.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1kj.8.md) · **Assignee:** `sase-1kj.8.1.2` · **Size:** medium
**Created:** 2026-10-13 17:50:21 EDT · **Closed:** 2026-10-13 19:15:09 EDT
**Plan:** [202610/artifact\_link\_inverted\_index.md](https://github.com/sase-org/sase--plans/blob/main/202610/artifact_link_inverted_index.md)

## Description

native-index: implement the immutable core index, indexed row and projection queries, and GIL-releasing opaque Python handle against the captured parity fixtures.

## Notes

[2026-10-13T23:15:09Z · sase-1kj.8.1.2] Native immutable artifact-link index in sase_core::artifact_link::index with GIL-releasing PyO3 handle. Bindings: ArtifactLinkIndexHandle, artifact_link_index_build, artifact_link_index_chips, artifact_link_index_target, artifact_link_index_rows, artifact_link_index_project, artifact_link_index_wire_schema_version. Verified: 13 sase_core tests (full parity fixture chip/target pin, first-wins/max-uses, alias collision, self-edge/projected writable, first-row patch projection, empty keys, malformed rows, missing vs non-selectable, neighbor_target row-project, 200-noise no-scan candidate_row_count=2, concurrent frozen reads); 2 sase_core_py round-trip tests including conversion-cost; just fmt; clippy -D warnings; sase tool run check 21d0be48247dbea0ab2d0172d7759a95 succeeded in 486588ms. TUI consumers and sase-core-revision.txt ratchet belong to sase-1kj.8.1.3. No --epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-1kj.8.1.1](sase-1kj.8.1.1.md) ✓ · ⧖ 2026-10-13
- **Blocks:** [sase-1kj.8.1.3](sase-1kj.8.1.3.md) ◐ · ⧖ 2026-10-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1kj.8.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1kj.8.1.2/README.md) | [sase-1kj.8.1.2](sase-1kj.8.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@daad8f2`](https://github.com/sase-org/sase-core/commit/daad8f261cb09c1553fca5b3a531ee61e12977e9) | feat(artifact\_link): add immutable inverted index and PyO3 handle | [sase-1kj.8.1.2](sase-1kj.8.1.2.md) | 2026-10-13 19:16:43 EDT |
