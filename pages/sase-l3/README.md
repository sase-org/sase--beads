# Bead: sase-l3 — Grok Build LLM provider

[Bead Pages](../README.md) / sase-l3

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.zu](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.zu.md) · **Assignee:** `sase-l3.land`
**Created:** 2026-08-13 14:40:33 EDT · **Closed:** 2026-08-14 07:57:08 EDT
**Plan:** [202608/grok\_provider.md](https://github.com/sase-org/sase--plans/blob/main/202608/grok_provider.md)

## Description

SASE gains a first-class `grok` LLM provider driving xAI's Grok Build CLI, supported everywhere the existing providers are — invocation, streaming text, reasoning pane, Tools panel, usage/cost accounting, doctor, agent-cli inventory and updates, model routing, skill deployment, TUI theming, and docs — with tool rows and reasoning that render as richly as Claude's rather than degrading to opaque key lists.

## Notes

[2026-08-13T20:22:58Z · sase-kz.land] DISCOVERED ISSUE: Proposed by sase-kz.8 during epic sase-kz landing, and independently reproduced by sase-kz.land at master 026de34f6 on a clean tree. `just _lint-symvision` fails repo-wide with exactly one finding: 'stream_and_parse_messages_json_output in src/sase/llm_provider/_subprocess_claude.py' (unused public function). Because symvision runs before the test lanes in both `just check` and `just check-full`, this blocks the whole-repo gate for every agent, not just this epic's. Causally owned here: phase sase-l3.1 (ad4ae62ae) introduced the symbol as a provider-parameterized seam and re-exported it from src/sase/llm_provider/_subprocess.py:50; its only current callers are _subprocess_claude.py:36 and tests/llm_provider/test_messages_wire.py. The second real consumer is phase sase-l3.3 (src/sase/llm_provider/grok.py), which is still in progress -- so the finding should clear on its own when l3.3 lands. If l3.3 will not consume it directly, the symvision decision hierarchy applies instead ('_'-prefix it, since today it is used only within _subprocess_claude.py plus the re-export). All other gates are green at 026de34f6: every other lint gate, SASE validation, committed-plan validation, and the full test suite (29682 passed, 10 skipped, exit 0).

[2026-08-13T21:28:55Z · toobig-2l.split_file.tests.monitor.test_monitor_store.0] DISCOVERED ISSUE: During unrelated monitor-store test-file splitting, all 28 affected tests collected but failed in shared setup because src/sase/llm_provider/_subprocess.py imports the absent public stream_and_parse_messages_json_output; _subprocess_claude.py now defines only the private _stream_and_parse_messages_json_output. Corroborated exact duplicate task sase-lg. This also belongs here because the regression is causally tied to phase sase-l3.1's provider-neutral stream layer and its collision with the private rename from sase-ld.

[2026-08-13T23:49:18Z · 001.f1] DISCOVERED ISSUE: During unrelated confirm_notification_read_tab verification on 2026-08-13, just check fails before the test lane at whole-repo Ruff with F811 in src/sase/llm_provider/_subprocess_claude.py: stream_and_parse_messages_json_output is defined at both lines 42 and 112. The local diff touches only src/sase/ace/tui/modals/notification_modal_basic_actions.py and tests/test_notification_modal_read_tab.py. This is causally tied to this epic's provider-neutral/Grok stream-symbol work and the public/private rename conflict already tracked by ready task sase-lg; added +1 evidence there rather than creating a new task.

[2026-08-14T11:57:08Z · sase-l3.land] VERIFIED (step 1): all 8 phases closed and their claimed work is really in the tree -- provider-neutral Messages-wire stream layer (_subprocess_claude.py), Grok tool-call normalizer (_tool_call_grok.py), grok.py provider module + its sase_llm entry point, doctor identity check with a regex derived from real Grok Build 1.0.3 output, badge/palette/model-surface polish, skill deployment via the generic ~/.grok/skills path, and a docs sweep whose claims match the code (four effort levels, grok-4.6 only). Read every child bead note and confirmed each was addressed.

INTEGRATED (step 2): the only real collision with non-epic work was stream_and_parse_messages_json_output -- phase .1 (ad4ae62ae) added it public, non-epic c1970b5a0 (task sase-ld) made it private, and 4183f3d4d then added a duplicate wrapper. The tree resolves this correctly now: 'python -c import sase.llm_provider' succeeds, clearing task sase-lg's reproduction, and ruff/mypy/symvision are clean on it. Both blockers phase .8 recorded as unresolved have since been fixed by later commits (procs facade, notification store). No post-epic commit duplicates the provider-neutral layer this epic added.

DEFECT FOUND AND FIXED DURING LANDING: phase .2 introduced _GROK_TOOL_USES, a module-global written on every tool_use but read with .get() and never released -- the only unbounded module-global among all the tool-call normalizers (ToolCallDurationTracker pops; MuseToolCallTracker is per-run), so a long Grok run retained every tool input, including full Write payloads, for the life of the process. Changed to .pop() and added a regression test confirmed to fail against the old code. Verified in this landing pass: 652 tests pass across tests/ace/tui/tools + tests/llm_provider, and ruff, ruff-format, and mypy are clean on both changed files.

FOLLOW-UPS: six of seven proposals already had beads (sase-l8/l9/la, sase-lb, sase-ll, sase-lm) or were fixed during the epic; filed sase-lq for the Grok CLAUDE.md/AGENTS.md double-load, the only one with no existing bead. Also flagged and recorded on sase-ln: the epic's own docs commit aea9bf645 silently captured 10 files of a concurrent agent's in-progress notification work under a message describing only doc changes -- no work was lost, but that history is misattributed to sase-l3.7 on origin/master; sase-ln tracks the 'stitch create' staging bug behind it.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-l3.1](sase-l3.1.md) | Provider-neutral Messages-wire stream layer | ✓ closed | medium | 2026-08-13 | 1 | 2 |
| [sase-l3.2](sase-l3.2.md) | Grok tool-call normalizer | ✓ closed | medium | 2026-08-13 | 1 | 1 |
| [sase-l3.3](sase-l3.3.md) | The grok provider module | ✓ closed | medium | 2026-08-13 | 1 | 1 |
| [sase-l3.4](sase-l3.4.md) | Doctor, inventory, and binary-collision safety | ✓ closed | small | 2026-08-13 | 1 | 1 |
| [sase-l3.5](sase-l3.5.md) | Badge, palette, and model-surface polish | ✓ closed | small | 2026-08-13 | 1 | 1 |
| [sase-l3.6](sase-l3.6.md) | Skill deployment and instruction files | ✓ closed | small | 2026-08-13 | 1 | 1 |
| [sase-l3.7](sase-l3.7.md) | Documentation sweep | ✓ closed | medium | 2026-08-13 | 1 | 1 |
| [sase-l3.8](sase-l3.8.md) | Authenticated end-to-end smoke exercises | ✓ closed | xsmall | 2026-08-13 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-l3: Grok Build LLM provider [closed]"]
    n1["sase-l3.1: Provider-neutral Messages-wire stream layer [closed]"]
    n2["sase-l3.2: Grok tool-call normalizer [closed]"]
    n3["sase-l3.3: The grok provider module [closed]"]
    n4["sase-l3.4: Doctor, inventory, and binary-collision safety [closed]"]
    n5["sase-l3.5: Badge, palette, and model-surface polish [closed]"]
    n6["sase-l3.6: Skill deployment and instruction files [closed]"]
    n7["sase-l3.7: Documentation sweep [closed]"]
    n8["sase-l3.8: Authenticated end-to-end smoke exercises [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n1 -.-> n2
    n2 -.-> n3
    n3 -.-> n4
    n3 -.-> n5
    n3 -.-> n6
    n4 -.-> n7
    n5 -.-> n7
    n6 -.-> n7
    n7 -.-> n8
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-l3.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-l3.1.md) | [sase-l3.1](sase-l3.1.md) | 2 |
| [bbugyi200.athena.sase-l3.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-l3.2/README.md) | [sase-l3.2](sase-l3.2.md) | 1 |
| [bbugyi200.athena.sase-l3.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-l3.3/README.md) | [sase-l3.3](sase-l3.3.md) | 1 |
| [bbugyi200.athena.sase-l3.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-l3.4/README.md) | [sase-l3.4](sase-l3.4.md) | 1 |
| [bbugyi200.athena.sase-l3.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-l3.5/README.md) | [sase-l3.5](sase-l3.5.md) | 1 |
| [bbugyi200.athena.sase-l3.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-l3.6/README.md) | [sase-l3.6](sase-l3.6.md) | 1 |
| [bbugyi200.athena.sase-l3.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-l3.7/README.md) | [sase-l3.7](sase-l3.7.md) | 1 |
| [bbugyi200.athena.sase-l3.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-l3.8/README.md) | [sase-l3.8](sase-l3.8.md) | 1 |
| [bbugyi200.athena.sase-l3.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-l3.land/README.md) | [sase-l3](README.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ad4ae62`](https://github.com/sase-org/sase/commit/ad4ae62aef705022872998254613c72e068a6d43) | feat(llm-provider): add provider-neutral messages parser | [sase-l3.1](sase-l3.1.md) | 2026-08-13 15:23:41 EDT |
| sase--beads | [`sase--beads@db722fb`](https://github.com/sase-org/sase--beads/commit/db722fbec1a17d7e613e1649ac22fd6179664ffc) | chore(beads): publish sase-l6 plan records | [sase-l3.1](sase-l3.1.md) | 2026-08-13 15:31:38 EDT |
| sase | [`4d36d6d`](https://github.com/sase-org/sase/commit/4d36d6d3d6632859ddc5cf78ab9f621f9cc92ccb) | feat: normalize Grok tool-call stream artifacts | [sase-l3.2](sase-l3.2.md) | 2026-08-13 17:04:01 EDT |
| sase | [`3085a0d`](https://github.com/sase-org/sase/commit/3085a0d287adadc52aa44a31cbd38896fe10fbc9) | feat(llm): add Grok provider | [sase-l3.3](sase-l3.3.md) | 2026-08-13 17:32:54 EDT |
| sase | [`fbcf643`](https://github.com/sase-org/sase/commit/fbcf64399ee06d516bc4298a22afe71956595bf0) | fix(doctor): flag grok executables that aren't Grok Build | [sase-l3.4](sase-l3.4.md) | 2026-08-13 17:53:42 EDT |
| sase | [`c1b2724`](https://github.com/sase-org/sase/commit/c1b2724a1fc46e264f1900395b2023644eb40552) | test: cover Grok skill deployment | [sase-l3.6](sase-l3.6.md) | 2026-08-13 18:06:36 EDT |
| sase | [`d9c685e`](https://github.com/sase-org/sase/commit/d9c685e86b808e481bb826e24ac7f0f27e91baa0) | feat: polish Grok provider presentation | [sase-l3.5](sase-l3.5.md) | 2026-08-13 18:17:52 EDT |
| sase | [`aea9bf6`](https://github.com/sase-org/sase/commit/aea9bf645a8e6e1fc7ccff57253f31068eb9f01a) | docs: add Grok Build coverage across provider documentation | [sase-l3.7](sase-l3.7.md) | 2026-08-13 18:42:15 EDT |
| sase | [`aef2d8e`](https://github.com/sase-org/sase/commit/aef2d8eb5b11c46265a468fa49686c52d33cb79a) | fix(grok): recreate timer for interrupt relaunch | [sase-l3.8](sase-l3.8.md) | 2026-08-13 20:24:14 EDT |
| sase | [`d1e8815`](https://github.com/sase-org/sase/commit/d1e88155b140e793560574e480c8cc17ccdd57c6) | fix(llm\_provider): release Grok tool\_use state when its result arrives | [sase-l3](README.md) | 2026-08-14 07:59:13 EDT |
