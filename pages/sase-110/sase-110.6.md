# Bead: sase-110.6 — Machine-targeted and remote-raised sudo over ssh -t

[Bead Pages](../README.md) / [sase-110](README.md) / sase-110.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0kl](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0kl.md) · **Assignee:** `sase-110.6` · **Size:** large
**Created:** 2026-09-14 11:33:18 EDT
**Plan:** [202609/agent\_sudo\_requests.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_sudo_requests.md)

## Description

remote-sudo: add ssh targets to machine records, machine-targeted requests executed over ssh -t with a sealed manifest, remote-raised requests answered via the ssh -t relay from local ACE, and deny-only behavior on every non-TTY surface.

## Dependencies

- **Depends on:** [sase-110.4](sase-110.4.md) ✓ · ⧖ 2026-09-14
- **Blocks:** [sase-110.8](sase-110.8.md) ◐ · ⧖ 2026-09-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-110.6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-110.6.md) | [sase-110.6](sase-110.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7a1a1ca`](https://github.com/sase-org/sase/commit/7a1a1ca3e46554fd99035617484773af8b57cf6e) | feat(sudo): support remote sudo handoff over ssh | [sase-110.6](sase-110.6.md) | 2026-09-15 09:33:47 EDT |
