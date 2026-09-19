# Bead: sase-11l.11.5.1 — Ratchet and verify the hold-deadlock core revision

[Bead Pages](../README.md) / [sase-11l.11.5](sase-11l.11.5.md) / sase-11l.11.5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11l.11.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11l.11.land.md) · **Assignee:** `sase-11l.11.5.1` · **Size:** small
**Created:** 2026-09-19 04:37:25 EDT · **Closed:** 2026-09-19 06:06:15 EDT
**Plan:** [202609/hold\_deadlock\_core\_pin.md](https://github.com/sase-org/sase--plans/blob/main/202609/hold_deadlock_core_pin.md)

## Description

source-pin: move SASE's source pin to a current core revision containing the deadlock binding and verify the pinned build.

## Notes

[2026-09-19T08:45:29Z · sase-11l.11.5.1] Ratcheted sase-core-revision.txt 8261449c5f30870604d369635f6214125e8da0f1 (v0.34.61) -> 093eb2dc296ebdd6568ebe809bd37a5d9e3d82a7 (v0.34.62). Core HEAD contains 0a7301ca435d (agent_hold_deadlock_reaches). pyproject.toml and uv.lock untouched. Install + hold-deadlock tests + just check next.

[2026-09-19T09:05:30Z · sase-11l.11.5.1--1] Re-ratcheted sase-core-revision.txt 093eb2dc296ebdd6568ebe809bd37a5d9e3d82a7 -> 44b82c3e392bb4642fbb909a2d656b8e94d2cadd after origin/master moved during just install. 44b82c3e392b is a descendant of 0a7301ca435d. pyproject.toml and uv.lock still untouched. Rebuild + hold-deadlock tests + just check next.

[2026-09-19T09:54:28Z · sase-11l.11.5.1--2] Re-ratcheted sase-core-revision.txt 44b82c3e392bb4642fbb909a2d656b8e94d2cadd -> 39602c950f8882d71dab1e3b74c17d2751e8b1cf (v0.34.63) after origin/master moved during just check. 39602c95 is a descendant of 0a7301ca435d. Fast-forwarded SASE workspace onto origin/master 9cfa200675 so artifact-ref tests expect reserved kind tool exported by the pinned core. pyproject.toml and uv.lock still untouched. Rebuild + hold-deadlock tests + just check next.

[2026-09-19T10:06:15Z · sase-11l.11.5.1--3] Verified pin 39602c950f8882d71dab1e3b74c17d2751e8b1cf (sase-core v0.34.63 HEAD, descendant of 0a7301ca435d); installed sase-core-rs 0.34.63 exposes agent_hold_deadlock_reaches; tests/test_run_agent_wait_slot_hold_deadlock.py 14 passed; tools/ratchet_core_revision --check exit 0; just check passed; pyproject.toml and uv.lock untouched.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11l.11.5.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11l.11.5.1.md) | [sase-11l.11.5.1](sase-11l.11.5.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0fc51c2`](https://github.com/sase-org/sase/commit/0fc51c29981ff59c742ae5261267a1acd9e2d2fb) | chore(core): ratchet hold-deadlock source pin | [sase-11l.11.5.1](sase-11l.11.5.1.md) | 2026-09-19 06:09:20 EDT |
