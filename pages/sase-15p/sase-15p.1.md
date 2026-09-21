# Bead: sase-15p.1 — Rust normalizer and Gemini weekly anchor rule

[Bead Pages](../README.md) / [sase-15p](README.md) / sase-15p.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0os](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0os.md) · **Assignee:** `sase-15p.1` · **Size:** medium
**Created:** 2026-09-21 15:31:52 EDT · **Closed:** 2026-09-21 15:49:23 EDT
**Plan:** [202609/agy\_usage\_windows.md](https://github.com/sase-org/sase--plans/blob/main/202609/agy_usage_windows.md)

## Description

core-normalizer: in sase-core, add agy.rs to normalize the `agy -p /usage --output-format json` envelope into honest model_family-scoped windows with the hardening guards (omitted-zero TSV cross-check, turn-ran guard, logged-out envelope), add the narrow agy arm to is_weekly_all_window, export and bind provider_usage_normalize_agy_usage, and cover it with fixtures and tests.

## Notes

[2026-09-21T19:48:44Z · sase-15p.1] PROPOSED FOLLOW-UP: fourth provider allowlist arm in indicator.rs (agy/gemini-weekly) corroborates sase-14i declarative headline-window replacement

[2026-09-21T19:49:14Z · sase-15p.1] PROPOSED FOLLOW-UP: capture a real exhausted agy /usage payload (omitted remaining_fraction shape still unobserved) and add it as a fixture

[2026-09-21T19:49:23Z · sase-15p.1] agy.rs normalizer + gemini-weekly anchor arm landed in sase-core; ./scripts/check.sh all green (21 agy unit + 3 projection + py binding round-trip pass); epic-symbols clean; 2 PROPOSED FOLLOW-UP notes recorded

## Dependencies

- **Blocks:** [sase-15p.2](sase-15p.2.md) ✓ · ⧖ 2026-09-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-15p.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-15p.1/README.md) | [sase-15p.1](sase-15p.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@45a966c`](https://github.com/sase-org/sase-core/commit/45a966c64523f21a90959758317088869618b1ee) | feat(provider-usage): add agy usage normalizer and Gemini weekly anchor rule | [sase-15p.1](sase-15p.1.md) | 2026-09-21 15:50:37 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.24.cld][1] | research sase-core agent maintainability (non-split sase-core feature run evidence) | 1 |
| read-by | [agent:sase-15p.1][2] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.24.cld/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-15p.1/README.md

<!-- sase:referenced-by:end -->
