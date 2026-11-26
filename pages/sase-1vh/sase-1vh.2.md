# Bead: sase-1vh.2 — Typed host lookup failures, provider-retry exclusion, honest runner hint

[Bead Pages](../README.md) / [sase-1vh](README.md) / sase-1vh.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1gu](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1gu.md) · **Assignee:** `sase-1vh.2` · **Size:** small
**Created:** 2026-11-26 14:45:31 EST
**Plan:** [202611/launch\_lookup\_busy\_resilience.md](https://github.com/sase-org/sase--plans/blob/main/202611/launch_lookup_busy_resilience.md)

## Description

typed-transient-classification: add an IndexLookupUnavailable base with a transient flag for both lookup exceptions, exclude host lookup failures from provider retry via is_host_owned_failure, and make record_runner_error print a typed transient or index-repair hint instead of the coincidental provider match.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vh.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vh.2/README.md) | [sase-1vh.2](sase-1vh.2.md) | 0 |
