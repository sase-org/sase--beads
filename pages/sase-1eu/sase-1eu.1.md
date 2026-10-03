# Bead: sase-1eu.1 — Deliver the ctrl+shift chords through kitty and tmux

[Bead Pages](../README.md) / [sase-1eu](README.md) / sase-1eu.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ve](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ve.md) · **Assignee:** `sase-1eu.1` · **Size:** small
**Created:** 2026-10-02 11:33:51 EDT · **Closed:** 2026-10-02 11:52:38 EDT
**Plan:** [202610/three\_pane\_splits.md](https://github.com/sase-org/sase--plans/blob/main/202610/three_pane_splits.md)

## Description

terminal-chain: in the linked chezmoi repo, unmap kitty's ctrl+shift+f/b/o window maps and enable tmux CSI-u extended keys so ctrl+shift chords reach Textual, then record a manual verification checklist.

## Notes

[2026-10-02T15:50:17Z · sase-1eu.1] Manual verification checklist (run on the Mac in kitty, after chezmoi apply fires the reload hooks): 1) kitty: run kitty +kitten show_key -m kitty outside tmux, press ctrl+shift+f/b/o — each must arrive as a key event in the app, no kitty window action. 2) tmux: tmux show -s extended-keys prints on; inside tmux repeat show_key — expect CSI-u sequences carrying ctrl+shift modifiers (not bare ctrl keys). 3) End-to-end once Textual bindings land (later phases): ctrl+shift+f/b swap and ctrl+shift+d close work in the sase TUI under kitty->tmux.

[2026-10-02T15:52:38Z · sase-1eu.1] kitty: ctrl+shift+f/b/o mapped to no_op (verified config parses — no 'invalid config line' from kitty; negative control confirms kitty reports bad lines); tmux: extended-keys on + xterm-kitty:extkeys confirmed live on an isolated server; manual show_key checklist recorded as bead note

[2026-10-03T03:59:00Z · sase-1eu.land] Terminal-chain completion (land_three_pane_splits step 5): chezmoi tmux.conf now sets extended-keys-format csi-u alongside extended-keys on (kitty no_op maps unchanged). SASE adds TmuxModifyOtherKeysDriver (src/sase/tmux_driver.py) used by AceApp and SasePager via get_driver_class: writes ESC[>4;2m on entering app mode only when TMUX is set, writes ESC[>4;0m on leaving (exit and suspend via stop_application_mode), re-sent on resume via start. Headless/test drivers and non-tmux sessions untouched. Verified: private tmux 3.5a server accepts the new config (show-options reports extended-keys on + extended-keys-format csi-u); driver unit tests green (sequences only when TMUX set, reset on stop/suspend path). Manual checklist (requires chezmoi apply, NOT run): run chezmoi apply, then inside tmux inside kitty press ctrl+shift+f/b/d/o in ACE and the pager and confirm swap/close actions fire; confirm ctrl+f, j, >, Tab, shift+tab, Enter, Esc, Backspace, ctrl+space and f12 still behave; after app exit confirm shell receives legacy bytes. -r Record terminal-chain verification and manual checklist

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eu.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eu.1/README.md) | [sase-1eu.1](sase-1eu.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| chezmoi | [`chezmoi@78f0db4`](https://github.com/bbugyi200/dotfiles/commit/78f0db4e04b069e211c0c4f93c5780c7e4a2d64f) | feat(terminal): pass ctrl+shift chords through kitty and tmux | [sase-1eu.1](sase-1eu.1.md) | 2026-10-02 11:53:45 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1eu.1][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eu.1/README.md

<!-- sase:referenced-by:end -->
