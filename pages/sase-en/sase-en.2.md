# Bead: sase-en.2 — Build only the invoked command's subparser

[Bead Pages](../README.md) / [sase-en](README.md) / sase-en.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sl.f1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sl.f1/README.md) · **Assignee:** `sase-en.2` · **Size:** medium
**Created:** 2026-08-03 12:40:08 UTC
**Plan:** [202608/bead\_show\_speed.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_show_speed.md)

## Description

parser: give create_parser an opt-in only= hint so a normal sase <cmd> run registers just that command's subparser, drive it from a single shared command registry so the full and narrow paths cannot drift, and stop parser_artifact from importing the heavy artifact facade for one tuple of argparse choices.

## Dependencies

- **Blocks:** [sase-en.4](sase-en.4.md) ◐
