# Bead: sase-1qz — Agent Hijack: stop a stalled agent, keep its work, recover in one keypress

[Bead Pages](../README.md) / sase-1qz

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.research.33.linker.w0` · **Assignee:** `sase-1qz.land`
**Created:** 2026-11-02 17:42:13 EST · **Closed:** 2026-11-07 05:37:27 EST
**Plan:** [202611/agent\_hijack.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_hijack.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202611/agent_hijack.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | [bead:sase-1rj][2] | Agent Hijack epic whose land triage filed this follow-up; its plan plan:202611/agent_hijack.md defines the hijack and recovery contract |
| related | [bead:sase-1rk][3] | Agent Hijack epic whose land triage filed this follow-up; its plan plan:202611/agent_hijack.md defines the hijack and recovery contract |

_Plus 13 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/agent_hijack.md
[2]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-1rj/README.md
[3]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-1rk/README.md

<!-- sase:links:end -->

## Description

A user can hijack a stalled sase agent (,k, the kill dialog's h, or `sase agent hijack NAME`). Its process tree stops, but its workspace claim, Agents-tab node, and evidence stay. The node shows a ⏏ HIJACKED status, and <enter> opens a single-keypress recovery panel: escalate to a smarter model, continue, or instruct in the same workspace; restart or edit from a fresh workspace after a verified snapshot; view the diff, open a shell, or dismiss. Every path is durable, exactly-once, and fails closed so work is never silently lost.

## Notes

[2026-11-05T01:37:08Z · sase-1ra.6--4] DISCOVERED ISSUE: sase tool run check 0ea4d12896bf1d703ba1b18ecdb64ea3 on HEAD 02e93fd failed tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed. The audit reports five unreviewed sites in src/sase/agent/hijack/recover_subject.py and recover_settle.py, introduced by commit 8462195314 (feat(agent): exactly-once hijack recovery launch and settlement). This is within the active Agent Hijack recovery source scope; the same audit node is tracked by sase-1by, and this post-close recurrence was corroborated there.

[2026-11-07T09:56:39Z · toobig-9m.agent_artifact_run_trash.0] DISCOVERED ISSUE: sase tool run check ec87921f2522ad058bc846f39079f15f on HEAD fb66f62d34 failed at lint (test waits) with tests/fakey/test_agent_hijack_e2e.py:105: fixed-sleep-missing-pragma. The sleep is time.sleep(0.02) in _wait_for, added by f5124b3310 (feat(agent-hijack): retire beta flag and add end-to-end coverage) which is this epic's phase .11 prove-it-end-to-end work. Deterministic static lint: tools/check_test_wait_helpers reports the same file:line before pytest runs. This turn only split src/sase/core/agent_artifact_run_trash.py and did not touch the fakey hijack e2e file. Fix by adding an inline '# sase-test-wait: <reason>' pragma or replacing the poll sleep with an observable wait. Closed sase-zh/sase-18r were the same gate in different files and are not this node. No new task: this epic still owns the introducing test.

[2026-11-07T10:17:22Z · sase-1qz.land] LAND FOLLOW-UP TRIAGE (sase-1qz.land). CREATED (task(feature), ready, provenance sase-1qz.11): sase-1rj Telegram/mobile hijack recovery (11 #1); sase-1rk quiet-for-N-min stall hint (11 #2); sase-1rl x-as-fate-chooser decision (11 #3); sase-1rm pre-expiry hold warning (11 #4); sase-1rn Salvage & Commit (11 #5); sase-1ro hijack recovery guide candidate (11 #7); sase-1rp split docs/reference/tui/agent-statuses.md (found at land: page at 5999/6000-word cap after compressing hijack rows). CORROBORATED (+1): sase-1q0 microbench (1qz.3 #1, 1qz.4 #1, 1qz.8 #1); sase-1oy sudo settlement/reclaimer (1qz.1 #1, 1qz.4 #1); sase-1mr startup toast (1qz.1 #1). ACTIVE-EPIC: isolation-guard offender tests/ace/tui/test_log_panel_keymap.py:331 (1qz.7 #1) still fails on f5124b3310; owned by sase-1ra (introduced by sase-1ra.5 45bcf6fe39), supplementary DISCOVERED ISSUE note added there. DECLINED: 1qz.11 #6 decision records (reviewer chose decision_records=no; refiling re-litigates that decision); 1qz.4 #2 glossary strand (published by sase-1qz.11 as sase/memory/glossary/agent-hijack.md); 1qz.9 #1 / 1qz.10 #1 / 1qz.11 #8 sase-core schema skew (no longer reproduces: after just install-venv, check _setup passes with only the informational ahead-of-pin note); 1qz.10 #2 symvision _choice_for_enter_target (symvision green on this tree); 1qz.1 #1 monitor starter race and pulse-navigation, 1qz.4 #1 snippets debounce and app_import_budget (none reproduced in today's 60410-test full-lane run, ToolRun 72dc8c62653f598b0d866b6b748e3c6d); 1qz.4 #1 / 1qz.8 #1 panel pilot grammar timeouts (sase-1al, predate fix 02e93fd261); 1qz.8 #1 sase-1pk feature-flag lint (transient; lint feature flags green). Nested epic sase-1qz.6.1 follow-ups were triaged by sase-1qz.6.1.land.

[2026-11-07T10:37:27Z · sase-1qz.land] LAND VERIFICATION (sase-1qz.land). VERIFIED: all 11 phases closed, including nested epic sase-1qz.6.1 (7 phases, closed by its own lander after a settlement-completion tale). Read every child note; checked source against the plan: Rust bindings (19 hijack/recovery symbols in sase_core_rs at pin c8adc878ae), HIJACKED in the Stopped bucket and ESCALATED/CONTINUED beside ANSWERED, ,k in default_config.yml, kill-dialog h choice, footer chips, Enter routes HIJACKED rows to the recovery panel, `sase agent hijack` / `sase agent recover` (-a/-D/-j/-m/-n/-p), restart claims the restart resolution, kill refuses HIJACKED, strict_workspace follow-up, #fork hijack frame, custody hooks in stale sweep, healer, and stranded facts. DECISIONS honored: enter_default=escalate, successor_context=fork default, glossary:agent-hijack strand published, no decision records. Flag agent_hijack retired: registry, schema, and Off branches gone; flag bead sase-1r1 closed. 269 hijack tests passed after `just install-venv` (the venv wheel was stale). Epic note #1 (marker-path audit) was fixed by sase-1qz.6.1.4.1.6. LANDING FIXES (epic-caused): ESCALATED/CONTINUED rendered bold cyan against the plan's grey "exactly like ANSWERED", so they now render in the settled-gate grey, with docs and test updated; `sase agent recover -h` and two docs pages still described the retired beta flag; the land phase's e2e poll sleep lacked a sase-test-wait pragma, so lint (test waits) was red on master, also reported as epic note #2; the land phase pushed reference/tui/agent-statuses.md to 6152/6000 words (docs lint red), so the hijack rows are collapsed to one HIJACKED row that points at agents-tab-modes.md#hijack-recovery-panel (5999 words; split filed as sase-1rp); the recovery panel's submit_agent_recovery was missing from the proc-producer inventory; and the land phase's new glossary term re-wrapped the generated term list, breaking the xprompt-terminology allowlist. INTEGRATION: the ACE-run prune and trash feature (sase-1rd, landed mid-epic) did not protect hijacked runs, so a held or expired hijack's artifacts dir could be quarantined, breaking Restart and Edit. Retention now protects runs referenced by active or expired hijack ledger records (new ledger.list_recoverable_records), with a test and a scheduler-housekeeping doc line. Also reviewed the staged-handoff kill-path retirement, stale_running_cleanup split, stranded-handoff, retention-custody, codex mid-turn-kill, unread-jump fallback, and recent hijack toobig splits: nothing else to rewire. Upstream fb66f62d34 and 9cded455b0 are disjoint split refactors. CHECK: sase tool run check 79a3696305f060663c8695849edbf01b passed (exit 0, all lint gates plus 1150 scoped test files). The earlier full-lane run 72dc8c62653f598b0d866b6b748e3c6d failed only on the sase-1ra-owned isolation guards plus the two now-fixed nodes. FOLLOW-UPS: see note #3 (7 feature tasks sase-1rj..sase-1rp, +1 on sase-1q0/sase-1oy/sase-1mr, sase-1ra note, and the declines with reasons).

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1qz.1](sase-1qz.1.md) | sase-core: hijack statuses, ledger wire, and eligibility | ✓ closed | medium | 2026-11-02 | 1 | 2 |
| [sase-1qz.10](sase-1qz.10.md) | Instruct and Edit through the prompt bar | ✓ closed | medium | 2026-11-02 | 1 | 1 |
| [sase-1qz.11](sase-1qz.11.md) | Remove the flag, document, and prove it end to end | ✓ closed | medium | 2026-11-02 | 1 | 0 |
| [sase-1qz.2](sase-1qz.2.md) | sase-core: escalation policy, continuation prompt, and config | ✓ closed | medium | 2026-11-02 | 1 | 2 |
| [sase-1qz.3](sase-1qz.3.md) | Runner settlement that keeps custody | ✓ closed | medium | 2026-11-02 | 1 | 1 |
| [sase-1qz.4](sase-1qz.4.md) | The stop protocol and \`sase agent hijack\` | ✓ closed | medium | 2026-11-02 | 1 | 1 |
| [sase-1qz.5](sase-1qz.5.md) | Every release path respects a hijack | ✓ closed | medium | 2026-11-02 | 1 | 1 |
| [sase-1qz.6](sase-1qz.6.md) | Keep-the-work recovery (Escalate, Switch, Continue, Instruct) | ✓ closed | large | 2026-11-02 | 0 | 0 |
| [sase-1qz.7](sase-1qz.7.md) | Start-over and leave recovery (Restart, Edit backend, Dismiss) | ✓ closed | medium | 2026-11-02 | 1 | 1 |
| [sase-1qz.8](sase-1qz.8.md) | Agents-tab rendering and the ,k way in | ✓ closed | medium | 2026-11-02 | 1 | 1 |
| [sase-1qz.9](sase-1qz.9.md) | The recovery panel | ✓ closed | medium | 2026-11-02 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1qz: Agent Hijack: stop a stalled agent, keep its work, recover in one keypress [closed]"]
    n1["sase-1qz.1: sase-core: hijack statuses, ledger wire, and eligibility [closed]"]
    n2["sase-1qz.10: Instruct and Edit through the prompt bar [closed]"]
    n3["sase-1qz.11: Remove the flag, document, and prove it end to end [closed]"]
    n4["sase-1qz.2: sase-core: escalation policy, continuation prompt, and config [closed]"]
    n5["sase-1qz.3: Runner settlement that keeps custody [closed]"]
    n6["sase-1qz.4: The stop protocol and `sase agent hijack` [closed]"]
    n7["sase-1qz.5: Every release path respects a hijack [closed]"]
    n8["sase-1qz.6: Keep-the-work recovery (Escalate, Switch, Continue, Instruct) [closed]"]
    n9["sase-1qz.6.1: Complete keep-work recovery for hijacked agents [closed]"]
    n10["sase-1qz.6.1.1: Rust recovery transaction and preview contracts [closed]"]
    n11["sase-1qz.6.1.2: Read-only recovery preview and continuation context [closed]"]
    n12["sase-1qz.6.1.3: Same-workspace launch with mandatory inheritance [closed]"]
    n13["sase-1qz.6.1.4: Exactly-once recovery launch and settlement [closed]"]
    n14["sase-1qz.6.1.4.1: Complete the production keep-work recovery transaction [closed]"]
    n15["sase-1qz.6.1.4.1.1: Rust execution validation and confirmation contract [closed]"]
    n16["sase-1qz.6.1.4.1.2: Prepare and pin the real recovery prompt [closed]"]
    n17["sase-1qz.6.1.4.1.3: Submit and resume the pinned recovery request [closed]"]
    n18["sase-1qz.6.1.4.1.4: Prove required inheritance before provider execution [closed]"]
    n19["sase-1qz.6.1.4.1.5: Confirm the actual successor and fail safely [closed]"]
    n20["sase-1qz.6.1.4.1.6: Verify the production transaction and closure evidence [closed]"]
    n21["sase-1qz.6.1.5: Crash repair and successor-following waits [closed]"]
    n22["sase-1qz.6.1.6: Recovery command, durable operation, and integration coverage [closed]"]
    n23["sase-1qz.6.1.7: Verify and complete the assigned recovery phase [closed]"]
    n24["sase-1qz.7: Start-over and leave recovery (Restart, Edit backend, Dismiss) [closed]"]
    n25["sase-1qz.8: Agents-tab rendering and the ,k way in [closed]"]
    n26["sase-1qz.9: The recovery panel [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n8 --> n9
    n9 --> n10
    n9 --> n11
    n9 --> n12
    n9 --> n13
    n13 --> n14
    n14 --> n15
    n14 --> n16
    n14 --> n17
    n14 --> n18
    n14 --> n19
    n14 --> n20
    n9 --> n21
    n9 --> n22
    n9 --> n23
    n0 --> n24
    n0 --> n25
    n0 --> n26
    n1 -.-> n5
    n2 -.-> n3
    n4 -.-> n8
    n5 -.-> n6
    n6 -.-> n7
    n6 -.-> n25
    n7 -.-> n3
    n7 -.-> n8
    n8 -.-> n24
    n10 -.-> n11
    n10 -.-> n12
    n11 -.-> n13
    n12 -.-> n13
    n13 -.-> n21
    n15 -.-> n16
    n15 -.-> n18
    n16 -.-> n17
    n17 -.-> n19
    n18 -.-> n19
    n19 -.-> n20
    n21 -.-> n22
    n22 -.-> n23
    n24 -.-> n26
    n25 -.-> n26
    n26 -.-> n2
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1qz.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1qz.1/README.md) | [sase-1qz.1](sase-1qz.1.md) | 2 |
| [bbugyi200.apollo.sase-1qz.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1qz.2.md) | [sase-1qz.2](sase-1qz.2.md) | 2 |
| [bbugyi200.apollo.sase-1qz.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1qz.3.md) | [sase-1qz.3](sase-1qz.3.md) | 1 |
| [bbugyi200.apollo.sase-1qz.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1qz.4.md) | [sase-1qz.4](sase-1qz.4.md) | 1 |
| [bbugyi200.apollo.sase-1qz.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1qz.5/README.md) | [sase-1qz.5](sase-1qz.5.md) | 1 |
| [bbugyi200.apollo.sase-1qz.6.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1qz.6.1.1/README.md) | [sase-1qz.6.1.1](sase-1qz.6.1.1.md) | 2 |
| [bbugyi200.apollo.sase-1qz.6.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1qz.6.1.2/README.md) | [sase-1qz.6.1.2](sase-1qz.6.1.2.md) | 1 |
| [bbugyi200.apollo.sase-1qz.6.1.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1qz.6.1.3.md) | [sase-1qz.6.1.3](sase-1qz.6.1.3.md) | 1 |
| [bbugyi200.apollo.sase-1qz.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1qz.8.md) | [sase-1qz.8](sase-1qz.8.md) | 1 |
| [bbugyi200.athena.sase-1qz.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.10/README.md) | [sase-1qz.10](sase-1qz.10.md) | 1 |
| [bbugyi200.athena.sase-1qz.11](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qz.11.md) | [sase-1qz.11](sase-1qz.11.md) | 0 |
| [bbugyi200.athena.sase-1qz.6.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.6.1.2/README.md) | [sase-1qz.6.1.2](sase-1qz.6.1.2.md) | 0 |
| [bbugyi200.athena.sase-1qz.6.1.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qz.6.1.4.md) | [sase-1qz.6.1.4](sase-1qz.6.1.4.md) | 1 |
| [bbugyi200.athena.sase-1qz.6.1.4.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.6.1.4.1.1/README.md) | [sase-1qz.6.1.4.1.1](sase-1qz.6.1.4.1.1.md) | 1 |
| [bbugyi200.athena.sase-1qz.6.1.4.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.6.1.4.1.2/README.md) | [sase-1qz.6.1.4.1.2](sase-1qz.6.1.4.1.2.md) | 1 |
| [bbugyi200.athena.sase-1qz.6.1.4.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.6.1.4.1.3/README.md) | [sase-1qz.6.1.4.1.3](sase-1qz.6.1.4.1.3.md) | 1 |
| [bbugyi200.athena.sase-1qz.6.1.4.1.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qz.6.1.4.1.4.md) | [sase-1qz.6.1.4.1.4](sase-1qz.6.1.4.1.4.md) | 1 |
| [bbugyi200.athena.sase-1qz.6.1.4.1.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qz.6.1.4.1.5.md) | [sase-1qz.6.1.4.1.5](sase-1qz.6.1.4.1.5.md) | 1 |
| [bbugyi200.athena.sase-1qz.6.1.4.1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.6.1.4.1.6/README.md) | [sase-1qz.6.1.4.1.6](sase-1qz.6.1.4.1.6.md) | 1 |
| [bbugyi200.athena.sase-1qz.6.1.4.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qz.6.1.4.1.land.md) | [sase-1qz.6.1.4.1](sase-1qz.6.1.4.1.md) | 3 |
| [bbugyi200.athena.sase-1qz.6.1.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qz.6.1.5.md) | [sase-1qz.6.1.5](sase-1qz.6.1.5.md) | 1 |
| [bbugyi200.athena.sase-1qz.6.1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.6.1.6/README.md) | [sase-1qz.6.1.6](sase-1qz.6.1.6.md) | 1 |
| [bbugyi200.athena.sase-1qz.6.1.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qz.6.1.7.md) | [sase-1qz.6.1.7](sase-1qz.6.1.7.md) | 1 |
| [bbugyi200.athena.sase-1qz.6.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qz.6.1.land.md) | [sase-1qz.6.1](sase-1qz.6.1.md) | 3 |
| [bbugyi200.athena.sase-1qz.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.7/README.md) | [sase-1qz.7](sase-1qz.7.md) | 1 |
| [bbugyi200.athena.sase-1qz.9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qz.9.md) | [sase-1qz.9](sase-1qz.9.md) | 1 |
| [bbugyi200.athena.sase-1qz.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.land/README.md) | [sase-1qz](README.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@65925ca`](https://github.com/sase-org/sase-core/commit/65925ca8b6427fc0037c9ddbb5ebba8e6927fabe) | feat(agent-hijack): add core ledger and eligibility | [sase-1qz.1](sase-1qz.1.md) | 2026-11-02 20:45:42 EST |
| sase | [`85c8d46`](https://github.com/sase-org/sase/commit/85c8d4613a3a8ef06ec2e67de6c398d59b92b412) | feat(agent-hijack): add Python hijack workflow wrappers | [sase-1qz.1](sase-1qz.1.md) | 2026-11-02 20:48:03 EST |
| sase-core | [`sase-core@f1bbb4f`](https://github.com/sase-org/sase-core/commit/f1bbb4f3b81383c06df422c9df9fa13f0ec244f7) | feat(agent-hijack): add escalation policy and continuation-prompt core with bindings | [sase-1qz.2](sase-1qz.2.md) | 2026-11-02 23:27:54 EST |
| sase | [`38c3a3c`](https://github.com/sase-org/sase/commit/38c3a3c5fc92f6c3cb0d9887c7458a9e4666a178) | feat(agent-hijack): add Python escalation policy and continuation-prompt support | [sase-1qz.2](sase-1qz.2.md) | 2026-11-03 02:29:57 EST |
| sase | [`01a2828`](https://github.com/sase-org/sase/commit/01a28287c8f7d2ce5c7ae71e769e74a377892ea7) | feat(agent-hijack): settle hijacked runner outcome while holding custody | [sase-1qz.3](sase-1qz.3.md) | 2026-11-03 03:22:28 EST |
| sase | [`f163ba7`](https://github.com/sase-org/sase/commit/f163ba74c0dc2a237133e5af68b5ad8fd72ce789) | feat(agent-hijack): add ordered stop orchestrator with hijack ingress | [sase-1qz.4](sase-1qz.4.md) | 2026-11-03 06:35:53 EST |
| sase | [`8ac56e2`](https://github.com/sase-org/sase/commit/8ac56e2a09ed23f18d972041e814a384bb8d4d78) | feat(agent-hijack): retain claims across every release path | [sase-1qz.5](sase-1qz.5.md) | 2026-11-03 07:54:03 EST |
| sase | [`81808e9`](https://github.com/sase-org/sase/commit/81808e9ba0ad955a6a3562cd4a21b53b24bf542a) | feat(ace): add Agent Hijack controls to Agents tab | [sase-1qz.8](sase-1qz.8.md) | 2026-11-03 11:07:38 EST |
| sase-core | [`sase-core@bbef1df`](https://github.com/sase-org/sase-core/commit/bbef1df25612c79839e4ae96d9d5648ce041b4a8) | feat(agent-hijack): add recovery identity, preview, and reconcile wires | [sase-1qz.6.1.1](sase-1qz.6.1.1.md) | 2026-11-03 13:06:17 EST |
| sase | [`83cd8de`](https://github.com/sase-org/sase/commit/83cd8deffe4eff5362b773089c601b280d904462) | feat(agent-hijack): wrap recovery preview and reconcile bindings | [sase-1qz.6.1.1](sase-1qz.6.1.1.md) | 2026-11-03 13:08:21 EST |
| sase | [`09bd42e`](https://github.com/sase-org/sase/commit/09bd42e622e7b63823376c23844b9d37a21e2c2b) | feat(agent-hijack): same-workspace recovery successor with mandatory inheritance | [sase-1qz.6.1.3](sase-1qz.6.1.3.md) | 2026-11-03 17:12:38 EST |
| sase | [`a4fe560`](https://github.com/sase-org/sase/commit/a4fe5601302cf121e56dcc7c93c5b5c19c71a653) | feat(agent-hijack): add recovery preview and continuation context | [sase-1qz.6.1.2](sase-1qz.6.1.2.md) | 2026-11-04 00:14:05 EST |
| sase | [`8462195`](https://github.com/sase-org/sase/commit/84621953144b886b80b7c36c8d26b9b0aaeb7c7b) | feat(agent): exactly-once hijack recovery launch and settlement | [sase-1qz.6.1.4](sase-1qz.6.1.4.md) | 2026-11-04 17:29:08 EST |
| sase-core | [`sase-core@417d5c8`](https://github.com/sase-org/sase-core/commit/417d5c8d46aecc9eafc4fe31250307c714c5962a) | feat(agent-hijack): add execution validation and confirmation contract | [sase-1qz.6.1.4.1.1](sase-1qz.6.1.4.1.1.md) | 2026-11-05 10:49:21 EST |
| sase | [`c6e2c87`](https://github.com/sase-org/sase/commit/c6e2c87ba2a826d8b10b4e7418da8bd1c5209167) | fix(agent-hijack): prepare and pin recovery prompts | [sase-1qz.6.1.4.1.2](sase-1qz.6.1.4.1.2.md) | 2026-11-05 11:59:28 EST |
| sase | [`3fe8d5d`](https://github.com/sase-org/sase/commit/3fe8d5d34b7a0530860ff8f0e7922490dcbdc56f) | feat(recovery): enforce bootstrap inheritance before provider execution | [sase-1qz.6.1.4.1.4](sase-1qz.6.1.4.1.4.md) | 2026-11-05 12:45:56 EST |
| sase | [`7896ea6`](https://github.com/sase-org/sase/commit/7896ea657b8ef77c72f16cb309ca70f100e05381) | feat(agent-recovery): persist pinned recovery admission | [sase-1qz.6.1.4.1.3](sase-1qz.6.1.4.1.3.md) | 2026-11-05 14:21:08 EST |
| sase | [`812ddbc`](https://github.com/sase-org/sase/commit/812ddbc3aed901f77385830432216598f8843e4c) | fix(hijack): settle recovery only with verified custody | [sase-1qz.6.1.4.1.5](sase-1qz.6.1.4.1.5.md) | 2026-11-05 16:40:55 EST |
| sase | [`ef11650`](https://github.com/sase-org/sase/commit/ef11650ad40dd125d3b7c0cbace7ad6d7481e076) | test(agent): verify hijack recovery production transaction and closure evidence | [sase-1qz.6.1.4.1.6](sase-1qz.6.1.4.1.6.md) | 2026-11-05 17:51:01 EST |
| sase | [`52b1c45`](https://github.com/sase-org/sase/commit/52b1c451b1618e3479f1d6610b862a017224f4f1) | fix(hijack): integrate recovery transaction landing | [sase-1qz.6.1.4.1](sase-1qz.6.1.4.1.md) | 2026-11-05 18:55:22 EST |
| sase | [`5eef604`](https://github.com/sase-org/sase/commit/5eef60448ce9b44b253817df21835ba09993e42a) | chore(symvision): note sase-1qz.6.1.4.1 rows dropped at land | [sase-1qz.6.1.4.1](sase-1qz.6.1.4.1.md) | 2026-11-05 19:49:30 EST |
| sase--plans | [`sase--plans@920e0bc`](https://github.com/sase-org/sase--plans/commit/920e0bc0eab6ab925be4f08b1a40225c9c3a4e7e) | docs(plans): mark recovery\_transaction\_completion done | [sase-1qz.6.1.4.1](sase-1qz.6.1.4.1.md) | 2026-11-05 19:50:51 EST |
| sase | [`efac88d`](https://github.com/sase-org/sase/commit/efac88d0b987989debc6107dcc3d130feb31d8d8) | feat(hijack): reconcile\_wait crash repair and successor-following waits | [sase-1qz.6.1.5](sase-1qz.6.1.5.md) | 2026-11-05 20:41:46 EST |
| sase | [`a7d68a2`](https://github.com/sase-org/sase/commit/a7d68a2e71a99d12feb05289db32f1d30b5f295d) | feat(agent): add hijack recovery command and durable operation | [sase-1qz.6.1.6](sase-1qz.6.1.6.md) | 2026-11-06 09:56:04 EST |
| sase | [`acc6f78`](https://github.com/sase-org/sase/commit/acc6f7842214f4622576e3e56e4914e2e836e2bc) | chore(symvision): re-key leftover sase-1qz.6 epic-symbol rows to sase-1qz.7 | [sase-1qz.6.1.7](sase-1qz.6.1.7.md) | 2026-11-06 10:49:47 EST |
| sase-core | [`sase-core@cd02e31`](https://github.com/sase-org/sase-core/commit/cd02e319227a0359d418f4aae60ce93b5e45bb5c) | feat(agent-hijack): return proven-undispatched recoveries to held | [sase-1qz.6.1](sase-1qz.6.1.md) | 2026-11-06 13:00:11 EST |
| sase | [`71011e1`](https://github.com/sase-org/sase/commit/71011e1e10771c589e2c6dd8219dd6a3d32a1040) | feat(hijack-recovery): finish keep-work settlement without user action | [sase-1qz.6.1](sase-1qz.6.1.md) | 2026-11-06 13:50:06 EST |
| sase--plans | [`sase--plans@aae102d`](https://github.com/sase-org/sase--plans/commit/aae102da76fa123a0b995886ad23fc2b211888a4) | docs(plans): mark hijack keep-work recovery epic plan done | [sase-1qz.6.1](sase-1qz.6.1.md) | 2026-11-06 13:53:01 EST |
| sase | [`f4ca45e`](https://github.com/sase-org/sase/commit/f4ca45edf82f5561bfeb5fecc8aa410c6df5c82b) | feat(hijack-recovery): add snapshot-verified restart and dismiss resolutions | [sase-1qz.7](sase-1qz.7.md) | 2026-11-06 15:09:55 EST |
| sase | [`a6ceb8b`](https://github.com/sase-org/sase/commit/a6ceb8bf930fee6654b74c7f5aba5c27d747226b) | feat(ace): add hijack recovery panel | [sase-1qz.9](sase-1qz.9.md) | 2026-11-06 16:34:33 EST |
| sase | [`039c4a8`](https://github.com/sase-org/sase/commit/039c4a858d7ced67bbb89699dcb3d737d9095b85) | feat(ace): wire hijack recovery panel Instruct and Edit through the prompt bar | [sase-1qz.10](sase-1qz.10.md) | 2026-11-06 16:57:29 EST |
| sase | [`8a9a993`](https://github.com/sase-org/sase/commit/8a9a993e0808570e5102b20fb91b2ac5c6499177) | fix(agent-hijack): land epic integration fixes and protect held runs from prune | [sase-1qz](README.md) | 2026-11-07 05:39:43 EST |
| sase--plans | [`sase--plans@2143da6`](https://github.com/sase-org/sase--plans/commit/2143da683f3557c54686319f09636779edb07b58) | chore(plans): mark agent\_hijack plan done | [sase-1qz](README.md) | 2026-11-07 05:40:55 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:18n][1] | Research user-facing behavior of agent hijack epic for a report | 1 |
| read-by | [agent:research.3a.cdx][2] | Check dependencies, active epic coverage, and alternatives to the leading task candidates | 1 |
| read-by | [agent:research.3a.cld][3] | Check scope of active athena epic to avoid conflicts when ranking task beads | 1 |
| read-by | [agent:research.3a.final][4] | Check active epic phase scopes for conflict screening of task bead recommendations | 1 |
| read-by | [agent:research.3a.gem][5] | Inspect scope and conflicts for research recommendation | 2 |
| read-by | [agent:research.3a.grk][6] | Need live epic scopes and high-impact candidate task details to rank work without colliding with in-flight epics | 1 |
| read-by | [agent:sase-1qz.10][7] | Need epic scope for phase context | 1 |
| read-by | [agent:sase-1qz.2--3][8] | Need epic DECISIONS and plan | 1 |
| read-by | [agent:sase-1qz.6.1.4.1.3][9] | Need final decisions governing this recovery epic | 1 |
| read-by | [agent:sase-1qz.7][10] | Need epic plan for phase 1qz.7 | 2 |
| read-by | [agent:sase-1rd.land][11] | Need ownership of marker-audit proposal and recovery integration scope | 1 |
| read-by | [agent:toobig-9d.test_agent_hijack_recover.0][12] | Check whether the active hijack recovery epic caused the unrelated macro terminology failure | 1 |
| read-by | [agent:toobig-9m.agent_artifact_run_trash.0][13] | Need epic scope to judge whether the hijack e2e test-waits failure belongs on the live Agent Hijack epic | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.18n/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3a.cdx/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3a.cld/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3a.final/README.md
[5]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3a.gem/README.md
[6]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3a.grk/README.md
[7]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.10/README.md
[8]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qz.2.md
[9]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.6.1.4.1.3/README.md
[10]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.7/README.md
[11]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rd.land.md
[12]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-9d.test_agent_hijack_recover.0/README.md
[13]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-9m.agent_artifact_run_trash.0/README.md

<!-- sase:referenced-by:end -->
