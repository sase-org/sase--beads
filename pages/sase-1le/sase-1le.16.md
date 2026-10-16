# Bead: sase-1le.16 — Generated CLI reference

[Bead Pages](../README.md) / [sase-1le](README.md) / sase-1le.16

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.4l.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.4l.linker.w0.md) · **Assignee:** `sase-1le.16` · **Size:** medium
**Created:** 2026-10-15 18:11:13 EDT · **Closed:** 2026-10-15 22:07:50 EDT
**Plan:** [202610/sase\_sh\_docs\_redesign.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_sh_docs_redesign.md)

## Description

cli-registry: generate one reference page per command group from the argparse tree and replace cli.md's hand-written tables with links.

## Notes

[2026-10-16T02:07:34Z · sase-1le.16] PROPOSED FOLLOW-UP: format-only drift in docs/reference/glossary.md and design-decisions.md reproduces identically on clean HEAD (a1dd710acd); prettier reflow vs raw render output, blocks just check fmt-docs-check for unrelated agents

[2026-10-16T02:07:50Z · sase-1le.16] cli-registry done: tools/render_cli (sase-only source) generates docs/reference/cli/<66 groups>.md + index.md from argparse; cli.md tables replaced with links (ceiling 14508->6927); nav + reference hub + maps updated. Verified: render_cli --check ok, docs-gen-check ok, check_docs ok, 41 related tests pass, just docs-check strict build + 264-URL contract green. Full just check still red on pre-existing glossary/design-decisions format drift proven identical on clean HEAD; recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Blocks:** [sase-1le.20](sase-1le.20.md) ◐ · ⧖ 2026-10-15
- **Depends on:** [sase-1le.8](sase-1le.8.md) ✓ · ⧖ 2026-10-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1le.16](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.16/README.md) | [sase-1le.16](sase-1le.16.md) | 0 |
