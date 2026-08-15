# Bead: sase-m9.1.1 — Sase agent and shell taxonomy migration

[Bead Pages](../README.md) / [sase-m9.1](sase-m9.1.md) / sase-m9.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m9.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m9.1.md) · **Assignee:** `sase-m9.1.1.land`
**Created:** 2026-08-14 19:23:30 EDT · **Closed:** 2026-08-14 21:36:04 EDT
**Plan:** [202608/shell\_taxonomy.md](https://github.com/sase-org/sase--plans/blob/main/202608/shell_taxonomy.md)

## Description

Replace the agent-lane term with the canonical sase-agent and sase-shell model, preserve serialized and Python compatibility where required, and migrate monitor CLI language without changing runtime behavior.

## Notes

[2026-08-15T01:36:04Z · sase-m9.1.1.land] Landed shell taxonomy cleanup for user-facing monitor/agent-family docs and help text while preserving compatibility/internal lane APIs. Verified earlier in this workspace: generated skill preview clean, sase memory init --check passed, focused suite passed (399 tests), and just check passed with scoped tests escalating to the full suite. Finalizer also reran git diff --check clean. just check-full monitor result was not confirmed under the single-turn finalizer contract.

[2026-08-15T02:03:44Z · sase-m9.1.1.land--2] Post-close landing note after successful full verification: implementation landed as 4280bc990c59dd3c2558af442673b0c037015281 for canonical SaseAgentRef projection plus narrow AgentLaneRef and lane_* compatibility aliases; e923dcb5d104705db58ffdf402309b85aac160b5 for monitor -a/--agent CLI language with hidden --lane compatibility and historical lane wire and JSON fields retained; 2265f2618c149e6c29cada008d8121c7544b9332 for glossary, generated memory and provider surfaces, ACE terminology, and visual snapshot updates. Current landing commit 76356cf57d71e7574350f003f15caea0f50d9c0d aligned docs/monitors.md, docs/ace.md, agent-family, agents-sidecar, bead, development, getting-started, and SDD docs plus Agents help bindings, agent_hoods, agent_info_panel, and monitor exec wording. Verification covered the previously recorded focused projection, publication, association, hosted-link, monitor parser and handler, glossary, ACE terminology, and keymap suites; monitor start/list help showed agent options and suppressed lane aliases; sase memory init --check passed; generated skill deployment was verified by .venv/bin/sase skill init --diff returning clean; just check passed; the first just check-full reported four failures that passed in exact serial reruns and a focused xdist rerun, and monitor zefx9kd3zag9 reran just check-full successfully. Later non-epic commits 9c66dafee, 33180daf1, and 97e12b29e were reviewed for shell-taxonomy impact; they changed Antigravity and cheaper model config plus typed Artifacts-pane row identity, not agent-lane projection or monitor terminology, so no source integration was required. Retained lane terms are intentional compatibility or unrelated domains: sase.agent_lanes, AgentLaneRef and lane_* aliases, historical monitor lane records, JSON and internal engine APIs, hidden --lane flags, plus AXE, test, display, layout, and launch-routing lanes. Follow-up dispositions are complete: FORCE_COLOR ANSI assertion evidence was added as a +1 to ready task sase-m7; the Artifacts/Beads select_entry_target failure was recorded as a DISCOVERED ISSUE on active epic sase-m6 because of the typed Artifacts target linkage; the Models effort-picker 111-pixel PNG drift was created as ready task sase-ma. After close, symvision.md was read, just symvision passed, and no expired sase-m9.1.1 epic-symbol entries existed.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m9.1.1.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m9.1.1.land.md) | [sase-m9.1.1](sase-m9.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`76356cf`](https://github.com/sase-org/sase/commit/76356cf57d71e7574350f003f15caea0f50d9c0d) | docs: align shell taxonomy wording | [sase-m9.1.1](sase-m9.1.1.md) | 2026-08-14 21:36:53 EDT |
