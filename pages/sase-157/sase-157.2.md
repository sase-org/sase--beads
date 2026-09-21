# Bead: sase-157.2 — Let the verification gate run a filtered suite

[Bead Pages](../README.md) / [sase-157](README.md) / sase-157.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0oj](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0oj.md) · **Assignee:** `sase-157.2` · **Size:** xsmall
**Created:** 2026-09-21 06:25:44 EDT · **Closed:** 2026-09-21 07:04:35 EDT
**Plan:** [202609/macos\_portability.md](https://github.com/sase-org/sase--plans/blob/main/202609/macos_portability.md)

## Description

check-args: forward trailing arguments from scripts/check.sh and the justfile through to cargo test so a filtered or skipped run is possible without bypassing the documented gate.

## Notes

[2026-09-21T11:04:35Z · sase-157.2] check.sh test/clippy forward trailing args to cargo (explicit -p/--package/--workspace replaces default --workspace scope since cargo unions them); justfile test takes *args. Verified: check.sh test -p sase_core lists only sase_core targets, -- --skip run green, clippy -p sase_core clean, and full just check passes.

## Dependencies

- **Depends on:** [sase-157.1](sase-157.1.md) ✓ · ⧖ 2026-09-21
- **Blocks:** [sase-157.3](sase-157.3.md) ◐ · ⧖ 2026-09-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-157.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-157.2/README.md) | [sase-157.2](sase-157.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@5e8d315`](https://github.com/sase-org/sase-core/commit/5e8d3158b4562cfc23ca4998f059177d9029a010) | feat(sase-core): forward check.sh/justfile trailing args to cargo test/clippy | [sase-157.2](sase-157.2.md) | 2026-09-21 07:06:03 EDT |
