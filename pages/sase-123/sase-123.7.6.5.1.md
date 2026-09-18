# Bead: sase-123.7.6.5.1 — Preserve arbitrary key text across both SSH shell boundaries

[Bead Pages](../README.md) / [sase-123.7.6.5](sase-123.7.6.5.md) / sase-123.7.6.5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-123.7.6.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-123.7.6.land.md) · **Assignee:** `sase-123.7.6.5.1` · **Size:** small
**Created:** 2026-09-18 02:08:33 EDT · **Closed:** 2026-09-18 02:23:38 EDT
**Plan:** [202609/remote\_send\_keys\_hint\_quoting.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_send_keys_hint_quoting.md)

## Description

shell-safe-key-template: repair the printed hint and prove apostrophes and other harmless shell metacharacters reach tmux as one exact argument.

## Notes

[2026-09-18T06:23:38Z · sase-123.7.6.5.1] Verified remote send-keys hint carries apostrophes and shell metacharacters through fake local SSH and remote shell as one tmux argument; ran just test tests/main/test_screenshot_remote_command.py -q, just test tests/main/test_screenshot_command.py tests/main/test_screenshot_launch_failures.py -q, just fix, just check, and epic-symbols showed no leftovers.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-123.7.6.5.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-123.7.6.5.1/README.md) | [sase-123.7.6.5.1](sase-123.7.6.5.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`99eb1ac`](https://github.com/sase-org/sase/commit/99eb1acc0ed9ef38c54dc7feec935be97468a2dc) | fix(screenshot): quote remote send-keys hint safely | [sase-123.7.6.5.1](sase-123.7.6.5.1.md) | 2026-09-18 02:25:15 EDT |
