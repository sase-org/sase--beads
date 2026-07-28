# Bead: sase-5r.4 — Phase 4 — Migrate sase to the published package

[Bead Pages](../README.md) / [sase-5r](README.md) / sase-5r.4

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-5r.4`
**Created:** 2026-07-12 00:04:47 UTC
**Plan:** [202607/toolong\_extraction.md](https://github.com/sase-org/sase--plans/blob/main/202607/toolong_extraction.md)

## Description

Repository/worktree requirement: perform all work for this bead in ~/projects/github/bbugyi200/toolong/. This directory is the existing local git repository whose remote points to bbugyi200/toolong; use it directly and do not create or use another checkout.

## Notes

SASE now installs toobig>=0.1.0,<0.2.0 from PyPI and uses the toobig binary/Just target/xprompt integration. just install and just toobig pass; all 16,733 tests pass. just check passes formatting and every lint stage including lint (toobig), then stops at unrelated pre-existing init-memory drift that cannot be changed without explicit user approval.

## Dependencies

- **Depends on:** [sase-5r.3](sase-5r.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-5r.4--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-5r.4.md#member-1) | [sase-5r.4](sase-5r.4.md) | 0 |
