# Bead: sase-158 — Live, streaming progress for sase update

[Bead Pages](../README.md) / sase-158

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.1d](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.1d.md) · **Assignee:** `sase-158.land`
**Created:** 2026-09-21 07:49:21 EDT
**Plan:** [202609/sase\_update\_live\_progress.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_update_live_progress.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/sase_update_live_progress.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/sase_update_live_progress.md

<!-- sase:links:end -->

## Description

`sase update` shows every step as it happens: a live timeline on terminals and an append-only log when output is piped. It streams the tail of slow subprocess output (cargo, uv), shows each checkout's commits and diffstat as it fast-forwards, expands the failing step's output on error, survives Ctrl-C cleanly, and always leaves a full log file behind. The JSON and quiet contracts stay stable.

## Notes

[2026-09-21T14:49:56Z · sase-11y.11.land] DISCOVERED ISSUE (sase-11y.11 land agent, workspace sase_32, master f330e2b94): three whole-repo just check gates are red on files added or changed by 94ccd1917 (sase-158.1, streaming subprocess runner). (1) lint (mypy): src/sase/dev_update/prebuild.py:134 and :162 pass _run_command where DevCommandRunner is expected. DevCommandRunner.__call__ gained an on_output keyword that _run_command lacks. Also routed to sase-th note #5 by sase-14q, and reported by phase sase-11y.11.3 (PROPOSED FOLLOW-UP). (2) lint (test waits): tests/dev_update/test_stream_command.py:119 fixed-sleep-missing-pragma (needs '# sase-test-wait: <reason>' or an observable wait). (3) lint (symvision): sanitize_line in src/sase/dev_update/stream_command.py is an unused public symbol. Consume it in a later phase with a sase-158 --epic-symbol entry until then, or privatize it. The sase-158.1 note verified mypy on only 4 files and never reached the whole-repo gates, so these slipped through. Every agent's just check stops at mypy until (1) is fixed.

[2026-09-21T20:17:32Z · sase-158.land] LANDING INTERRUPTED (sase-158.land, master 562d52db0): remaining epic-caused work planned as a child epic ("Finish sase update live progress", phases stream-and-backend-fixes, timeline-renderer-fixes, handler-wiring-fixes).

Verified: all 5 phases are implemented per the plan (commits 94ccd1917, d9a1de8cc, 5a89392fe, f64bd3ac2, cc2953128). Targeted tests pass (87 + 105). Every whole-repo `just check` lint gate is green on master: mypy, test waits, symvision, pyscripts, toobig. The check test lane was cut off while setup rebuilt sase_core_rs from source (blocked_unpublished core floor); that is not epic work. No --epic-symbol entries.

Note #1 discovered issues are resolved: the prebuild mypy error (f64bd3ac2), the test-wait pragma, and sanitize_line, privatized in 319fe6b24.

Remaining epic-caused defects, now in the child plan:
(1) HIGH: result panels print to stdout while the transient Live region is still running, which corrupts success, mode-switch, and dry-run output on a real terminal.
(2) The managed uv step never receives output lines (no tail, failure expansion, -v, or log output).
(3) Transitive uv packages become top-level rows.
(4) restart/completions/managed rows are declared before the dev rows, so they render out of order.
(5) Failure frames show pending rows as ○, and plain mode prints skipped lines after the error panel.
(6) finalize("interrupted") also marks pending rows; a late Ctrl-C prints the frame twice and writes a second journal entry.
(7) -v goes silent after 200 lines per step.
(8) run_streaming does not bound its pump joins or group-kill after the leader exits, so a timeout can hang.
(9) CRLF lines become empty strings.
(10) The prebuild streaming path drops stdin=DEVNULL.
(11) The health-check repair row is not parented.
(12) Stale merging…/fetching… details.
(13) The 28-char title cap truncates the plan's own titles.
(14) The plain fallback triggers lazily.
(15) The running clock is not m:ss.
(16) The log header has no argv or mode.
(17) CI: tests/completion/snapshots/cli_spec.json is missing update -v (2 failing tests on master).
(18) Dead members, duplicate RunUvFn, and docs inaccuracies.
Also added: Ctrl-C at the mode-switch confirmation prompt should exit 130 with no traceback.

Integration: I reviewed every commit since 94ccd1917. 319fe6b24 and d05be99aa already absorbed epic fallout. No other commit needs to use or conflicts with update_progress/run_streaming.

PROPOSED FOLLOW-UP outcomes:
- sase-158.2 note #1 (pyscripts Rule 2 on tools/fix_tui_screenshots): declined; already resolved, `lint (pyscripts)` passes on master.
- sase-158.4 note #1 (split tests/test_detach_scope.py): declined; done by d05be99aa, toobig passes.

Declined review items:
- Dry-run JSON log_path key inconsistency: dry runs have no log by design.
- Check-summary skipped count and display-name collision cosmetics: harmless.
- Hooking the Admin Center Updates tab to the progress events: explicitly out of scope in the plan and not proposed by any bead.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-158.1](sase-158.1.md) | Streaming subprocess runner | ✓ closed | medium | 2026-09-21 | 1 | 1 |
| [sase-158.2](sase-158.2.md) | Progress event protocol, timeline model, and renderers | ✓ closed | medium | 2026-09-21 | 1 | 1 |
| [sase-158.3](sase-158.3.md) | Emit progress events from dev-update, uv, and mode-switch backends | ✓ closed | medium | 2026-09-21 | 1 | 1 |
| [sase-158.4](sase-158.4.md) | Wire the live timeline into the sase update live path | ✓ closed | medium | 2026-09-21 | 1 | 1 |
| [sase-158.5](sase-158.5.md) | Mode switch, dry-run, and documentation | ✓ closed | small | 2026-09-21 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-158: Live, streaming progress for sase update [in_progress]"]
    n1["sase-158.1: Streaming subprocess runner [closed]"]
    n2["sase-158.2: Progress event protocol, timeline model, and renderers [closed]"]
    n3["sase-158.3: Emit progress events from dev-update, uv, and mode-switch backends [closed]"]
    n4["sase-158.4: Wire the live timeline into the sase update live path [closed]"]
    n5["sase-158.5: Mode switch, dry-run, and documentation [closed]"]
    n6["sase-158.6: Finish sase update live progress [in_progress]"]
    n7["sase-158.6.1: Bound streaming waits, fix CRLF, and fix backend step details [closed]"]
    n8["sase-158.6.2: Fix the timeline model, renderers, and session lifecycle [in_progress]"]
    n9["sase-158.6.3: Fix the update handlers, managed rows, and docs [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n6 --> n7
    n6 --> n8
    n6 --> n9
    n1 -.-> n3
    n2 -.-> n3
    n3 -.-> n4
    n4 -.-> n5
    n8 -.-> n9
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-158.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-158.1.md) | [sase-158.1](sase-158.1.md) | 1 |
| [bbugyi200.apollo.sase-158.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-158.2/README.md) | [sase-158.2](sase-158.2.md) | 1 |
| [bbugyi200.apollo.sase-158.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-158.3/README.md) | [sase-158.3](sase-158.3.md) | 1 |
| [bbugyi200.apollo.sase-158.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-158.4/README.md) | [sase-158.4](sase-158.4.md) | 1 |
| [bbugyi200.apollo.sase-158.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-158.5/README.md) | [sase-158.5](sase-158.5.md) | 1 |
| [bbugyi200.apollo.sase-158.6.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-158.6.1/README.md) | [sase-158.6.1](sase-158.6.1.md) | 1 |
| [bbugyi200.apollo.sase-158.6.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-158.6.2/README.md) | [sase-158.6.2](sase-158.6.2.md) | 1 |
| [bbugyi200.apollo.sase-158.6.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-158.6.3/README.md) | [sase-158.6.3](sase-158.6.3.md) | 0 |
| [bbugyi200.apollo.sase-158.6.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-158.6.land/README.md) | [sase-158.6](sase-158.6.md) | 0 |
| [bbugyi200.apollo.sase-158.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-158.land.md) | [sase-158](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`94ccd19`](https://github.com/sase-org/sase/commit/94ccd19176a50586b97c2f8add0d431d1097ed18) | feat(dev-update): add line-streaming subprocess runner with on\_output sink | [sase-158.1](sase-158.1.md) | 2026-09-21 09:28:42 EDT |
| sase | [`d9a1de8`](https://github.com/sase-org/sase/commit/d9a1de8cc03d9c8f0cab1a50d150fc8bc67481cd) | feat(update-progress): add event protocol, timeline, renderers, and session | [sase-158.2](sase-158.2.md) | 2026-09-21 09:38:52 EDT |
| sase | [`5a89392`](https://github.com/sase-org/sase/commit/5a89392fe0fbfc59052b47257b9a882345c3302a) | feat(dev-update): instrument plan, execute, reconcile and mode-switch backends with progress events | [sase-158.3](sase-158.3.md) | 2026-09-21 10:35:55 EDT |
| sase | [`f64bd3a`](https://github.com/sase-org/sase/commit/f64bd3ac23c282e3af056ace496b5def2eccf37c) | feat(update): wire live-update progress session timeline | [sase-158.4](sase-158.4.md) | 2026-09-21 13:32:15 EDT |
| sase | [`cc29531`](https://github.com/sase-org/sase/commit/cc2953128a4ad317b4dc9f0720f629a678bcfaa6) | feat(update): run mode-switch in live session, transient dry-run timeline, docs | [sase-158.5](sase-158.5.md) | 2026-09-21 14:58:00 EDT |
| sase | [`2f15d0a`](https://github.com/sase-org/sase/commit/2f15d0a7269aef13b62365e735a2aa1cda59a772) | feat(update-progress): fix timeline model, renderers, and session lifecycle | [sase-158.6.2](sase-158.6.2.md) | 2026-09-21 16:41:45 EDT |
| sase | [`e0ffcfd`](https://github.com/sase-org/sase/commit/e0ffcfde81bc681f3942d00cee34e9b9fdec6c35) | fix(dev-update): bound streaming waits, CRLF lines, and backend step details | [sase-158.6.1](sase-158.6.1.md) | 2026-09-21 17:40:36 EDT |
