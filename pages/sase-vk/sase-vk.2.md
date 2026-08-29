# Bead: sase-vk.2 — Tier-free H2 sections and the new Memory Webs section

[Bead Pages](../README.md) / [sase-vk](README.md) / sase-vk.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0g6.w0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0g6.w0.md) · **Assignee:** `sase-vk.2` · **Size:** medium
**Created:** 2026-08-29 11:29:35 EDT · **Closed:** 2026-08-29 13:29:38 EDT
**Plan:** [202608/memory\_webs\_agents\_section.md](https://github.com/sase-org/sase--plans/blob/main/202608/memory_webs_agents_section.md)

## Description

section: rename the generated H2 anchors to Core Memory / Memory Webs / Reference Memory, rename the AGENTS template variables, render web descriptors into the new middle section, and teach the AGENTS.md parser and TUI rail the three-group shape.

## Notes

[2026-08-29T17:29:38Z · sase-vk.2] Verified generated AGENTS.md is ## 1. Core Memory, ## 2. Memory Webs with ### 2.1 Decisions (decisions) / ### 2.2 Glossary Terms (glossary) / ### 2.3 Task Bead Types (task_types), and ## 3. Reference Memory; CLAUDE.md/GEMINI.md/QWEN.md/OPENCODE.md match byte-for-byte; webless home/chezmoi renders ## 1. Core Memory then ## 2. Reference Memory with no Memory Webs heading or gap; second-pass project sase memory init --check is clean; parser still recovers descriptions from legacy Tier headings; just check passed (full-suite escalation via core-identity-changed); just test-visual 842 passed, 1 skipped.

## Dependencies

- **Depends on:** [sase-vk.1](sase-vk.1.md) ✓ · ⧖ 2026-08-29
- **Blocks:** [sase-vk.3](sase-vk.3.md) ◐ · ⧖ 2026-08-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-vk.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-vk.2/README.md) | [sase-vk.2](sase-vk.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b726d0a`](https://github.com/sase-org/sase/commit/b726d0a18cf690c871b12b4bb56ef5d07652afeb) | feat(memory): give agent docs a Memory Webs section | [sase-vk.2](sase-vk.2.md) | 2026-08-29 13:30:53 EDT |
