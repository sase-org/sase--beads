# Bead: sase-11y.2.1 — sase-core service foundations

[Bead Pages](../README.md) / [sase-11y.2](sase-11y.2.md) / sase-11y.2.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.2.md) · **Assignee:** `sase-11y.2.1.land`
**Created:** 2026-09-16 15:15:24 EDT · **Closed:** 2026-09-18 04:19:43 EDT
**Plan:** [202609/core\_service\_foundations.md](https://github.com/sase-org/sase--plans/blob/main/202609/core_service_foundations.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/core_service_foundations.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/core_service_foundations.md

<!-- sase:links:end -->

## Description

sase-core owns every piece of shared service-host behavior that later phases of the service-host epic (sase-11y) build on: the proc-wire `service` block with per-service retention, the `service.procs` config composer, the pure restart-decision function, the locked boot-scoped service state store, and the versioned service status snapshot. Each piece has PyO3 bindings and a thin typed Python facade, and the Procs query dialect gains the `service` and `svc:` fields.

## Notes

[2026-09-18T08:19:43Z · 0mm--1] Closed core service foundations after reviewing all child work: phases .1-.4 delivered the proc wire service block, per-service retention and Procs query fields; service.procs config composer/schema/defaults/loader; restart decisions and locked service state store; enablement resolution and service status snapshot wire. Nested epic .5 completed the landing integration and resolved the four original ratchet proposals from phases .1-.4 by pinning sase-core to bd5946c17c798b841ab4b84793f5c2a1a7711567, which contains required core commits 4cee31a, 51ae484, a756136, fe7c4a0, and 3c75d2e. No other child proposals were declined or filed; the stale test-node-id mentioned in .2 was fixed by that phase.

Drift review: primary service/supervision/procs/config/query paths had no post-base commits needing integration; core drift since 3c75d2e only showed unrelated gate-decision commit 41a9830 already inside the pin. Epic-symbol checks for sase-11y.2.1 and sase-11y.2 were empty.

Verification: just install passed, just fix passed and left no diff, focused regression batch passed 90 tests across tests/service, supervision, procs facade, query profile, TUI proc query, and config schema, and linked sase-core just check passed (including core unit totals around 2989 passed and agent scan parity 45 passed). The landing just check-full monitor pmztzxqgca9a ran but failed on unrelated existing/concurrent issues, not service-foundation behavior: synthetic stage-one/boom monitor diagnostic contamination is tracked by existing ready task sase-114; completion snapshot/gate-cancel drift is already recorded on active gate-decision epic sase-zr.7.1.1.5; and the reproduced monitor pid-file/pass_fds fixture cascade is now filed as ready bug task sase-12l. With those unrelated failures handled through task/epic flow, the service-foundation gate evidence is acceptable for closing this epic.
