# Bead: sase-ko.4 — Enable the idle guard on bugyi\_chop\_ci\_watch

[Bead Pages](../README.md) / [sase-ko](README.md) / sase-ko.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.yx](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.yx/README.md) · **Assignee:** `sase-ko.4` · **Size:** xsmall
**Created:** 2026-08-12 16:00:20 EDT
**Plan:** [202608/chop\_agent\_runners\_guard.md](https://github.com/sase-org/sase--plans/blob/main/202608/chop_agent_runners_guard.md)

## Description

ci-watch-idle: add `inhibit_if: {agent_runners: {max: 0}}` to the `ci_watch` chop in the chezmoi-managed config, refresh its description body, and verify the live runtime accepts and honors it.

## Dependencies

- **Depends on:** [sase-ko.2](sase-ko.2.md) ✓ · ⧖ 2026-08-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ko.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ko.4/README.md) | [sase-ko.4](sase-ko.4.md) | 0 |
