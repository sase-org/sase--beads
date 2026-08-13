# Bead: sase-kv.4 — Research sidecar ref provider icon

[Bead Pages](../README.md) / [sase-kv](README.md) / sase-kv.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.z6.f2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.z6.f2.md) · **Assignee:** `sase-kv.4` · **Size:** xsmall
**Created:** 2026-08-13 09:16:57 EDT · **Closed:** 2026-08-13 09:35:49 EDT
**Plan:** [202608/artifacts\_tab\_icons.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_tab_icons.md)

## Description

research: declare the research ref provider's icon in the sase-research plugin so the Research pane matches the research tribe mark already configured there.

## Notes

[2026-08-13T13:35:49Z · sase-kv.4] Added required ref.icon (∴) to RESEARCH_REF_PROVIDER_SPEC in sase-research/src/sase_research/provider.py, matching the research tribe mark. Ran just check in sase-research: 25/27 tests pass; the 2 failures (test_research_ref_provider_discovered_with_provenance, test_use_and_inline_normalize_identically) are pre-existing cross-phase blockers on sibling phase sase-kv.3, which still needs to add icon support to the builtin plan provider spec and to the sidecar-ref inline-config schema validator (currently rejects icon as an unknown field) — confirmed via direct repro, unrelated to this change.

## Dependencies

- **Depends on:** [sase-kv.1](sase-kv.1.md) ✓ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-kv.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-kv.4/README.md) | [sase-kv.4](sase-kv.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-research | [`sase-research@379b362`](https://github.com/sase-org/sase-research/commit/379b3621a722c213b02fb2f8717d512cdddf3bd3) | feat(research): declare ref.icon for the sidecar ref provider spec | [sase-kv.4](sase-kv.4.md) | 2026-08-13 09:36:22 EDT |
