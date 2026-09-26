# Bead: sase-19f.5 — Research swarm authors a 1.5x capacity multiplier

[Bead Pages](../README.md) / [sase-19f](README.md) / sase-19f.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.1o](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.1o.md) · **Assignee:** `sase-19f.5` · **Size:** small
**Created:** 2026-09-25 12:24:42 EDT · **Closed:** 2026-09-25 19:45:03 EDT
**Plan:** [202609/queue\_capacity\_multiplier.md](https://github.com/sase-org/sase--plans/blob/main/202609/queue_capacity_multiplier.md)

## Description

research-swarm: in sase-research-artifacts, render `%q(1.5x, w=0.25)` in every swarm segment, with the optional `runners` input replacing the multiplier with an absolute budget. Update the tests, wheel and publish smokes, docs, and dependency floors where a published core supports it.

## Notes

[2026-09-25T23:26:15Z · sase-19f.5] PROPOSED FOLLOW-UP: raise sase-core-rs floor past first published release containing core-parse (0.34.73 lacks parse_queue_capacity_value); sase 0.17.2 unpublished so sase>=0.17.2 floor stays

[2026-09-25T23:45:03Z · sase-19f.5--1] Monitor 6qs5qe6rp2v8 passed: just install && sase tool run check exit 0 in sase-research-artifacts; epic-symbols clean

## Dependencies

- **Depends on:** [sase-19f.3](sase-19f.3.md) ✓ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-19f.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-19f.5.md) | [sase-19f.5](sase-19f.5.md) | 0 |
