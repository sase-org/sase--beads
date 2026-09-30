# Bead: sase-1dq.6 — Mid-word autosuggest from the core word completion

[Bead Pages](../README.md) / [sase-1dq](README.md) / sase-1dq.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u0.md) · **Assignee:** `sase-1dq.6` · **Size:** medium
**Created:** 2026-09-30 16:38:28 EDT
**Plan:** [202609/next\_word\_autosuggest.md](https://github.com/sase-org/sase--plans/blob/main/202609/next_word_autosuggest.md)

## Description

midword-autosuggest: in auto mode, each typed word character requests complete_current_word. The UI composes suffix plus continuation as an inline ghost or peek, keeps silent on a core that lacks the field, filters deleted words, and guards keystroke latency with a measured synchronous-draft threshold and an off-pump deferred path.

## Dependencies

- **Depends on:** [sase-1dq.2](sase-1dq.2.md) ◐ · ⧖ 2026-09-30
- **Depends on:** [sase-1dq.5](sase-1dq.5.md) ◐ · ⧖ 2026-09-30
- **Blocks:** [sase-1dq.7](sase-1dq.7.md) ◐ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1dq.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1dq.6/README.md) | [sase-1dq.6](sase-1dq.6.md) | 0 |
