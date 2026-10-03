# Bead: sase-1ex.10 — Explicit prompt-active state and one prompt-bar accessor

[Bead Pages](../README.md) / [sase-1ex](README.md) / sase-1ex.10

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vk](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vk.md) · **Assignee:** `sase-1ex.10` · **Size:** medium
**Created:** 2026-10-02 14:53:56 EDT
**Plan:** [202610/prompt\_space\_and\_project\_cycle\_latency.md](https://github.com/sase-org/sase--plans/blob/main/202610/prompt_space_and_project_cycle_latency.md)

## Description

prompt-active-state: track the active prompt bar explicitly on the app so `_prompt_input_active()` no longer queries the DOM. Route every `#prompt-input-bar` and `PromptInputBar` lookup through one accessor, which is the prerequisite for a hidden spare bar.

## Dependencies

- **Blocks:** [sase-1ex.11](sase-1ex.11.md) ◐ · ⧖ 2026-10-02
- **Depends on:** [sase-1ex.3](sase-1ex.3.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ex.10](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ex.10.md) | [sase-1ex.10](sase-1ex.10.md) | 0 |
