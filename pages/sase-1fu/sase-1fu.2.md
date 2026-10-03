# Bead: sase-1fu.2 — Drain provider JSONL promptly and preserve UTF-8

[Bead Pages](../README.md) / [sase-1fu](README.md) / sase-1fu.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vt](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vt.md) · **Assignee:** `sase-1fu.2` · **Size:** medium
**Created:** 2026-10-03 15:03:53 EDT
**Plan:** [202610/muse\_reply\_streaming.md](https://github.com/sase-org/sase--plans/blob/main/202610/muse_reply_streaming.md)

## Description

jsonl-reader: replace buffered text reads in the shared JSONL transport with bounded nonblocking byte reads and incremental decoding, preserving stderr, partial records, EOF, and completion-watchdog semantics across providers.

## Dependencies

- **Blocks:** [sase-1fu.4](sase-1fu.4.md) ◐ · ⧖ 2026-10-03

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1fu.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1fu.2/README.md) | [sase-1fu.2](sase-1fu.2.md) | 0 |
