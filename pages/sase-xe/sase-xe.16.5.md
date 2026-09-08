# Bead: sase-xe.16.5 — Third-party provider imports follow the finalizers trust model

[Bead Pages](../README.md) / [sase-xe.16](sase-xe.16.md) / sase-xe.16.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08c](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08c.md) · **Assignee:** `sase-xe.16.5` · **Size:** medium
**Created:** 2026-09-08 10:21:35 EDT
**Plan:** [202609/remote\_dispatch\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_completion.md)

## Description

provider-isolation: today collect_dispatch_providers and helpers eagerly ep.load() third-party entry points in-process, which the parent plan's dispatch-plugins phase explicitly forbade. Inventory entry points as metadata in-process; import provider code only inside a bounded, separately supervised helper subprocess with a deadline and cancellation, and only for the selected provider, following the finalizers loading model. A provider exception or timeout affects only its machines. Decide the dispatch_connection_plan hook: add it for third-party providers or record an explicit deferral decision (builtin providers derive plans from enrolled machine records and do not need it).

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.16.5/README.md) | [sase-xe.16.5](sase-xe.16.5.md) | 0 |
