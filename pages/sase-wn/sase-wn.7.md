# Bead: sase-wn.7 — Stop multi-second idle re-renders of the prompt panel

[Bead Pages](../README.md) / [sase-wn](README.md) / sase-wn.7

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.o.f0` · **Assignee:** `sase-wn.7` · **Size:** medium
**Created:** 2026-09-04 12:11:12 EDT
**Plan:** [202609/sase\_idle\_cpu\_diet.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_idle_cpu_diet.md)

## Description

ace-idle-render-cache: make prompt-panel rendering (section-navigation strips/heights, lazy syntax highlighting, frontmatter lexing) cache-stable across refreshes of unchanged content, so an idle ace stops logging 1.5-4s main-thread stalls re-rendering the same document.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-wn.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-wn.7/README.md) | [sase-wn.7](sase-wn.7.md) | 0 |
