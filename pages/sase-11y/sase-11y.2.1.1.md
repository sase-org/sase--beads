# Bead: sase-11y.2.1.1 — Proc wire service block, per-service retention, Procs query fields

[Bead Pages](../README.md) / [sase-11y.2.1](sase-11y.2.1.md) / sase-11y.2.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.2.md) · **Assignee:** `sase-11y.2.1.1` · **Size:** medium
**Created:** 2026-09-16 15:15:25 EDT · **Closed:** 2026-09-16 16:56:31 EDT
**Plan:** [202609/core\_service\_foundations.md](https://github.com/sase-org/sase--plans/blob/main/202609/core_service_foundations.md)

## Description

proc-service-block: add the optional additive `service` block `{name, mode, source}` to proc rows and reserve requests in sase-core (no schema bump), validate it when a row is created, keep the newest 20 terminal rows per named service proc instead of counting them against the generic cap, add a shared service-name vocabulary module, and carry the block through the Python Proc/ProcReserve/ObservedProc models into new `service` and `svc:` Procs query fields.

## Notes

[2026-09-16T20:55:46Z · sase-11y.2.1.1] PROPOSED FOLLOW-UP: ratchet sase-core-revision.txt past proc-service-block core commit — core changes in this phase intentionally leave the pin untouched until the land step can point at the committed sase-core SHA.

[2026-09-16T20:56:31Z · sase-11y.2.1.1] Verified proc service wire/model propagation, validation, per-service retention, and Procs query fields with targeted Rust/Python tests, linked sase-core just check with PYO3_PYTHON/LD_LIBRARY_PATH, main just check, and clean epic-symbols.

## Dependencies

- **Blocks:** [sase-11y.2.1.2](sase-11y.2.1.2.md) ✓ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.2.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.2.1.1/README.md) | [sase-11y.2.1.1](sase-11y.2.1.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5c0da1b`](https://github.com/sase-org/sase/commit/5c0da1be43816696d9c66d3bd1febb2eb3673e4b) | feat(procs): surface service metadata | [sase-11y.2.1.1](sase-11y.2.1.1.md) | 2026-09-16 16:58:56 EDT |
| sase-core | [`sase-core@4cee31a`](https://github.com/sase-org/sase-core/commit/4cee31acb81e7d304c5cdec04eaed426f33cec40) | feat(procs): add service proc wire metadata | [sase-11y.2.1.1](sase-11y.2.1.1.md) | 2026-09-16 17:02:07 EDT |
