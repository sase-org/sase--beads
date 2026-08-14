# Bead: sase-lb.1 — One live agent per numbered workspace — close the monitor claim hole

[Bead Pages](../README.md) / [sase-lb](README.md) / sase-lb.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.015](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.015.md) · **Assignee:** `sase-lb.1.land`
**Created:** 2026-08-14 11:09:07 EDT
**Plan:** [202608/workspace\_claim\_invariant.md](https://github.com/sase-org/sase--plans/blob/main/202608/workspace_claim_invariant.md)

## Description

A numbered `<project>_<N>` workspace checkout is never occupied by two live agents at once. Every process that works inside a numbered workspace holds the RUNNING-field claim for that exact number for as long as it is in there, the claim's PID is always a live process, and any code path that cannot satisfy that invariant fails loudly instead of silently running unclaimed.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-lb.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-lb.1.land/README.md) | [sase-lb.1](sase-lb.1.md) | 0 |
