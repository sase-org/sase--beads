# Bead: sase-18j.10.2 — Match possible owners on file identity, not on shared path tokens

[Bead Pages](../README.md) / [sase-18j.10](sase-18j.10.md) / sase-18j.10.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-18j.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-18j.land.md) · **Assignee:** `sase-18j.10.2` · **Size:** medium
**Created:** 2026-09-25 19:07:45 EDT · **Closed:** 2026-09-25 20:05:54 EDT
**Plan:** [202609/e3\_live\_triage\_repair.md](https://github.com/sase-org/sase--plans/blob/main/202609/e3_live_triage_repair.md)

## Description

core-owner-match: in sase-core only, replace the any-3-char-token substring owner match with a path-level match against a candidate's location plus a guarded file-name title match. Record what matched, and add the sase-191.3 probe as a regression fixture.

## Notes

[2026-09-26T00:02:13Z · sase-18j.10.2] Pin expectation for sase-18j.10.3: move sase-core-revision.txt to the sase-core commit that lands this phase (path-level owner matching in crates/sase_core/src/tool_run/triage/classify.rs). Parent of that commit is ed548d3e2 on master. Confirm it is reachable from origin/master after push. Owner matcher now uses location equality/directory-prefix plus guarded filename title match; possible_owners include matched_on; sase-191.3 probe (executor.py vs sase-106/sase-10a-shaped candidates) yields no owners. Unit tests owner_match* and classification_is_permutation_stable passed; clippy -p sase_core -D warnings passed; epic-symbols empty.

[2026-09-26T00:05:54Z · sase-18j.10.2] Verified: sase tool run check a6586250049f35f23282e2490ae7accb green (exit 0, 2m27s) in sase-core; verdict pass. Owner matcher is location equality/directory-prefix plus guarded filename title match with matched_on. sase-191.3 probe (executor.py vs sase-106/sase-10a-shaped candidates) yields no owners. Unit tests owner_match* and classification_is_permutation_stable passed. clippy -p sase_core -D warnings passed. epic-symbols empty. Pin expectation: sase-18j.10.3 moves sase-core-revision.txt to the commit that lands this phase (parent ed548d3e2).

## Dependencies

- **Blocks:** [sase-18j.10.3](sase-18j.10.3.md) ◐ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18j.10.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18j.10.2/README.md) | [sase-18j.10.2](sase-18j.10.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@9d049aa`](https://github.com/sase-org/sase-core/commit/9d049aac62ff173e41c9fec59734fcfc4af982d8) | fix(triage): match possible owners on file identity | [sase-18j.10.2](sase-18j.10.2.md) | 2026-09-25 20:07:17 EDT |
