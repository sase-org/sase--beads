# Bead: sase-s6.1 — Gated code directives and shared fenced-code contract

[Bead Pages](../README.md) / [sase-s6](README.md) / sase-s6.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0b8](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0b8.md) · **Assignee:** `sase-s6.1` · **Size:** medium
**Created:** 2026-08-22 14:14:57 EDT · **Closed:** 2026-08-22 15:20:49 EDT
**Plan:** [202608/typed\_launch\_units.md](https://github.com/sase-org/sase--plans/blob/main/202608/typed_launch_units.md)

## Description

launch-code-contract: create the typed_launch_units beta gate and one Rust-owned CodeValue, directive grammar, fence scanner, and code-input wire shared by runtime and editor surfaces.

## Notes

[2026-08-22T19:20:49Z · sase-s6.1] typed_launch_units beta flag (sase-s7) registered via sase flag new; Rust CodeValue, CommonMark fence scanner, and gated %if/%proc registry; Python consumes Rust-scanned owned fences; flag-off rejects %if/%proc with no model leakage; type:code internal/unadvertised; ACE/LSP hide gated names unless enabled; clippy + focused parser/flag tests pass; no leftover epic-symbols

## Dependencies

- **Blocks:** [sase-s6.2](sase-s6.2.md) ✓ · ⧖ 2026-08-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-s6.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-s6.1/README.md) | [sase-s6.1](sase-s6.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`316dd82`](https://github.com/sase-org/sase/commit/316dd8265f6ba79da9cac3099b19819858acde9e) | feat(xprompt): add gated typed\_launch\_units fenced-code contract | [sase-s6.1](sase-s6.1.md) | 2026-08-22 15:22:47 EDT |
| sase-core | [`sase-core@a38ec1a`](https://github.com/sase-org/sase-core/commit/a38ec1ab37fcce9f2fadaae4872467e1851902a6) | feat(editor): add CodeValue, fence scanner, and gated if/proc | [sase-s6.1](sase-s6.1.md) | 2026-08-22 15:24:36 EDT |
