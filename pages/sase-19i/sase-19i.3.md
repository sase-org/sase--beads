# Bead: sase-19i.3 — Two-tier Node Finder preview

[Bead Pages](../README.md) / [sase-19i](README.md) / sase-19i.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0s5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0s5.md) · **Assignee:** `sase-19i.3` · **Size:** medium
**Created:** 2026-09-25 13:06:10 EDT · **Closed:** 2026-09-25 17:15:51 EDT
**Plan:** [202609/agents\_node\_finder.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_node_finder.md)

## Description

finder-preview: add the Tier 0 renderers, which do no I/O and paint on every highlight: kind chip, compact identity, breadcrumb, why-hidden and Enter-action lines, and kind-specific in-memory sections. Add the Tier 1 prompt-head and reply-tail loader. It is thread-only, never mutates live rows, and sits behind a modal-local LRU.

## Notes

[2026-09-25T21:12:19Z · sase-19i.3] PROPOSED FOLLOW-UP: Remove stale sase-18j Symvision exemptions for tool_run_triage_record and tool_run_triage_stage — check run 54630604655c2858488f51efff78aade confirms both already have real non-test consumers in src/sase/tool/executor.py and src/sase/tool/triage_stage.py; this is a clean-base failure unrelated to this phase.

[2026-09-25T21:15:51Z · sase-19i.3] Implemented the pure Tier 0 Node Finder preview, thread-only Tier 1 loader with copy-only hydration and 128-entry LRU, and focused coverage. Verified mypy plus 34 Node Finder tests. sase tool run check reached Symvision; the only remaining failure is the documented pre-existing stale sase-18j exemptions for tool_run_triage_record/stage, while all Node Finder exemptions are valid.

## Dependencies

- **Depends on:** [sase-19i.1](sase-19i.1.md) ✓ · ⧖ 2026-09-25
- **Blocks:** [sase-19i.4](sase-19i.4.md) ◐ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19i.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19i.3/README.md) | [sase-19i.3](sase-19i.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d62a459`](https://github.com/sase-org/sase/commit/d62a459a2d527d663cfd425104add367acee4f7e) | feat(tui): add Node Finder previews | [sase-19i.3](sase-19i.3.md) | 2026-09-25 17:17:23 EDT |
