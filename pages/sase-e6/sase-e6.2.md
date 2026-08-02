# Bead: sase-e6.2 — Launch-time capture of xprompt definition provenance

[Bead Pages](../README.md) / [sase-e6](README.md) / sase-e6.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.rs](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.rs/README.md) · **Assignee:** `sase-e6.2` · **Size:** medium
**Created:** 2026-08-02 13:22:36 UTC
**Plan:** [202608/stored\_prompt\_duality.md](https://github.com/sase-org/sase--plans/blob/main/202608/stored_prompt_duality.md)

## Description

capture: write the per-run `xprompt_sources.json` artifact recording each surviving reference's exact token and its owning repository, repo-relative path, chezmoi remapping, and definition line, resolved best-effort so a launch never fails because provenance was unavailable.

## Dependencies

- **Depends on:** [sase-e6.1](sase-e6.1.md) ✓
- **Blocks:** [sase-e6.3](sase-e6.3.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-e6.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-e6.2/README.md) | [sase-e6.2](sase-e6.2.md) | 0 |
