# Bead: sase-p3.15 — Repair the required-plugin install path

[Bead Pages](../README.md) / [sase-p3](README.md) / sase-p3.15

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-p3.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-p3.land.md) · **Assignee:** `sase-p3.15.land`
**Created:** 2026-08-18 04:37:37 EDT
**Plan:** [202608/required\_plugin\_install\_repair.md](https://github.com/sase-org/sase--plans/blob/main/202608/required_plugin_install_repair.md)

## Description

`plugins.required` is satisfiable everywhere sase builds — CI, a fresh ephemeral workspace, and a workspace with a stale or dangling install — by installing exactly what the project declares and verifying it actually imports; and a required plugin's bundled config no longer leaks into test runs.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p3.15.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p3.15.land/README.md) | [sase-p3.15](sase-p3.15.md) | 0 |
