# Bead: sase-123.7.6.5 — Make the remote screenshot send-keys hint apostrophe-safe

[Bead Pages](../README.md) / [sase-123.7.6](sase-123.7.6.md) / sase-123.7.6.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-123.7.6.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-123.7.6.land.md) · **Assignee:** `sase-123.7.6.5.land`
**Created:** 2026-09-18 02:08:32 EDT · **Closed:** 2026-09-18 02:40:11 EDT
**Plan:** [202609/remote\_send\_keys\_hint\_quoting.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_send_keys_hint_quoting.md)

## Description

The printed remote send-keys hint carries an arbitrary single-line key through both the local and remote shells without syntax errors or argument splitting.

## Notes

[2026-09-18T06:40:11Z · sase-123.7.6.5.land] Verified the sole child phase sase-123.7.6.5.1 and its only note against commit 99eb1acc0e and the current source: remote_send_keys_hint now transports an ordinary shell-quoted single-line key over stdin, preserves the shell-quoted unique tmux target, and the two-shell fake-SSH test proves spaces, apostrophes, double quotes, dollar signs, pipes, and semicolons arrive as exactly one tmux argument without execution. Re-ran the focused remote screenshot tests (12 passed), the screenshot command lane (13 passed), and just check (including 66 scoped test files and Symvision). The epic and child contained no PROPOSED FOLLOW-UP entries. Git history since the epic began contains only its own implementation commit, so there was no post-start integration drift or duplicate/conflicting work to update. sase bead epic-symbols reported no entries.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-123.7.6.5.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-123.7.6.5.land.md) | [sase-123.7.6.5](sase-123.7.6.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase--plans | [`sase--plans@bddf6a9`](https://github.com/sase-org/sase--plans/commit/bddf6a980b2683562dcd1e4eff2dbe0ecddf2031) | docs(plans): mark screenshot epics done | [sase-123.7.6.5](sase-123.7.6.5.md) | 2026-09-18 03:39:39 EDT |
