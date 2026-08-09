# Bead: sase-i3.1 — Derive plurals and display aliases in the Rust glossary domain

[Bead Pages](../README.md) / [sase-i3](README.md) / sase-i3.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wa.f0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wa.f0/README.md) · **Assignee:** `sase-i3.1` · **Size:** medium
**Created:** 2026-08-09 08:17:43 EDT · **Closed:** 2026-08-09 08:29:32 EDT
**Plan:** [202608/glossary\_alias\_plurals.md](https://github.com/sase-org/sase--plans/blob/main/202608/glossary_alias_plurals.md)

## Description

core: add phrase pluralization to sase-core, split authored / effective / display alias lists, and expose the new display list on the glossary wire.

## Notes

[2026-08-09T12:29:32Z · sase-i3.1] Implemented Rust glossary plural derivation, display_aliases wire field, effective/display alias splitting, and regression tests in sase-core; verified cargo test --workspace glossary, just rust-fmt, and just rust-check.

## Dependencies

- **Blocks:** [sase-i3.2](sase-i3.2.md) ✓ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-i3.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-i3.1/README.md) | [sase-i3.1](sase-i3.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@5c555dc`](https://github.com/sase-org/sase-core/commit/5c555dcda69367e31b64edc57d487f0b4a464b5c) | feat(glossary): derive plural aliases for matching | [sase-i3.1](sase-i3.1.md) | 2026-08-09 08:31:38 EDT |
