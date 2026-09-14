# Bead: sase-zr — Make gate approval and notification dismissal respond promptly

[Bead Pages](../README.md) / sase-zr

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.athena.0js` · **Assignee:** `sase-zr.land`
**Created:** 2026-09-12 05:06:12 EDT
**Plan:** [202609/prompt\_gate\_approval.md](https://github.com/sase-org/sase--plans/blob/main/202609/prompt_gate_approval.md)

## Description

Publish durable tale and epic approval decisions and refresh ACE and Telegram promptly without waiting for archive publication or successor launch, while preserving execution recovery and exactly-once follow-up ownership.

## Notes

[2026-09-14T16:14:51Z · 0kp] DISCOVERED ISSUE: Telegram inbound is completely dead on athena since 2026-09-13 ~19:12 EDT — the supervised long-poll receiver introduced by sase-zr.5 (sase-telegram 829e738) can never launch. receiver.py submits argv ['sase_chop_tg_inbound','--receiver'] through sase.procs.submit_proc_request, but the proc supervisor resolves that bare console-script name against the host services' PATH, which does not include the uv tool venv bin (~/.local/share/uv/tools/sase/bin) — the script's only location ('which sase_chop_tg_inbound' fails; lumberjack/gateway PATH checked via /proc/<pid>/environ). Every ~5s re-arm therefore dies at spawn: proc rows show status=error, termination_reason=launch-failure, message "could not start command: [Errno 2] No such file or directory: 'sase_chop_tg_inbound'" (e.g. proc fybcqbbeppx1, log ~/.sase/procs/logs/fybcqbbeppx1.log), flooding ~/.sase/procs/procs.jsonl with ~1 failed row per 7s. update_offset.txt has not advanced since 2026-09-13 19:12, so every Telegram button press since then (incl. today's plan-approval attempts) is never fetched. Tests cannot catch this by design: ensure_receiver_running lets tests substitute a harmless argv, so the real console-script argv is never exercised. Also relevant to sase-zr.6's partial-command verification: plan gate plan/c7d980c0-f436-405c-b0a8-382ceb32676c holds an incomplete attempt (journal attempt_started 2026-09-13T16:42 EDT, approve+commit, empty input digests, no terminal event) and an identical Telegram resubmission would raise partial_attempt with no Telegram resume/restart affordance. Note: no sase-zr agent is currently running, so a remediation plan is being proposed separately for the receiver launch fix; sase-zr.6 should still verify the receiver lifecycle end-to-end on a real host.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-zr.1](sase-zr.1.md) | Measure approval stages and replace full-history gate lookup | ✓ closed | medium | 2026-09-12 | 1 | 2 |
| [sase-zr.2](sase-zr.2.md) | Separate durable decision acceptance from slow execution | ✓ closed | medium | 2026-09-12 | 1 | 3 |
| [sase-zr.3](sase-zr.3.md) | Apply decision and notification changes through ACE's fast path | ✓ closed | medium | 2026-09-12 | 1 | 1 |
| [sase-zr.4](sase-zr.4.md) | Decouple Telegram acknowledgements and cleanup from gate execution | ✓ closed | medium | 2026-09-12 | 1 | 1 |
| [sase-zr.5](sase-zr.5.md) | Remove Telegram's periodic polling delay | ✓ closed | medium | 2026-09-12 | 1 | 1 |
| [sase-zr.6](sase-zr.6.md) | Verify latency, recovery, and coordinated rollout | ✓ closed | medium | 2026-09-12 | 1 | 2 |

## Lineage

```mermaid
flowchart TD
    n0["sase-zr: Make gate approval and notification dismissal respond promptly [in_progress]"]
    n1["sase-zr.1: Measure approval stages and replace full-history gate lookup [closed]"]
    n2["sase-zr.2: Separate durable decision acceptance from slow execution [closed]"]
    n3["sase-zr.3: Apply decision and notification changes through ACE's fast path [closed]"]
    n4["sase-zr.4: Decouple Telegram acknowledgements and cleanup from gate execution [closed]"]
    n5["sase-zr.5: Remove Telegram's periodic polling delay [closed]"]
    n6["sase-zr.6: Verify latency, recovery, and coordinated rollout [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n1 -.-> n2
    n2 -.-> n3
    n2 -.-> n4
    n3 -.-> n6
    n4 -.-> n5
    n5 -.-> n6
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-zr.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-zr.1.md) | [sase-zr.1](sase-zr.1.md) | 2 |
| [bbugyi200.apollo.sase-zr.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-zr.2.md) | [sase-zr.2](sase-zr.2.md) | 3 |
| [bbugyi200.apollo.sase-zr.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-zr.3/README.md) | [sase-zr.3](sase-zr.3.md) | 1 |
| [bbugyi200.apollo.sase-zr.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-zr.4/README.md) | [sase-zr.4](sase-zr.4.md) | 1 |
| [bbugyi200.apollo.sase-zr.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-zr.5.md) | [sase-zr.5](sase-zr.5.md) | 1 |
| [bbugyi200.apollo.sase-zr.6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-zr.6.md) | [sase-zr.6](sase-zr.6.md) | 2 |
| [bbugyi200.apollo.sase-zr.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-zr.land/README.md) | [sase-zr](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`93f3d58`](https://github.com/sase-org/sase/commit/93f3d58911b9968575bd08676c65b3577e01e016) | feat(gate-shell): add indexed gate-shell-by-gate-id lookup with telemetry | [sase-zr.1](sase-zr.1.md) | 2026-09-13 19:12:59 EDT |
| sase-core | [`sase-core@682dbec`](https://github.com/sase-org/sase-core/commit/682dbeca5967c2fd210597c6c9a6df6b90991a1b) | feat(agent\_scan): add core index module and Python bindings for gate-shell lookup | [sase-zr.1](sase-zr.1.md) | 2026-09-13 19:19:11 EDT |
| sase | [`c8152f4`](https://github.com/sase-org/sase/commit/c8152f4978272b6c6cce30ec9f23470926fff144) | feat(gate-shell): accept gate decisions durably before slow execution | [sase-zr.2](sase-zr.2.md) | 2026-09-13 21:51:48 EDT |
| sase-core | [`sase-core@809f45e`](https://github.com/sase-org/sase-core/commit/809f45ed26a656d8fb8152afb1f077dd6070f022) | feat(gate\_decision): add durable decision-acceptance policy and binding | [sase-zr.2](sase-zr.2.md) | 2026-09-13 21:53:32 EDT |
| sase | [`d2ba89c`](https://github.com/sase-org/sase/commit/d2ba89cb420aea18ac27b4192e6bb49731729cbd) | fix(monitor): keep lookup helpers private | [sase-zr.2](sase-zr.2.md) | 2026-09-14 08:59:17 EDT |
| sase-telegram | [`sase-telegram@c34432c`](https://github.com/sase-org/sase-telegram/commit/c34432cac2dcf8fb27a8139c877446350607b89b) | feat(gate,inbound): submit Telegram gate answers through the shared supervised proc | [sase-zr.4](sase-zr.4.md) | 2026-09-14 09:41:27 EDT |
| sase-telegram | [`sase-telegram@829e738`](https://github.com/sase-org/sase-telegram/commit/829e73801ba60f0ac8611c30aa8f0c97a95c5e56) | feat(inbound): replace polling gap with a supervised long-poll receiver | [sase-zr.5](sase-zr.5.md) | 2026-09-14 10:28:38 EDT |
| sase | [`ae6afe9`](https://github.com/sase-org/sase/commit/ae6afe968541d24496496b5c82755f381435afc7) | feat(ace): submit plan gates through durable answers | [sase-zr.3](sase-zr.3.md) | 2026-09-14 14:16:18 EDT |
| sase | [`7f7700d`](https://github.com/sase-org/sase/commit/7f7700d030c3806b56e326db9567cfa9345cc2f5) | docs(notifications): document gate decision receipts, rollout order, and latency probes | [sase-zr.6](sase-zr.6.md) | 2026-09-14 19:28:12 EDT |
| sase-telegram | [`sase-telegram@90815d2`](https://github.com/sase-org/sase-telegram/commit/90815d20c1b5223df24e244aa58701a54b125643) | feat(telegram): acknowledge callback queries before durable gate submission | [sase-zr.6](sase-zr.6.md) | 2026-09-14 19:42:25 EDT |
