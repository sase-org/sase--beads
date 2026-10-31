# Bead: sase-1q4 — Explicit session/turn targets for fork and agent waits

[Bead Pages](../README.md) / sase-1q4

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5j.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5j.linker.w0.md) · **Assignee:** `sase-1q4.land`
**Created:** 2026-10-30 17:43:12 EDT
**Plan:** [202610/fork\_wait\_session\_turn\_target.md](https://github.com/sase-org/sase--plans/blob/main/202610/fork_wait_session_turn_target.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/fork_wait_session_turn_target.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 2 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/fork_wait_session_turn_target.md

<!-- sase:links:end -->

## Description

`#fork:<name>` reliably waits for the whole agent session, even when the parent is promoted into a session after the fork launched. Users can explicitly choose `session` or `turn` with `#fork(<name>, target=session|turn)`, `%wait(<name>, target=session|turn)`, `sase agent wait -T`, and the plan-gate coder options. Admission and injected fork history agree on the same bound target.

## Notes

[2026-10-31T07:12:00Z · toobig-8x.agent_loader_artifacts.0] DISCOVERED ISSUE: During artifact-loader split verification, sase tool run check ToolRun 8d8f3532b1b6f22323abb1bbd6d9da11 exited 1 after the scoped pytest lane. Seven NEW failures across tests/ace/tui/widgets/test_directive_arg_completion_wait.py, tests/ace/tui/widgets/test_directive_completion_candidates.py, tests/ace/tui/widgets/test_wait_directive_completion_interactions.py, tests/test_macro_directive_completion_parity.py, and tests/test_macro_directive_contract.py reflect assertions that omit the new %wait target= keyword: runtime completion candidates and argument hints now include target= while expected lists and contracts do not. This is directly tied to the %wait target implementation from phase sase-1q4.5; the artifact-loader diff does not touch these files. Evidence: ToolRun 8d8f3532b1b6f22323abb1bbd6d9da11.

[2026-10-31T11:34:05Z · sase-1q4.land] LAND TRIAGE of PROPOSED FOLLOW-UPs: (1) sase-1q4.2#1 federation_worker listener flake -> +1 on existing sase-1gz. (2) sase-1q4.2#2 test_guard_p95_latency load flake -> new flake task sase-1qf. (3) sase-1q4.2#3 test_reset_to_auto_matches_fresh_decision load flake -> new flake task sase-1qg. (4) sase-1q4.2#4 / sase-1q4.4#1 pager past_eof teardown AttributeError -> declined: fixed on master by e28334c45a; tests/pager/test_app_navigation.py -k past_eof passes (2 passed) at 4a4b6fede8. (5) sase-1q4.3#1 sudo_runner output_policy_none_keeps_ledger_empty -> +1 on existing sase-15h. (6) sase-1q4.3#2 quadratic _isolate_sase_home TempPathFactory.mktemp scans -> new bug task sase-1qe (small; root cause confirmed in _pytest make_numbered_dir). (7) sase-1q4.5#1 typed-agent %wait(..., target=turn) dropped by typed admission -> NOT a follow-up: epic-caused gap, kept as remaining sase-1q4 landing work (also affects explicit target=session on exact members; every LaunchApproval-approved agent-initiated launch goes through typed admission). (8) sase-1q4.5#2 / 1q4.6#1 / 1q4.9#2 / 1q4.11#1 agents_sync handle_agents_sync NameError -> declined: sase-1q7 closed, fixed by eec20f6ad5. (9) sase-1q4.8#1 ratchet sase-core-revision.txt -> declined: done in 4a4b6fede8 (pin dddcb0b7 = sase-core master HEAD, contains all four epic core commits). (10) sase-1q4.9#1 stale sase-1q4.4 --epic-symbol rows -> declined: rows already removed. Related pre-existing defect found while verifying (typed admission agent waits not session-aware, from sase-s6.3) recorded as DISCOVERED ISSUE on active epic sase-s6.

[2026-10-31T13:05:16Z · sase-1q4.land] CLOSE BLOCKED: sase bead close sase-1q4 refused because origin/master still has --epic-symbol sase-1q4(wait_targets_with_descriptions). The working-tree Justfile has that row deleted (land of unused wait_targets_with_descriptions facade). Close after this Justfile deletion reaches origin/master; do not --force. Verification already in /tmp/sase-1q4-close-note.txt and this agent's landing: sase-core check b846b1f80378a0597e5b27a485f80305; sase check 1ad7b595c705f632ecacbb6267c10e3a. Plan frontmatter set to status: done.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1q4.1](sase-1q4.1.md) | Promotion-aware bare-name fork waits | ✓ closed | medium | 2026-10-30 | 1 | 1 |
| [sase-1q4.10](sase-1q4.10.md) | Fork history follows the bound wait record | ✓ closed | medium | 2026-10-30 | 1 | 1 |
| [sase-1q4.11](sase-1q4.11.md) | The | ✓ closed | medium | 2026-10-30 | 1 | 1 |
| [sase-1q4.2](sase-1q4.2.md) | Rust wait-target vocabulary and pure rules | ✓ closed | medium | 2026-10-30 | 1 | 2 |
| [sase-1q4.3](sase-1q4.3.md) | Keyword-only macro inputs in sase-core | ✓ closed | medium | 2026-10-30 | 1 | 2 |
| [sase-1q4.4](sase-1q4.4.md) | Turn-pinned wait records and evaluation | ✓ closed | medium | 2026-10-30 | 1 | 1 |
| [sase-1q4.5](sase-1q4.5.md) | The %wait target= keyword end to end | ✓ closed | medium | 2026-10-30 | 1 | 2 |
| [sase-1q4.6](sase-1q4.6.md) | sase agent wait --target | ✓ closed | small | 2026-10-30 | 1 | 1 |
| [sase-1q4.7](sase-1q4.7.md) | Turn targets in plan-gate coder options | ✓ closed | medium | 2026-10-30 | 1 | 1 |
| [sase-1q4.8](sase-1q4.8.md) | Show and edit bound turns in the TUI | ✓ closed | medium | 2026-10-30 | 1 | 2 |
| [sase-1q4.9](sase-1q4.9.md) | Keyword-only macro inputs in sase | ✓ closed | medium | 2026-10-30 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1q4: Explicit session/turn targets for fork and agent waits [in_progress]"]
    n1["sase-1q4.1: Promotion-aware bare-name fork waits [closed]"]
    n2["sase-1q4.10: Fork history follows the bound wait record [closed]"]
    n3["sase-1q4.11: The [closed]"]
    n4["sase-1q4.2: Rust wait-target vocabulary and pure rules [closed]"]
    n5["sase-1q4.3: Keyword-only macro inputs in sase-core [closed]"]
    n6["sase-1q4.4: Turn-pinned wait records and evaluation [closed]"]
    n7["sase-1q4.5: The %wait target= keyword end to end [closed]"]
    n8["sase-1q4.6: sase agent wait --target [closed]"]
    n9["sase-1q4.7: Turn targets in plan-gate coder options [closed]"]
    n10["sase-1q4.8: Show and edit bound turns in the TUI [closed]"]
    n11["sase-1q4.9: Keyword-only macro inputs in sase [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n0 --> n9
    n0 --> n10
    n0 --> n11
    n1 -.-> n2
    n1 -.-> n6
    n2 -.-> n3
    n4 -.-> n6
    n5 -.-> n11
    n6 -.-> n7
    n6 -.-> n8
    n7 -.-> n3
    n7 -.-> n9
    n9 -.-> n10
    n11 -.-> n3
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1q4.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1q4.1.md) | [sase-1q4.1](sase-1q4.1.md) | 1 |
| [bbugyi200.athena.sase-1q4.10](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1q4.10.md) | [sase-1q4.10](sase-1q4.10.md) | 1 |
| [bbugyi200.athena.sase-1q4.11](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1q4.11.md) | [sase-1q4.11](sase-1q4.11.md) | 1 |
| [bbugyi200.athena.sase-1q4.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1q4.2/README.md) | [sase-1q4.2](sase-1q4.2.md) | 2 |
| [bbugyi200.athena.sase-1q4.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1q4.3.md) | [sase-1q4.3](sase-1q4.3.md) | 2 |
| [bbugyi200.athena.sase-1q4.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1q4.4/README.md) | [sase-1q4.4](sase-1q4.4.md) | 1 |
| [bbugyi200.athena.sase-1q4.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1q4.5/README.md) | [sase-1q4.5](sase-1q4.5.md) | 2 |
| [bbugyi200.athena.sase-1q4.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1q4.6/README.md) | [sase-1q4.6](sase-1q4.6.md) | 1 |
| [bbugyi200.athena.sase-1q4.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1q4.7.md) | [sase-1q4.7](sase-1q4.7.md) | 1 |
| [bbugyi200.athena.sase-1q4.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1q4.8.md) | [sase-1q4.8](sase-1q4.8.md) | 2 |
| [bbugyi200.athena.sase-1q4.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1q4.9/README.md) | [sase-1q4.9](sase-1q4.9.md) | 1 |
| [bbugyi200.athena.sase-1q4.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1q4.land.md) | [sase-1q4](README.md) | 3 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`167af33`](https://github.com/sase-org/sase/commit/167af335307c8e83fd3994c9f9081c326fbbf6a5) | feat(agent): promotion-aware bare-name fork waits | [sase-1q4.1](sase-1q4.1.md) | 2026-10-30 18:18:33 EDT |
| sase | [`3fcb69f`](https://github.com/sase-org/sase/commit/3fcb69fb3ca7ff8caed60edf06fc9da47647e422) | fix(fork): honor bound wait records in injected history | [sase-1q4.10](sase-1q4.10.md) | 2026-10-30 20:50:58 EDT |
| sase-core | [`sase-core@d7b00dd`](https://github.com/sase-org/sase-core/commit/d7b00dd7e2088d64a4cf335385856c17d44a3bed) | feat(wait\_target): add parse, effective-target, and NamedEnum vocabulary | [sase-1q4.2](sase-1q4.2.md) | 2026-10-30 21:29:22 EDT |
| sase | [`271632e`](https://github.com/sase-org/sase/commit/271632e9d7381398fa1503730ed91f4a03d23e00) | feat(macros): add wait\_target NamedEnum facade and frontmatter wiring | [sase-1q4.2](sase-1q4.2.md) | 2026-10-30 22:18:35 EDT |
| sase-core | [`sase-core@18ad5fd`](https://github.com/sase-org/sase-core/commit/18ad5fd6f4592af4d61ef8e8187514b032bec03f) | feat(macro): add keyword-only input metadata and binding rules | [sase-1q4.3](sase-1q4.3.md) | 2026-10-30 23:32:07 EDT |
| sase | [`cb230ad`](https://github.com/sase-org/sase/commit/cb230adb5e50eed82039be6112716fbde0f23808) | docs(macros): document keyword-only inputs and wait targets | [sase-1q4.3](sase-1q4.3.md) | 2026-10-31 00:15:21 EDT |
| sase | [`5ade788`](https://github.com/sase-org/sase/commit/5ade7889b22e276ff20e8d304424b88d7f2777e0) | feat(wait): pin explicit session/turn wait identity records | [sase-1q4.4](sase-1q4.4.md) | 2026-10-31 00:27:05 EDT |
| sase | [`9e6e2b3`](https://github.com/sase-org/sase/commit/9e6e2b329fd94b3b3bd3840c43d787de5b8b9a04) | feat(macros): mirror keyword-only inputs across sase Python | [sase-1q4.9](sase-1q4.9.md) | 2026-10-31 01:11:51 EDT |
| sase | [`ef4bc2b`](https://github.com/sase-org/sase/commit/ef4bc2b34a6b844fea782d6d5ccd97f35471a316) | feat(agent): add -T/--target session\|turn to sase agent wait | [sase-1q4.6](sase-1q4.6.md) | 2026-10-31 01:43:29 EDT |
| sase-core | [`sase-core@80f5af4`](https://github.com/sase-org/sase-core/commit/80f5af40f4482f10187f207082249dd329cf329c) | feat(editor): parse and diagnose %wait target=session\|turn | [sase-1q4.5](sase-1q4.5.md) | 2026-10-31 02:37:20 EDT |
| sase | [`eed4ef9`](https://github.com/sase-org/sase/commit/eed4ef925b351e7aa9770dddbee969b79ec15589) | feat(macro): accept %wait(..., target=session\|turn) | [sase-1q4.5](sase-1q4.5.md) | 2026-10-31 02:38:38 EDT |
| sase | [`1b01062`](https://github.com/sase-org/sase/commit/1b01062d2e7bec72d3c312ee19a7772247164820) | feat(plan-gates): carry turn=\<agent\> waits through coder options | [sase-1q4.7](sase-1q4.7.md) | 2026-10-31 03:43:16 EDT |
| sase | [`dcee7f1`](https://github.com/sase-org/sase/commit/dcee7f11e9342935619dfbd85d670c7dfff1c98e) | feat(fork): bind explicit wait targets and structured refs | [sase-1q4.11](sase-1q4.11.md) | 2026-10-31 03:58:25 EDT |
| sase-core | [`sase-core@dddcb0b`](https://github.com/sase-org/sase-core/commit/dddcb0b712600b5635df5bed91e1220c0b2bd31d) | feat(agent-scan): project wait\_turn\_bindings on scan wire | [sase-1q4.8](sase-1q4.8.md) | 2026-10-31 07:10:33 EDT |
| sase | [`4a4b6fe`](https://github.com/sase-org/sase/commit/4a4b6fede82aff9cdab6a29a8cfc1d993cf4dadb) | feat(tui): surface and edit bound turn waits | [sase-1q4.8](sase-1q4.8.md) | 2026-10-31 07:11:46 EDT |
| sase-core | [`sase-core@32c66dd`](https://github.com/sase-org/sase-core/commit/32c66ddf2b8b0cc1456cdea79a36dcd8202cd24d) | feat(agent-launch): forward explicit %wait targets through typed admission | [sase-1q4](README.md) | 2026-10-31 09:07:34 EDT |
| sase | [`9b880fb`](https://github.com/sase-org/sase/commit/9b880fbfdfc3a3004a3149b853b2981113bed190) | feat(wait): keep typed-admission %wait targets for the runner | [sase-1q4](README.md) | 2026-10-31 09:08:59 EDT |
| sase--plans | [`sase--plans@aabf9dd`](https://github.com/sase-org/sase--plans/commit/aabf9dd666b266d3dc1e68c3e6ec399cec3f9cc9) | chore(plans): mark fork\_wait\_session\_turn\_target epic plan done | [sase-1q4](README.md) | 2026-10-31 09:10:23 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1q4.2][1] | Need parent epic DECISIONS and remaining phases | 2 |
| read-by | [agent:toobig-8x.agent_loader_artifacts.0][2] | Need to assess whether wait target completion failures belong to this active epic | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1q4.2/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-8x.agent_loader_artifacts.0/README.md

<!-- sase:referenced-by:end -->
