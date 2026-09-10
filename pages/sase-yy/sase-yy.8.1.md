# Bead: sase-yy.8.1 — Freeze derived and alias operation identity across retries

[Bead Pages](../README.md) / [sase-yy.8](sase-yy.8.md) / sase-yy.8.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-yy.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-yy.land.md) · **Assignee:** `sase-yy.8.1` · **Size:** medium
**Created:** 2026-09-10 14:27:23 EDT · **Closed:** 2026-09-10 15:06:39 EDT
**Plan:** [202609/artifact\_link\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/artifact_link_landing_repairs.md)

## Description

producer_identity: make repeated derivation and rename discovery reuse byte-identical immutable events, reject collisions before persistence, and preserve machine eligibility without releasing unrelated agent reads.

## Notes

[2026-09-10T19:06:01Z · sase-yy.8.1] PROPOSED FOLLOW-UP: Resolve orphaned link_events flag lifecycle - just check fails because live flag bead sase-z0 has no registry definition after a8d99d295 removed FeatureFlag.link_events; close sase-z0 with the artifact-link cutover land work or restore a real registry and call-site before landing.

[2026-09-10T19:06:39Z · sase-yy.8.1] Implemented stable Rust-backed producer identity for derived and alias artifact-link events; focused pytest passed (59 passed); tools/validate_sase_core_rs passed; linked sase-core just check passed with LD_LIBRARY_PATH for libpython3.14; main just check was run and is blocked only by pre-existing live flag bead sase-z0 missing the link_events registry definition, with a PROPOSED FOLLOW-UP recorded on this phase; epic-symbols returned none.

## Dependencies

- **Blocks:** [sase-yy.8.2](sase-yy.8.2.md) ◐ · ⧖ 2026-09-10
- **Blocks:** [sase-yy.8.4](sase-yy.8.4.md) ◐ · ⧖ 2026-09-10
- **Blocks:** [sase-yy.8.5](sase-yy.8.5.md) ◐ · ⧖ 2026-09-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-yy.8.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-yy.8.1/README.md) | [sase-yy.8.1](sase-yy.8.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f5a3f5c`](https://github.com/sase-org/sase/commit/f5a3f5c99ec7c55a44ff0517c7eea820f0b46c3c) | fix(artifact-links): freeze replayable producer identity | [sase-yy.8.1](sase-yy.8.1.md) | 2026-09-10 15:08:10 EDT |
| sase-core | [`sase-core@d5d5be4`](https://github.com/sase-org/sase-core/commit/d5d5be4baa62d807a4a8959d2f43f12ff292bcf5) | fix(artifact-links): expose stable producer identity helpers | [sase-yy.8.1](sase-yy.8.1.md) | 2026-09-10 15:10:33 EDT |
