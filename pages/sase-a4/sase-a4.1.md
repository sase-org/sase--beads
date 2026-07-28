# Bead: sase-a4.1 — Replace the blanket in-flight veto with job-level terminal-failure evidence

[Bead Pages](../README.md) / [sase-a4](README.md) / sase-a4.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-a4.1` · **Size:** medium
**Created:** 2026-07-27 18:01:27 UTC · **Closed:** 2026-07-27 18:18:05 UTC
**Plan:** [202607/ci\_watch\_liveness.md](https://github.com/sase-org/sase--plans/blob/main/202607/ci_watch_liveness.md)

## Description

red-liveness: classify on terminal job evidence with a supersession check, a sha-independent debounce persisted in the chop state dir, and a benign no_ci state, so busy repositories become observable without weakening fail-closed behavior.

## Dependencies

- **Blocks:** [sase-a4.2](sase-a4.2.md) ✓
