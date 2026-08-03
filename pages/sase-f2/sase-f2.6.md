# Bead: sase-f2.6 — One-shot rewrite of stored files

[Bead Pages](../README.md) / [sase-f2](README.md) / sase-f2.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ej.land.w2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ej.land.w2/README.md) · **Assignee:** `sase-f2.6` · **Size:** medium
**Created:** 2026-08-03 14:48:50 EDT · **Closed:** 2026-08-03 15:50:21 EDT
**Plan:** [202608/revert\_stored\_prompt\_duality.md](https://github.com/sase-org/sase--plans/blob/main/202608/revert_stored_prompt_duality.md)

## Description

migrate: rewrite every already-stored chat transcript and archived prompt entry back to the pre-sase-e6 format with a throwaway tool, commit and push the affected agents sidecars, delete the orphaned provenance artifacts, and then delete the tool itself.

## Notes

[2026-08-03T19:37:39Z · sase-f2.6] PROPOSED FOLLOW-UP: make sase repo open disambiguate duplicate hidden sidecars — opening agents sidecars for this migration failed as ambiguous because each project has both the existing machine-level agents clone and a missing local agents entry with the same name/slug.

[2026-08-03T19:50:21Z · sase-f2.6] Rewrote stored prompt sections out of local chats, agents-sidecar prompt archives, and published sidecar chat transcripts; deleted xprompt_sources.json artifacts; pushed affected sase and bob-cli agents sidecars; post-write dry-run reported zero pending changes; sentinel search was clean across ~/.sase/chats and affected agents sidecars; xprompt_sources count is 0; sase/bob-cli/actstat prompt validation passed; migrated chat resume and response output succeeded; sidecar HEADs match origin/main. just check passed fmt/ruff/mypy/pyscripts/changelog and failed at symvision on sibling-phase stale symbols load_xprompt_source_records and render_prompt_sections.

## Dependencies

- **Depends on:** [sase-f2.1](sase-f2.1.md) ✓
- **Depends on:** [sase-f2.2](sase-f2.2.md) ✓
