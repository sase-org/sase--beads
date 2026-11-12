# Bead: sase-1sd.5 — Stop host completion from refusing checks that passed (sase-1qm)

[Bead Pages](../README.md) / [sase-1sd](README.md) / sase-1sd.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1bp](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1bp.md) · **Assignee:** `sase-1sd.5` · **Size:** large
**Created:** 2026-11-12 05:26:16 EST
**Plan:** [202611/next\_seven\_salvage\_and\_unstrand.md](https://github.com/sase-org/sase--plans/blob/main/202611/next_seven_salvage_and_unstrand.md)

## Description

fingerprint-refusal: prepared completions backed by a fully green just check are refused with stale_worktree_fingerprint even when every observed fingerprint matches on hand audit (5 refusals in October, 11 so far in November; fresh sase recurrences 11-07 and 11-10). Diff the sealed observation against the host-time observation for the fresh repro runs (suspect: cross-repo scope over main plus sase-core), fix the confirmed mechanism, and make every refusal record name which fingerprint component differed. Needs sase-core and sase changes.

## Dependencies

- **Depends on:** [sase-1sd.4](sase-1sd.4.md) ◐ · ⧖ 2026-11-12
- **Blocks:** [sase-1sd.6](sase-1sd.6.md) ◐ · ⧖ 2026-11-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1sd.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1sd.5/README.md) | [sase-1sd.5](sase-1sd.5.md) | 0 |
