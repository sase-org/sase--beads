# Bead: sase-11y.9 — Live migration on athena and apollo

[Bead Pages](../README.md) / [sase-11y](README.md) / sase-11y.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0m3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0m3.md) · **Assignee:** `sase-11y.9` · **Size:** medium
**Created:** 2026-09-16 14:42:06 EDT · **Closed:** 2026-09-19 10:59:36 EDT
**Plan:** [202609/service\_host\_1.md](https://github.com/sase-org/sase--plans/blob/main/202609/service_host_1.md)

## Description

rollout: install the platform unit on both machines, migrate the hand-written gateway units and the Telegram receiver per the runbook, and run the restart-with-live-work release gate before the new host is declared authoritative.

## Notes

[2026-09-19T14:58:05Z · sase-11y.9] PROPOSED FOLLOW-UP: telegram_receiver spawn uses bare sase_job_tg_inbound which is only in uv tools bin — host failed ENOENT until that dir was prepended to captured PATH; resolve plugin commands to absolute paths or install job scripts on ~/.local/bin

[2026-09-19T14:58:39Z · sase-11y.9] PROPOSED FOLLOW-UP: scheduler job processes stay in the sase.service cgroup so mixed KillMode SIGKILLs in-flight jobs on host restart (journal: sase_job_artifact_*); job-launched agents that had already escaped survived

[2026-09-19T14:59:06Z · sase-11y.9] PROPOSED FOLLOW-UP: host-owned telegram_receiver does not share the legacy concurrency key telegram-receiver:<chat_id>, so a leftover legacy receiver and the host child can both consume getUpdates unless the legacy proc is killed first

[2026-09-19T14:59:36Z · sase-11y.9] Live-migrated athena and apollo onto sase.service. Verified: service_host enabled; sase.service active/enabled and sase-gateway.service retired on both; curl 127.0.0.1:7629/api/v1/health ok; controller hello to apollo ok; gateway+scheduler running on both (overlay enablement); telegram_receiver running only on athena after killing mzys6fde9cxa and dropping tg_inbound (exactly one --receiver, ESTABLISHED Telegram socket); chezmoi gateway unit removed. Restart gate: live agents (sase-13i.2, 0nq--2, 0nr--code, this phase agent) survived host restart; oneshot ybcj425p85h7 supervisor stayed up across the last restart; systemd-run --scope sleep survived an earlier restart; athena captured PATH resolves claude/codex/grok/agy/opencode/muse/qwen plus sase_job_tg_inbound. Did not close sase-11y.

## Dependencies

- **Blocks:** [sase-11y.10](sase-11y.10.md) ◐ · ⧖ 2026-09-16
- **Depends on:** [sase-11y.5](sase-11y.5.md) ✓ · ⧖ 2026-09-16
- **Depends on:** [sase-11y.6](sase-11y.6.md) ✓ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.9/README.md) | [sase-11y.9](sase-11y.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| chezmoi | [`chezmoi@2f03d01`](https://github.com/bbugyi200/dotfiles/commit/2f03d0158bc0c076affabbdba2a16de8e9d16115) | feat(sase): migrate gateway and telegram onto the service host | [sase-11y.9](sase-11y.9.md) | 2026-09-19 11:01:35 EDT |
