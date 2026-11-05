# Bead: sase-1qz — Agent Hijack: stop a stalled agent, keep its work, recover in one keypress

[Bead Pages](../README.md) / sase-1qz

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.research.33.linker.w0` · **Assignee:** `sase-1qz.land`
**Created:** 2026-11-02 17:42:13 EST
**Plan:** [202611/agent\_hijack.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_hijack.md)

## Description

A user can hijack a stalled sase agent (,k, the kill dialog's h, or `sase agent hijack NAME`). Its process tree stops, but its workspace claim, Agents-tab node, and evidence stay. The node shows a ⏏ HIJACKED status, and <enter> opens a single-keypress recovery panel: escalate to a smarter model, continue, or instruct in the same workspace; restart or edit from a fresh workspace after a verified snapshot; view the diff, open a shell, or dismiss. Every path is durable, exactly-once, and fails closed so work is never silently lost.

## Notes

[2026-11-05T01:37:08Z · sase-1ra.6--4] DISCOVERED ISSUE: sase tool run check 0ea4d12896bf1d703ba1b18ecdb64ea3 on HEAD 02e93fd failed tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed. The audit reports five unreviewed sites in src/sase/agent/hijack/recover_subject.py and recover_settle.py, introduced by commit 8462195314 (feat(agent): exactly-once hijack recovery launch and settlement). This is within the active Agent Hijack recovery source scope; the same audit node is tracked by sase-1by, and this post-close recurrence was corroborated there.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1qz.1](sase-1qz.1.md) | sase-core: hijack statuses, ledger wire, and eligibility | ✓ closed | medium | 2026-11-02 | 1 | 2 |
| [sase-1qz.10](sase-1qz.10.md) | Instruct and Edit through the prompt bar | ◐ in_progress | medium | 2026-11-02 | 1 | 0 |
| [sase-1qz.11](sase-1qz.11.md) | Remove the flag, document, and prove it end to end | ◐ in_progress | medium | 2026-11-02 | 1 | 0 |
| [sase-1qz.2](sase-1qz.2.md) | sase-core: escalation policy, continuation prompt, and config | ✓ closed | medium | 2026-11-02 | 1 | 2 |
| [sase-1qz.3](sase-1qz.3.md) | Runner settlement that keeps custody | ✓ closed | medium | 2026-11-02 | 1 | 1 |
| [sase-1qz.4](sase-1qz.4.md) | The stop protocol and \`sase agent hijack\` | ✓ closed | medium | 2026-11-02 | 1 | 1 |
| [sase-1qz.5](sase-1qz.5.md) | Every release path respects a hijack | ✓ closed | medium | 2026-11-02 | 1 | 1 |
| [sase-1qz.6](sase-1qz.6.md) | Keep-the-work recovery (Escalate, Switch, Continue, Instruct) | ◐ in_progress | large | 2026-11-02 | 0 | 0 |
| [sase-1qz.7](sase-1qz.7.md) | Start-over and leave recovery (Restart, Edit backend, Dismiss) | ◐ in_progress | medium | 2026-11-02 | 1 | 0 |
| [sase-1qz.8](sase-1qz.8.md) | Agents-tab rendering and the ,k way in | ✓ closed | medium | 2026-11-02 | 1 | 1 |
| [sase-1qz.9](sase-1qz.9.md) | The recovery panel | ◐ in_progress | medium | 2026-11-02 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1qz: Agent Hijack: stop a stalled agent, keep its work, recover in one keypress [in_progress]"]
    n1["sase-1qz.1: sase-core: hijack statuses, ledger wire, and eligibility [closed]"]
    n2["sase-1qz.10: Instruct and Edit through the prompt bar [in_progress]"]
    n3["sase-1qz.11: Remove the flag, document, and prove it end to end [in_progress]"]
    n4["sase-1qz.2: sase-core: escalation policy, continuation prompt, and config [closed]"]
    n5["sase-1qz.3: Runner settlement that keeps custody [closed]"]
    n6["sase-1qz.4: The stop protocol and `sase agent hijack` [closed]"]
    n7["sase-1qz.5: Every release path respects a hijack [closed]"]
    n8["sase-1qz.6: Keep-the-work recovery (Escalate, Switch, Continue, Instruct) [in_progress]"]
    n9["sase-1qz.6.1: Complete keep-work recovery for hijacked agents [in_progress]"]
    n10["sase-1qz.6.1.1: Rust recovery transaction and preview contracts [closed]"]
    n11["sase-1qz.6.1.2: Read-only recovery preview and continuation context [closed]"]
    n12["sase-1qz.6.1.3: Same-workspace launch with mandatory inheritance [closed]"]
    n13["sase-1qz.6.1.4: Exactly-once recovery launch and settlement [in_progress]"]
    n14["sase-1qz.6.1.4.1: Complete the production keep-work recovery transaction [in_progress]"]
    n15["sase-1qz.6.1.4.1.1: Rust execution validation and confirmation contract [closed]"]
    n16["sase-1qz.6.1.4.1.2: Prepare and pin the real recovery prompt [in_progress]"]
    n17["sase-1qz.6.1.4.1.3: Submit and resume the pinned recovery request [in_progress]"]
    n18["sase-1qz.6.1.4.1.4: Prove required inheritance before provider execution [in_progress]"]
    n19["sase-1qz.6.1.4.1.5: Confirm the actual successor and fail safely [in_progress]"]
    n20["sase-1qz.6.1.4.1.6: Verify the production transaction and closure evidence [in_progress]"]
    n21["sase-1qz.6.1.5: Crash repair and successor-following waits [in_progress]"]
    n22["sase-1qz.6.1.6: Recovery command, durable operation, and integration coverage [in_progress]"]
    n23["sase-1qz.6.1.7: Verify and complete the assigned recovery phase [in_progress]"]
    n24["sase-1qz.7: Start-over and leave recovery (Restart, Edit backend, Dismiss) [in_progress]"]
    n25["sase-1qz.8: Agents-tab rendering and the ,k way in [closed]"]
    n26["sase-1qz.9: The recovery panel [in_progress]"]
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
| [bbugyi200.athena.sase-1qz.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.10/README.md) | [sase-1qz.10](sase-1qz.10.md) | 0 |
| [bbugyi200.athena.sase-1qz.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.11/README.md) | [sase-1qz.11](sase-1qz.11.md) | 0 |
| [bbugyi200.athena.sase-1qz.6.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.6.1.2/README.md) | [sase-1qz.6.1.2](sase-1qz.6.1.2.md) | 0 |
| [bbugyi200.athena.sase-1qz.6.1.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qz.6.1.4.md) | [sase-1qz.6.1.4](sase-1qz.6.1.4.md) | 1 |
| [bbugyi200.athena.sase-1qz.6.1.4.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.6.1.4.1.1/README.md) | [sase-1qz.6.1.4.1.1](sase-1qz.6.1.4.1.1.md) | 1 |
| [bbugyi200.athena.sase-1qz.6.1.4.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.6.1.4.1.2/README.md) | [sase-1qz.6.1.4.1.2](sase-1qz.6.1.4.1.2.md) | 0 |
| [bbugyi200.athena.sase-1qz.6.1.4.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.6.1.4.1.3/README.md) | [sase-1qz.6.1.4.1.3](sase-1qz.6.1.4.1.3.md) | 0 |
| [bbugyi200.athena.sase-1qz.6.1.4.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.6.1.4.1.4/README.md) | [sase-1qz.6.1.4.1.4](sase-1qz.6.1.4.1.4.md) | 0 |
| [bbugyi200.athena.sase-1qz.6.1.4.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.6.1.4.1.5/README.md) | [sase-1qz.6.1.4.1.5](sase-1qz.6.1.4.1.5.md) | 0 |
| [bbugyi200.athena.sase-1qz.6.1.4.1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.6.1.4.1.6/README.md) | [sase-1qz.6.1.4.1.6](sase-1qz.6.1.4.1.6.md) | 0 |
| [bbugyi200.athena.sase-1qz.6.1.4.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.6.1.4.1.land/README.md) | [sase-1qz.6.1.4.1](sase-1qz.6.1.4.1.md) | 0 |
| [bbugyi200.athena.sase-1qz.6.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.6.1.5/README.md) | [sase-1qz.6.1.5](sase-1qz.6.1.5.md) | 0 |
| [bbugyi200.athena.sase-1qz.6.1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.6.1.6/README.md) | [sase-1qz.6.1.6](sase-1qz.6.1.6.md) | 0 |
| [bbugyi200.athena.sase-1qz.6.1.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.6.1.7/README.md) | [sase-1qz.6.1.7](sase-1qz.6.1.7.md) | 0 |
| [bbugyi200.athena.sase-1qz.6.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.6.1.land/README.md) | [sase-1qz.6.1](sase-1qz.6.1.md) | 0 |
| [bbugyi200.athena.sase-1qz.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.7/README.md) | [sase-1qz.7](sase-1qz.7.md) | 0 |
| [bbugyi200.athena.sase-1qz.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.9/README.md) | [sase-1qz.9](sase-1qz.9.md) | 0 |
| [bbugyi200.athena.sase-1qz.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.land/README.md) | [sase-1qz](README.md) | 0 |

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

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.3a.cdx][1] | Check dependencies, active epic coverage, and alternatives to the leading task candidates | 1 |
| read-by | [agent:research.3a.cld][2] | Check scope of active athena epic to avoid conflicts when ranking task beads | 1 |
| read-by | [agent:research.3a.final][3] | Check active epic phase scopes for conflict screening of task bead recommendations | 1 |
| read-by | [agent:research.3a.gem][4] | Inspect scope and conflicts for research recommendation | 2 |
| read-by | [agent:research.3a.grk][5] | Need live epic scopes and high-impact candidate task details to rank work without colliding with in-flight epics | 1 |
| read-by | [agent:sase-1qz.2--3][6] | Need epic DECISIONS and plan | 1 |
| read-by | [agent:toobig-9d.test_agent_hijack_recover.0][7] | Check whether the active hijack recovery epic caused the unrelated macro terminology failure | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3a.cdx/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3a.cld/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3a.final/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3a.gem/README.md
[5]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3a.grk/README.md
[6]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qz.2.md
[7]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-9d.test_agent_hijack_recover.0/README.md

<!-- sase:referenced-by:end -->
