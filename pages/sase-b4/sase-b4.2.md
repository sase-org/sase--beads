# Bead: sase-b4.2 — ACE prompt gating and the Ctrl+T reveal

[Bead Pages](../README.md) / [sase-b4](README.md) / sase-b4.2

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b4.2` · **Size:** medium
**Created:** 2026-07-30 11:15:08 UTC · **Closed:** 2026-07-30 11:46:22 UTC
**Plan:** [202607/at\_reference\_file\_row\_gate.md](https://github.com/sase-org/sase--plans/blob/main/202607/at_reference_file_row_gate.md)

## Description

tui-gate: thread the new menu option through the Python artifact-ref facade and prompt completion mixins, add a per-menu "files revealed" state that a first `Ctrl+T` press sets instead of force-completing, surface a `[^T] files` panel hint, and refresh the affected tests and docs.

## Notes

[2026-07-30T11:46:22Z · sase-b4.2] Implemented the Python artifact-ref options plumbing, per-menu suppressed/revealed state, two-stage Ctrl+T reveal, [^T] files panel hint, help/docs updates, and regression coverage. Verified 58 focused artifact-reference/rendering tests, the help contract test, full just test (24175 passed, 7 skipped), and just test-visual (392 passed, 1 skipped). just check passed Python/Markdown formatting, keep-sorted, Ruff, mypy, pyscripts, and changelog stages before stopping on pre-existing unrelated Symvision private-import violations in src/sase/ace/tui/actions/clipboard palette modules; this bead does not touch those files.

[2026-07-30T11:47:10Z · sase-b4.2] Implemented the Python artifact-ref options plumbing, sticky per-menu file reveal, two-stage Ctrl+T behavior, panel hint, documentation, and regression coverage. Verified 58 focused tests, full just test (24175 passed, 7 skipped), and just test-visual (392 passed, 1 skipped); just check reached Symvision and stopped only on pre-existing unrelated clipboard-palette violations.

## Dependencies

- **Depends on:** [sase-b4.1](sase-b4.1.md) ✓
- **Blocks:** [sase-b4.3](sase-b4.3.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-b4.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b4.2/README.md) | [sase-b4.2](sase-b4.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`9ba92b0`](https://github.com/sase-org/sase/commit/9ba92b09a7cacd192f59ccc0756970d8ca67526d) | feat(ace): gate artifact file completion rows | [sase-b4.2](sase-b4.2.md) | 2026-07-30 11:47:37 |
