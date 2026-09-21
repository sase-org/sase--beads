# Bead: sase-157.10 — Make the required sase-core macOS CI leg actually run and pass

[Bead Pages](../README.md) / [sase-157](README.md) / sase-157.10

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-157.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-157.land.md) · **Assignee:** `sase-157.10.land`
**Created:** 2026-09-21 12:36:15 EDT · **Closed:** 2026-09-21 13:21:10 EDT
**Plan:** [202609/macos\_ci\_leg\_green.md](https://github.com/sase-org/sase--plans/blob/main/202609/macos_ci_leg_green.md)

## Description

The sase-core rust-checks macOS leg installs its toolchain, runs fmt, clippy, and the full test suite, and a master CI run is green on both ubuntu-latest and macos-latest with the macOS leg blocking.

## Notes

[2026-09-21T17:21:10Z · sase-157.10.land] Verified: sase-core d48aaf3 (sase-157.10.1) replaces GNU-only \s with POSIX [[:space:]] in ci.yml 'Read pinned toolchain' and fails loudly via ::error:: on empty/malformed channel; ci.yml matrix is [ubuntu-latest, macos-latest] with no continue-on-error, so macOS leg blocks. sase-157.10.2: master CI run 35628324928 (d48aaf3) green on all jobs incl. 'cargo fmt + clippy + test (macos-latest)'; release-plz PR 310 CI 35628421494 green; no macOS-only failures so no code change. Integration: commits since epic start are only d48aaf3 in sase-core and unrelated sase commits (0b30610471 bead read, af6b1f475c core-floor diag) - nothing to integrate. No PROPOSED FOLLOW-UP notes on children. No --epic-symbol entries.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-157.10.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-157.10.land/README.md) | [sase-157.10](sase-157.10.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase--plans | [`sase--plans@e091534`](https://github.com/sase-org/sase--plans/commit/e091534aab300d482dadb21bc029e5e284587f01) | chore(plans): mark macos\_ci\_leg\_green and macos\_portability plans done | [sase-157.10](sase-157.10.md) | 2026-09-21 13:28:54 EDT |
