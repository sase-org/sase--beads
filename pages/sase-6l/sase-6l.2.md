# Bead: sase-6l.2 — LLM execution-provider override + fakey demo scenario

[Bead Pages](../README.md) / [sase-6l](README.md) / sase-6l.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-6l.2`
**Created:** 2026-07-17 15:29:46 UTC
**Plan:** [202607/readme\_demo\_gif\_overhaul.md](https://github.com/sase-org/sase--plans/blob/main/202607/readme_demo_gif_overhaul.md)

## Description

See "Phase `override`": add a provider-agnostic SASE_LLM_EXEC_PROVIDER env knob at the invoke_agent provider-lookup choke point so launches execute under fakey while displaying the requested provider/model, record the executing provider in run artifacts, audit launch preflights, and add a bundled long-streaming fakey `demo` scenario with tests.

## Notes

COMMIT: f19cb4320

## Dependencies

- **Blocks:** [sase-6l.4](sase-6l.4.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-6l.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-6l.2/README.md) | [sase-6l.2](sase-6l.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`f8a8922`](https://github.com/sase-org/sase/commit/f8a892234fa7192492c9c7b3bf1247f49950ed3f) | feat(llm): support execution provider overrides (sase-6l.2) | [sase-6l.2](sase-6l.2.md) | 2026-07-17 16:21:15 |
