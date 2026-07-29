# Bead: sase-av.4 — Recognize and expand artifact references at launch

[Bead Pages](../README.md) / [sase-av](README.md) / sase-av.4

**Status:** ◐ in_progress · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-av.4` · **Size:** medium
**Created:** 2026-07-29 16:48:01 UTC
**Plan:** [202607/artifact\_refs\_and\_prompt\_bar.md](https://github.com/sase-org/sase--plans/blob/main/202607/artifact_refs_and_prompt_bar.md)

## Description

prompt-grammar: recognize `@<kind>:<payload>` references in launched prompts through the core scanner and expand them per kind — documents, chats, and artifact files to real paths, commits and bugs to their locators — before file-reference processing, failing the launch clearly when a known-kind reference does not resolve.

## Dependencies

- **Depends on:** [sase-av.2](sase-av.2.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-av.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-av.4/README.md) | [sase-av.4](sase-av.4.md) | 0 |
