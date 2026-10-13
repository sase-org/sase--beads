# Bead: sase-1ko.1 — Provider channel and suppression spikes, with outcomes recorded on the epic

[Bead Pages](../README.md) / [sase-1ko](README.md) / sase-1ko.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.13.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.13.linker.w0.md) · **Assignee:** `sase-1ko.1` · **Size:** small
**Created:** 2026-10-13 18:10:34 EDT · **Closed:** 2026-10-13 18:23:46 EDT
**Plan:** [202610/e3\_explicit\_delivery\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202610/e3_explicit_delivery_cutover.md)

## Description

spikes: run cheap direct CLI probes for Claude native exclusion, auto-memory, and the system-prompt files; Codex project-doc suppression, fresh shadow state, and fork children; Muse without workspace trust; and Grok memory v2. Record each outcome and CLI version as a structured note on the epic bead.

## Notes

[2026-10-13T22:23:27Z · sase-1ko.1] PROPOSED FOLLOW-UP: Verify whether Codex local memories_1.sqlite created inside an allowlist shadow home is inactive under foreign_memory=yes; the live shadow probe found it as a regular local file, not a symlink, and the Codex phase should assert no foreign memory is read or written.

[2026-10-13T22:23:46Z · sase-1ko.1] Ran and recorded Claude, Codex, Muse, and Grok provider spikes with CLI versions and settings; attached sanitized evidence to the epic; recorded the Codex shadow memory database finding as a proposed follow-up; verified No --epic-symbol entries for sase-1ko.1. has no leftovers.

## Dependencies

- **Blocks:** [sase-1ko.7](sase-1ko.7.md) ◐ · ⧖ 2026-10-13
- **Blocks:** [sase-1ko.8](sase-1ko.8.md) ◐ · ⧖ 2026-10-13
- **Blocks:** [sase-1ko.9](sase-1ko.9.md) ◐ · ⧖ 2026-10-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1ko.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1ko.1/README.md) | [sase-1ko.1](sase-1ko.1.md) | 0 |
