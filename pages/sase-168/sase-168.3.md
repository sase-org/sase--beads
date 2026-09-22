# Bead: sase-168.3 — Install on athena, dismiss the 8 rows, and verify

[Bead Pages](../README.md) / [sase-168](README.md) / sase-168.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pa](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pa.md) · **Assignee:** `sase-168.3` · **Size:** small
**Created:** 2026-09-22 10:05:59 EDT · **Closed:** 2026-09-22 11:08:47 EDT
**Plan:** [202609/remote\_attention\_dismissal\_fix.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_attention_dismissal_fix.md)

## Description

deploy-dismiss-verify: run sase update -y, restart pre-update TUIs through their Quit/Restart panel, dismiss the remote-attention rows, confirm they stay dismissed, and verify via sase screenshot that ?8 is gone.

## Notes

[2026-09-22T15:07:17Z · sase-168.3] PROPOSED FOLLOW-UP: follow inventory next_cursor per host so hosts with >100 pending requests are fully mirrored

[2026-09-22T15:07:47Z · sase-168.3] PROPOSED FOLLOW-UP: after a failed network read, federation worker cache-only reads still report status ok — they should carry the stale status and error like the network path does

[2026-09-22T15:08:47Z · sase-168.3] Installed sase 0.17.1+1137.g7c763a2e7 + sase-core-rs +2.g19ee7a09f via sase update -y; marker present. Restarted pre-update TUI sase:5.1 via Quit panel (r); header confirms new build. Dismissed all 8 apollo RemoteAttention rows; after 120s sleep all 8 still dismissed=true, 0 visible remote-attention rows. Fresh screenshot /tmp/remote_attention_after.png shows no ? chip; user TUI top bar shows #2 w1 with no ?8. epic-symbols clean.

## Dependencies

- **Depends on:** [sase-168.1](sase-168.1.md) ✓ · ⧖ 2026-09-22
- **Depends on:** [sase-168.2](sase-168.2.md) ✓ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-168.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-168.3/README.md) | [sase-168.3](sase-168.3.md) | 0 |
