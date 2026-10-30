# Bead: sase-1q2.1 — sase recognizes complete sase-core releases with compressed macOS wheel tags

[Bead Pages](../README.md) / [sase-1q2](README.md) / sase-1q2.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.16e](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.16e.md) · **Assignee:** `sase-1q2.1` · **Size:** small
**Created:** 2026-10-30 12:37:06 EDT · **Closed:** 2026-10-30 13:46:14 EDT
**Plan:** [202610/v0\_19\_0\_release.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_19_0_release.md)

## Description

core-match: port sase-core's compressed-tag wheel matcher into tools/_release_core.py and tools/release_candidate, with tests on the live 0.43.0 and 0.43.1 macOS filenames.

## Notes

[2026-10-30T17:45:45Z · sase-1q2.1] PROPOSED FOLLOW-UP: tests/ace/tui/widgets/decks/test_files_anchor_ownership.py::test_trailing_reserve_remeasures_when_flag_already_enabled timed out in sase tool run d538cb4e15c5023c998f189c681462ac (wait_for after <dur>), then passed focused; unrelated to the core matcher. tui-reds / sase-1ou.6.1 already worked Files stall.

[2026-10-30T17:46:14Z · sase-1q2.1] Ported sase-core pypi_release_files.matches into tools/_release_core.py matches_suffix and tools/release_candidate completeness/wheel selection. Tests cover live 0.43.0 and 0.43.1 compressed macOS filenames, arm64-only, wrong version/project, exact sdist, and yanked compressed wheels. Local proof: python3 tools/ratchet_core_pin --check --fetch --ref origin/master exited 3 with CORE_LAG(pin=17e79c8cf5323d2ef4abcadef3bf95aa4e81c24b, newest_complete=0.43.1). just fix and sase tool run check b99ba3882fbaf2a8c457b2a3d5c6f18b passed. Noted sase-1oe.4 about the matcher fix. epic-symbols empty.

## Dependencies

- **Blocks:** [sase-1q2.2](sase-1q2.2.md) ✓ · ⧖ 2026-10-30
- **Blocks:** [sase-1q2.6](sase-1q2.6.md) ◐ · ⧖ 2026-10-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1q2.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1q2.1/README.md) | [sase-1q2.1](sase-1q2.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`deb8bb6`](https://github.com/sase-org/sase/commit/deb8bb60b6aa1a159324fb3491f2ec69eedbf945) | fix(release): match compressed macOS tags for core completeness | [sase-1q2.1](sase-1q2.1.md) | 2026-10-30 13:48:02 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1q2.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1q2.1/README.md

<!-- sase:referenced-by:end -->
