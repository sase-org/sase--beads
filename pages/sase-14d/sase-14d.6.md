# Bead: sase-14d.6 — The two requested configurations

[Bead Pages](../README.md) / [sase-14d](README.md) / sase-14d.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0o7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0o7.md) · **Assignee:** `sase-14d.6` · **Size:** small
**Created:** 2026-09-20 13:11:36 EDT · **Closed:** 2026-09-20 17:04:59 EDT
**Plan:** [202609/notification\_delivery\_rules.md](https://github.com/sase-org/sase--plans/blob/main/202609/notification_delivery_rules.md)

## Description

chezmoi-config: add the global task-bead suppression rule to sase.yml and the sound-file rule to sase_kellys_mbp.yml in the chezmoi repo, after confirming the shipping build understands the key.

## Notes

[2026-09-20T21:04:59Z · sase-14d.6] Added quiet-task-beads (match tab: beads, toast false, sound none) under ace: in chezmoi home/dot_config/sase/sase.yml and mbp-chime (sound Glass.aiff) in sase_kellys_mbp.yml. Both files parse and validate against src/sase/config/sase.schema.json (ace.notification_rules present); installed athena sase (0.17.1+986.g4255afbb0) ships 'sase notify rules'. Not applied via chezmoi apply and not verified on kellys_mbp; apply only once a build carrying core-rules..observability is installed there, then check 'sase notify rules' / 'sase doctor' / 'sase notify rules --explain <TaskTriage id>'.

## Dependencies

- **Depends on:** [sase-14d.2](sase-14d.2.md) ✓ · ⧖ 2026-09-20
- **Depends on:** [sase-14d.5](sase-14d.5.md) ✓ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-14d.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14d.6/README.md) | [sase-14d.6](sase-14d.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| chezmoi | [`chezmoi@f7da682`](https://github.com/bbugyi200/dotfiles/commit/f7da68203d0b2d2568496fbac7f7c4497eb45870) | feat(sase): add notification delivery rules for task beads and kellys\_mbp chime | [sase-14d.6](sase-14d.6.md) | 2026-09-20 17:05:55 EDT |
