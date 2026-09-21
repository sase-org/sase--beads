# Bead: sase-157.10.1 — Make the CI toolchain-parse step portable to the macOS runner

[Bead Pages](../README.md) / [sase-157.10](sase-157.10.md) / sase-157.10.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-157.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-157.land.md) · **Assignee:** `sase-157.10.1` · **Size:** small
**Created:** 2026-09-21 12:36:17 EDT · **Closed:** 2026-09-21 12:50:11 EDT
**Plan:** [202609/macos\_ci\_leg\_green.md](https://github.com/sase-org/sase--plans/blob/main/202609/macos_ci_leg_green.md)

## Description

ci-toolchain-parse: replace the GNU-only grep/sed parsing of rust-toolchain.toml in the rust-checks job with a form BSD tools accept, and make sure scripts/check.sh runs under the macOS runner's bash.

## Notes

[2026-09-21T16:50:11Z · sase-157.10.1] ci.yml toolchain-parse now uses POSIX [[:space:]] (BSD-safe), fails loudly with ::error:: on bad parse; channel still resolves to stable on Linux (verified byte-identical), 10/10 parse checks pass, actionlint+YAML clean, check.sh audited bash-3.2-safe (no change), just check green on Linux. BSD-runner proof left to CI (no BSD sed available). No epic-symbol leftovers.

## Dependencies

- **Blocks:** [sase-157.10.2](sase-157.10.2.md) ◐ · ⧖ 2026-09-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-157.10.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-157.10.1/README.md) | [sase-157.10.1](sase-157.10.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@d48aaf3`](https://github.com/sase-org/sase-core/commit/d48aaf3e37582df010c8966c8b90a820f25b1530) | fix(ci): make toolchain-parse step portable to BSD sed/grep | [sase-157.10.1](sase-157.10.1.md) | 2026-09-21 12:51:55 EDT |
