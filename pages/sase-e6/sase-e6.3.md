# Bead: sase-e6.3 — Hosted URL resolution for xprompt definitions

[Bead Pages](../README.md) / [sase-e6](README.md) / sase-e6.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.athena.rs` · **Assignee:** `sase-e6.3` · **Size:** small
**Created:** 2026-08-02 13:22:41 UTC · **Closed:** 2026-08-02 15:16:44 UTC
**Plan:** [202608/stored\_prompt\_duality.md](https://github.com/sase-org/sase--plans/blob/main/202608/stored_prompt_duality.md)

## Description

links: add the resolver that turns one captured provenance record into a hosted blob URL with a line anchor, pinning the primary repository at the publication revision and returning nothing rather than guessing.

## Notes

[2026-08-02T15:16:31Z · sase-e6.3] PROPOSED FOLLOW-UP: `just check` fails at the "SASE validation" step (init repo --check) due to unrelated sidecar drift: sase/repos/plans/assets/plans-directory-map.png is 175.4 kB locally vs 1.3 MB expected. Confirmed pre-existing at master HEAD (reproduces with sase-e6.3 changes stashed), unrelated to xprompt work — needs `sase init repo` refresh or investigation into why the plans sidecar asset drifted.

[2026-08-02T15:16:44Z · sase-e6.3] Implemented XpromptTargetResolver + load_xprompt_source_records in src/sase/xprompt_links.py, resolving one captured xprompt provenance record to a hosted blob URL (with #L line anchor) pinned to the primary repo's publication revision, returning None on any unresolvable case (no hosted resolver, missing repo/relpath, disappeared root with no live fallback, non-hosted remote, unresolvable HEAD). Added epic-symbol symvision whitelisting for XpromptSourceRecord/XpromptTargetResolver/load_xprompt_source_records in Justfile. Verified: 9 new unit tests in tests/test_xprompt_links.py pass; ruff/mypy/symvision/toobig/keep-sorted lint all pass; full just test suite passes (25398 passed, 7 skipped). just check's SASE-validation step fails on unrelated pre-existing sidecar asset drift (confirmed reproducible on master HEAD without these changes) — logged as PROPOSED FOLLOW-UP on this bead.

## Dependencies

- **Depends on:** [sase-e6.1](sase-e6.1.md) ✓
- **Depends on:** [sase-e6.2](sase-e6.2.md) ✓
- **Blocks:** [sase-e6.4](sase-e6.4.md) ✓
- **Blocks:** [sase-e6.5](sase-e6.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-e6.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-e6.3/README.md) | [sase-e6.3](sase-e6.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| gh\_sase-org\_\_sase | [`e309358`](https://github.com/sase-org/sase/commit/e30935808ba50079c927c2c54130c4b155b9d0e1) | feat(xprompt): resolve hosted URLs for captured definition provenance | [sase-e6.3](sase-e6.3.md) | 2026-08-02 15:17:15 |
