# Bead: sase-11l.1 — Allow %queue capacity on proc units

[Bead Pages](../README.md) / [sase-11l](README.md) / sase-11l.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ls](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ls.md) · **Assignee:** `sase-11l.1` · **Size:** large
**Created:** 2026-09-15 22:45:59 EDT · **Closed:** 2026-09-15 23:56:07 EDT
**Plan:** [202609/hold\_directive.md](https://github.com/sase-org/sase--plans/blob/main/202609/hold_directive.md)

## Description

queue-on-procs: allow %queue(capacity=) on %proc units with default weight 0 so a stand-alone proc can gate on runner load and drain the host before dispatch.

## Notes

[2026-09-16T03:56:07Z · sase-11l.1] Implemented proc queue support across parser, wire, and admission; verified core parser/digest/capacity coverage, Python wire/admission regression tests, binding validation, linked core just check, and primary just check.

## Dependencies

- **Blocks:** [sase-11l.5](sase-11l.5.md) ◐ · ⧖ 2026-09-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11l.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11l.1.md) | [sase-11l.1](sase-11l.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b6b11f2`](https://github.com/sase-org/sase/commit/b6b11f21556bccae2efcd8c32a161d4171614528) | feat(agent-launch): admit queued proc units | [sase-11l.1](sase-11l.1.md) | 2026-09-15 23:58:04 EDT |
| sase-core | [`sase-core@20f1dce`](https://github.com/sase-org/sase-core/commit/20f1dce477880f97995eb8ea87fcd48aa0515fc4) | feat(agent-launch): parse proc queue directives | [sase-11l.1](sase-11l.1.md) | 2026-09-16 00:01:16 EDT |
