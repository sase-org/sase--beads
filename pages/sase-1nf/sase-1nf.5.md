# Bead: sase-1nf.5 — sase doctor survives unbound macro templates

[Bead Pages](../README.md) / [sase-1nf](README.md) / sase-1nf.5

**Status:** ○ open · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.12i](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.12i.md) · **Assignee:** `sase-1nf.5` · **Size:** small
**Created:** 2026-10-20 13:36:14 EDT
**Plan:** [202610/athena\_apollo\_audit\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/athena_apollo_audit_fixes.md)

## Description

doctor-macros: expand macros with raise_on_error in the model-macro check, skip parameterized macros explicitly while still reporting concrete broken presets, and make the diagnostics registry convert SystemExit into an ERROR check. Closes sase-1na.

## Notes

[2026-10-20T17:44:30Z · sase-1nf.5] PROPOSED FOLLOW-UP: Raw macro expansion in the doctor model-macro check still runs $(...) command substitutions in macro arguments even though the docs call this check read-only — scope or sandbox that

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nf.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.5/README.md) | [sase-1nf.5](sase-1nf.5.md) | 0 |
