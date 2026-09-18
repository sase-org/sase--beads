# Bead: sase-133.4 — sase screenshot text-input driving

[Bead Pages](../README.md) / [sase-133](README.md) / sase-133.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0na](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0na.md) · **Assignee:** `sase-133.4` · **Size:** medium
**Created:** 2026-09-18 16:38:01 EDT · **Closed:** 2026-09-18 17:39:13 EDT
**Plan:** [202609/remote\_dispatch\_agents\_tab\_parity.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_agents_tab_parity.md)

## Description

screenshot-text-input: add an ordered, repeatable --type option that sends literal text interleaved with -p presses and -w waits, forward it through the remote --host leg, and cover ordering and remote argv forwarding with tests, so query filters can be driven unattended.

## Notes

[2026-09-18T21:38:09Z · sase-133.4] PROPOSED FOLLOW-UP: Update tui_screenshot.md for --type — document repeatable -T/--type literal text (tmux send-keys -l) interleaved with -p/--press and -w/--wait-for in argv order, including `sase screenshot -p slash --type "machine:apollo" -p enter -w "17/17"` and remote --host forwarding; sase-12x is already a ready memory task for the same file (resvg runtime dependency) so land these together or after it.

[2026-09-18T21:38:35Z · sase-133.4] PROPOSED FOLLOW-UP: Symvision unused public ArtifactFileCache, MultiPrompt, TailCache — just check lint (symvision) fails on these independently of screenshot --type; they have no non-test cross-file importers (only in-file use, tests, and lazy string re-exports in sase.agent.__init__). Distinct from sase-10q (module.attr consumers). Make the classes private and drop unused package re-exports, or give them a real import-visible consumer.

[2026-09-18T21:39:13Z · sase-133.4] Added repeatable -T/--type that interleaves with -p/--press and -w/--wait-for in argv order (tmux send-keys -l -- TEXT). Forwarded through _remote_screenshot_argv; bumped screenshot contract schema to 2 so old remotes fail with the existing upgrade error. Parser, local send-keys order, and remote argv tests pass; just test-scoped 3519 passed. TUI ? help popup has no screenshot CLI surface. Memory note tui_screenshot.md left stale on purpose (PROPOSED FOLLOW-UP).

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-133.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-133.4/README.md) | [sase-133.4](sase-133.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`fa61906`](https://github.com/sase-org/sase/commit/fa61906da0978519d060f62eacd7417acaf02cb0) | feat(screenshot): add argv-ordered --type text driving | [sase-133.4](sase-133.4.md) | 2026-09-18 17:41:05 EDT |
