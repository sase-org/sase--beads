# Bead: sase-1df.2 — Rust Jinja tag scanner, slot classifier, and scope analysis

[Bead Pages](../README.md) / [sase-1df](README.md) / sase-1df.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.3g](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.3g.md) · **Assignee:** `sase-1df.2` · **Size:** medium
**Created:** 2026-09-30 08:47:17 EDT
**Plan:** [202609/jinja\_variable\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/jinja_variable_completion.md)

## Description

scan: find the Jinja tag at the cursor (respecting literal zones, comments, raw blocks, frontmatter, and string literals), classify the completion slot, and extract the document scope: declared inputs, skill flag, %repeat/%wait directives, and position-aware template locals with the open-block stack.

## Dependencies

- **Blocks:** [sase-1df.3](sase-1df.3.md) ◐ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1df.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1df.2/README.md) | [sase-1df.2](sase-1df.2.md) | 0 |
