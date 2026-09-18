# Bead: sase-11l.10 — Remove the agent\_holds flag and close out

[Bead Pages](../README.md) / [sase-11l](README.md) / sase-11l.10

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ls](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ls.md) · **Assignee:** `sase-11l.10` · **Size:** small
**Created:** 2026-09-15 22:46:07 EDT · **Closed:** 2026-09-18 15:19:23 EDT
**Plan:** [202609/hold\_directive.md](https://github.com/sase-org/sase--plans/blob/main/202609/hold_directive.md)

## Description

hold-flag-removal: delete the agent_holds Off branch, make %hold unconditional, close the flag bead, run the full landing gate, and propose the memory-documentation follow-up.

## Notes

[2026-09-18T14:36:52Z · sase-11l.10] PROPOSED FOLLOW-UP: memory — document %hold and %queue-on-procs in sase/memory/xprompts.md (directive table row, queue-on-proc note, hold semantics one-liner) and record the hold-store design (pull-model, fail-open, TTL, family-scoped release) as a decisions web strand.

[2026-09-18T19:19:23Z · sase-11l.10--5] just check-full (cydmxpd7nhjz) passed lint and test-cost after closing flag bead sase-11u, regenerating cli_spec.json, and recalibrating test-cost CPU budgets, then failed flake-baseline on 3 historical nodes. Snapshot drift retired via updated fixed-at after just sync-completion-spec; jsonline descendant cleanup now treats zombies as dead and waits for reap. just selection-health --fail-on-new-flake passed; just check passed (escalated to full suite); check_feature_flags passed; epic-symbols reported no leftovers.

## Dependencies

- **Depends on:** [sase-11l.5](sase-11l.5.md) ✓ · ⧖ 2026-09-15
- **Depends on:** [sase-11l.6](sase-11l.6.md) ✓ · ⧖ 2026-09-15
- **Depends on:** [sase-11l.7](sase-11l.7.md) ✓ · ⧖ 2026-09-15
- **Depends on:** [sase-11l.8](sase-11l.8.md) ✓ · ⧖ 2026-09-15
- **Depends on:** [sase-11l.9](sase-11l.9.md) ✓ · ⧖ 2026-09-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11l.10](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11l.10.md) | [sase-11l.10](sase-11l.10.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`932e6ff`](https://github.com/sase-org/sase/commit/932e6ffae232e38ecd0f72b3ee18bed3e0f6bf24) | feat(hold): make %hold unconditional and retire agent\_holds | [sase-11l.10](sase-11l.10.md) | 2026-09-18 16:24:14 EDT |
