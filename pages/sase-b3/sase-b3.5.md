# Bead: sase-b3.5 — Server-side fuzzy completion for editors

[Bead Pages](../README.md) / [sase-b3](README.md) / sase-b3.5

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b3.5` · **Size:** small
**Created:** 2026-07-30 08:18:31 UTC · **Closed:** 2026-07-30 08:54:42 UTC
**Plan:** [202607/fuzzy\_artifact\_ref\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202607/fuzzy_artifact_ref_completion.md)

## Description

lsp: return an incomplete list with filter text equal to the typed reference so clients keep server-ranked fuzzy rows, and put the matched runs and title into item documentation and label details.

## Notes

[2026-07-30T08:55:45Z · sase-b3.5] LSP @-reference completion now returns CompletionList{isIncomplete:true} with every item's filterText set to the typed reference (@kind:query / @query), sortText-ranked by the shared core matcher; documentation previews the payload with matched runs bolded plus the title, labelDetails.detail carries the title (suppressed when it just echoes the payload). Also dropped the starts_with prefilter from the document/chat and bead payload collectors (already query-independently bounded by bounded_relative_files) so fuzzy rows can reach editors at all. Verified: new server test proves @designs:site surfaces a bundled 202607/<bundle>/*.md row with correct filterText/newText/bolding, two lsp_convert unit tests cover payload+kind stages; cargo fmt --check, cargo clippy --workspace --all-targets -D warnings, and cargo test --workspace (all green). Committed and pushed as 374cfc3.

## Dependencies

- **Depends on:** [sase-b3.3](sase-b3.3.md) ✓
- **Blocks:** [sase-b3.9](sase-b3.9.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| bbugyi200.athena.sase-b3.5 | [sase-b3.5](sase-b3.5.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`374cfc3`](https://github.com/sase-org/sase-core/commit/374cfc37ede51b4b0f41dd0ce2e796597b1dbc97) | feat(lsp): serve server-ranked fuzzy artifact references | [sase-b3.5](sase-b3.5.md) | 2026-07-30 08:54:49 |
