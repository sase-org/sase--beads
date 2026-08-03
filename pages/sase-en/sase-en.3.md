# Bead: sase-en.3 — Resolve bead detail from one bead-store read

[Bead Pages](../README.md) / [sase-en](README.md) / sase-en.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sl.f1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sl.f1/README.md) · **Assignee:** `sase-en.3` · **Size:** medium
**Created:** 2026-08-03 12:40:23 UTC
**Plan:** [202608/bead\_show\_speed.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_show_speed.md)

## Description

store: add a single-pass bead detail read to the Rust core and its binding so sase bead show reduces the event store once instead of three times, and route the Python detail resolver through it.

## Dependencies

- **Blocks:** [sase-en.4](sase-en.4.md) ◐
