# Bead: sase-1nf.5 — sase doctor survives unbound macro templates

[Bead Pages](../README.md) / [sase-1nf](README.md) / sase-1nf.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.12i](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.12i.md) · **Assignee:** `sase-1nf.5` · **Size:** small
**Created:** 2026-10-20 13:36:14 EDT · **Closed:** 2026-10-20 13:54:58 EDT
**Plan:** [202610/athena\_apollo\_audit\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/athena_apollo_audit_fixes.md)

## Description

doctor-macros: expand macros with raise_on_error in the model-macro check, skip parameterized macros explicitly while still reporting concrete broken presets, and make the diagnostics registry convert SystemExit into an ERROR check. Closes sase-1na.

## Notes

[2026-10-20T17:44:30Z · sase-1nf.5] PROPOSED FOLLOW-UP: Raw macro expansion in the doctor model-macro check still runs $(...) command substitutions in macro arguments even though the docs call this check read-only — scope or sandbox that

[2026-10-20T17:54:58Z · sase-1nf.5] doctor-macros done: raise_on_error expansion with parameterized skip counting plus SystemExit-to-ERROR registry guard; closed sase-1na; 6 new tests pass; sase tool run check green (all lint gates plus scoped lane); no epic-symbol leftovers;  follow-up recorded as PROPOSED FOLLOW-UP note

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nf.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.5/README.md) | [sase-1nf.5](sase-1nf.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d958a16`](https://github.com/sase-org/sase/commit/d958a168fc1b21fa68a8cc457f711b6680fb5dcc) | fix(doctor): survive unbound macro templates in model-macro check | [sase-1nf.5](sase-1nf.5.md) | 2026-10-20 13:56:12 EDT |
