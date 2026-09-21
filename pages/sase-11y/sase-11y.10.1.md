# Bead: sase-11y.10.1 — Sunset legacy supervision paths, docs, and glossary

[Bead Pages](../README.md) / [sase-11y.10](sase-11y.10.md) / sase-11y.10.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.10](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.10.md) · **Assignee:** `sase-11y.10.1.land`
**Created:** 2026-09-20 13:56:11 EDT
**Plan:** [202609/service\_host\_sunset.md](https://github.com/sase-org/sase--plans/blob/main/202609/service_host_sunset.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/service_host_sunset.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | [bead:sase-152][2] | The service-host sunset epic whose plan never listed this sixth direct-start path |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/service_host_sunset.md
[2]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-152/README.md

<!-- sase:links:end -->

## Description

The sase service host is SASE's only supervisor of the scheduler: the service_host beta flag and every Off branch are gone, the ensure watchdog, the TUI direct-start path, the axe-start scope wrapper, the sase-update direct restart, and the Telegram rearm branch are deleted, `sase axe` is a documented alias of `sase scheduler`, the TUI tab id is `services`, and the docs and glossary describe the shipped system.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.10.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.10.1.land/README.md) | [sase-11y.10.1](sase-11y.10.1.md) | 0 |
