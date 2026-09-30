# Bead: sase-1df.8 — Auto-open the Jinja menu while typing

[Bead Pages](../README.md) / [sase-1df](README.md) / sase-1df.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.3g](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.3g.md) · **Assignee:** `sase-1df.8` · **Size:** small
**Created:** 2026-09-30 08:47:31 EDT · **Closed:** 2026-09-30 15:04:52 EDT
**Plan:** [202609/jinja\_variable\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/jinja_variable_completion.md)

## Description

tui-auto: open the menu the moment `{{`/`{%` auto-pair, on `|` and `.` inside tags, and on identifier typing, behind a new ace.prompt_completion.auto_jinja_menu setting. Keep alternation `|` handling out of tags and document the behavior in docs/ace.md.

## Notes

[2026-09-30T19:04:52Z · sase-1df.8--1] tui-auto: auto_jinja_menu setting wired; menu auto-opens after {{/ {% pairing, on | and . and identifier typing; | guard keeps %{a | b} alternation; 10 pilot tests plus 253 neighbor tests green; monitored check failed only on prettier docs/ace.md (my new paragraph mis-wrapped, base tree clean) — fixed via prettier --write and full prettier check now green

## Dependencies

- **Depends on:** [sase-1df.7](sase-1df.7.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1df.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1df.8.md) | [sase-1df.8](sase-1df.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f3df35b`](https://github.com/sase-org/sase/commit/f3df35b79f58d6e9e537180e66d01f52846885d6) | feat(ace): add Jinja auto-menu prompt completion with pilot tests | [sase-1df.8](sase-1df.8.md) | 2026-09-30 15:07:39 EDT |
