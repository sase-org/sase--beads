# Bead: sase-1g6.3 — Listen-card banner and Play button in the Highlights PDF

[Bead Pages](../README.md) / [sase-1g6](README.md) / sase-1g6.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.0b.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.0b.linker.w0.md) · **Assignee:** `sase-1g6.3` · **Size:** small
**Created:** 2026-10-04 18:40:12 EDT · **Closed:** 2026-10-04 19:58:52 EDT
**Plan:** [202610/research\_swarm\_listen\_card.md](https://github.com/sase-org/sase--plans/blob/main/202610/research_swarm_listen_card.md)

## Description

bob-listen-banner: render `listen` Divs as a dependency-free LaTeX callout and, when create bound a companion, prepend a "▶ Play" button linking to a configurable `obsidian://open` URI for the vault copy.

## Notes

[2026-10-04T23:58:24Z · sase-1g6.3] PROPOSED FOLLOW-UP: fix the clean-base bob-cli clippy hard failure at tests/cli/capture/pomodoro_name.rs:808 (unconditional || true); the identical issue is recorded by prerequisite phase sase-1g6.2.

[2026-10-04T23:58:52Z · sase-1g6.3] Implemented the LaTeX listen-card banner and configurable encoded Obsidian Play URI; verified Pandoc filter tests, xelatex PDF output with /URI action, audio-link config parsing, 13 create CLI tests, formatting, and diff checks. just all reaches the pre-existing clippy failure at tests/cli/capture/pomodoro_name.rs:808; recorded as a proposed follow-up citing sase-1g6.2.

[2026-10-04T23:59:08Z · sase-1g6.3] Implemented the LaTeX listen-card banner and configurable encoded Obsidian Play URI; verified Pandoc filter tests, xelatex PDF output with /URI action, audio-link config parsing, 13 create CLI tests, formatting, and diff checks. just all reaches the pre-existing clippy failure at tests/cli/capture/pomodoro_name.rs:808; recorded as a proposed follow-up citing sase-1g6.2.

## Dependencies

- **Depends on:** [sase-1g6.2](sase-1g6.2.md) ✓ · ⧖ 2026-10-04
- **Blocks:** [sase-1g6.4](sase-1g6.4.md) ◐ · ⧖ 2026-10-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1g6.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1g6.3/README.md) | [sase-1g6.3](sase-1g6.3.md) | 0 |
