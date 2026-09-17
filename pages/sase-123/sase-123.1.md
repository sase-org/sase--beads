# Bead: sase-123.1 — Promote the canonical rasterizer out of tests/

[Bead Pages](../README.md) / [sase-123](README.md) / sase-123.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0m5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0m5.md) · **Assignee:** `sase-123.1` · **Size:** small
**Created:** 2026-09-17 08:43:28 EDT · **Closed:** 2026-09-17 09:54:00 EDT
**Plan:** [202609/tui\_agent\_screenshots.md](https://github.com/sase-org/sase--plans/blob/main/202609/tui_agent_screenshots.md)

## Description

visual-render-promotion: move render_svg_to_png and the bundled fonts from tests/ace/tui/visual/ into a runtime src/sase module with lazy resvg/pillow imports, repoint the visual suite at it, and verify goldens stay byte-identical.

## Notes

[2026-09-17T13:53:31Z · sase-123.1] PROPOSED FOLLOW-UP: investigate current visual golden drift — `just test-visual` fails broadly in this workspace, and rendering a representative failing SVG with the committed pre-move rasterizer arguments also matches the new actual PNG rather than the committed golden, indicating an ambient renderer/UI drift rather than this promotion.

[2026-09-17T13:54:00Z · sase-123.1] Promoted render_svg_to_png and bundled fonts into src/sase/ace/tui, repointed visual helpers/fingerprints/audits, verified focused visual renderer tests pass, wheel contains the runtime fonts, just check passes, and confirmed no epic-symbol entries remain for sase-123.1. just test-visual still fails broadly in this workspace from ambient golden drift reproducible with the pre-move renderer arguments, recorded as a proposed follow-up.

## Dependencies

- **Blocks:** [sase-123.3](sase-123.3.md) ✓ · ⧖ 2026-09-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-123.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-123.1/README.md) | [sase-123.1](sase-123.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7aef336`](https://github.com/sase-org/sase/commit/7aef3364e22929aba2bc495306313ff17189c549) | feat(tui): promote visual rasterizer | [sase-123.1](sase-123.1.md) | 2026-09-17 09:55:49 EDT |
