# Bead: sase-ez.4 — Hand-fix the bob-cli bead and agent identities

[Bead Pages](../README.md) / [sase-ez](README.md) / sase-ez.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sy](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sy/README.md) · **Assignee:** `sase-ez.4` · **Size:** large
**Created:** 2026-08-03 11:32:33 EDT · **Closed:** 2026-08-03 16:41:53 EDT
**Plan:** [202608/revert\_bead\_reprefix\_epic.md](https://github.com/sase-org/sase--plans/blob/main/202608/revert_bead_reprefix_epic.md)

## Description

bob-cli-reprefix: rename the thirteen leaked-prefix bob-cli beads and their derived agent identities to a collision-free bob-cli prefix with a one-off throwaway script, rewriting the bead store, plan refs, agent artifacts, registries, chats, and the agents sidecar while leaving published commit history untouched.

## Notes

[2026-08-03T20:41:53Z · sase-ez.4] Implemented the approved bob-cli identity reprefix.

Backup path: /home/bryan/.sase/tmp/bob-cli-identity-reprefix-20260803/backups/20260803T201306Z
Pre-migration heads: beads 255d8c5d98f6e533ee651be98a127bdcc0ef2337, plans a43af3038665cab14ee293a92858d5bec957c63c, agents ed9c70f37967bece446a40d35436eec62ef13542.
Post-migration heads: beads 3875a2e9e63b56e2fac2b3175451b8af73b68039, plans 26bb5c4e78c60c49914a1b93f56466b84eeab14d, agents 04fce79b327b6716cf8f44424931989ead742ea8.

Migration counts: base pass planned/applied 320 writes, 21 renames, and 107 deletes across 13 affected bob-cli artifact dirs and 38 chat rows. Follow-up local metadata repair rewrote 6 local JSON/JSONL files, renamed 44 generated markdown PDF files, rewrote 12 markdown_pdfs/index.json files, and rewrote 7 done.json PDF references. Agents sidecar retirement removed the three leaked-prefix hoods, fourteen old agent bundle dirs, and the old gh_bobs-org__bob-cli-2.land family page; after a full sync re-synthesized commit-only old pages from immutable primary footers, those old paths were retired again.

Verification passed: bob-cli bead list shows 13 closed bob-cli IDs; bob-cli-b show/history render with rewritten child IDs and re-minted event IDs; sase bead doctor is clean; bead sync reports in sync with git; the three edited bob-cli plans validate with 0 warnings; postcheck reports pending_change_count 0 with no old streams, missing new streams, stale sidecar paths, pending chat/json rewrites, stale PDF references, or registry old-token hits; dismissed-bundle archive verify reports 17,338 valid bundles and 0 corrupt/missing/stale rows; agent sync --check --refresh -p bob-cli exits 0 with ahead=0 behind=0 and fetched head 04fce79b327b6716cf8f44424931989ead742ea8; chat lookup for bob-cli-e.land resolves the migrated identity and lookup for gh_bobs-org__bob-cli-5.5 returns no rows. Boundary scans found no old leaked-prefix IDs in the mutable bob-cli bead store, chats, notifications/dismissed JSON, generated markdown PDF filenames, or agents sidecar structured files excluding unrelated prompt prose. The remaining old IDs are accepted immutable primary-repository commit/history/footers and unrelated free-form historical prompt prose outside owned fields.

Expected exceptions: the bob-cli primary repository history was intentionally left unchanged, including historical commit bodies/footers/links that mention old IDs. A broad full agent sync can still infer commit-only pages from those immutable SASE_AGENT footers; I retired the generated old pages after confirming that behavior.

PROPOSED FOLLOW-UP: Teach agent sync/drop-retired to remember retired or remapped identities when immutable primary commit footers still contain historical SASE_AGENT values. During this migration, a full bob-cli sync re-synthesized old commit-only pages from preserved primary history, requiring a second retirement pass.

PROPOSED FOLLOW-UP: Repair or quarantine the four malformed SASE-project artifact JSON files that keep `sase agent index verify -j` false even after a clean rebuild: /home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202607/19/20260719084609/prompt_step_gh__diff.json, /home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202607/19/20260719084609/workflow_state.json, /home/bryan/.sase/projects/gh_sase-org__sase/artifacts/fix-hook/20260719084348/done.json, and /home/bryan/.sase/projects/gh_sase-org__sase/artifacts/fix-hook/20260719084413/done.json. The verify result is otherwise clean: indexed_rows=source_rows=6262, missing_rows=0, stale_rows=0, extra_rows=0, corrupt_rows=4.

PROPOSED FOLLOW-UP: Address unrelated `sase validate` failures for bob-cli: `init memory --check` wants generated memory/provider shim refresh, `init repo --check` wants sidecar guide refresh, and `plan links validate` reports 57 legacy prompt Markdown files still in the plans store. I did not run memory initialization because memory edits require explicit owner permission.

PROPOSED FOLLOW-UP: Clean up the unrelated bob-cli agent-sync quarantine diagnostics for stale publication requests bbugyi200.athena.sase-ez.4@26bb5c4e78c6 and @aee55cfc5bcf, or make sync --check distinguish those from the project being checked.

## Dependencies

- **Depends on:** [sase-ez.1](sase-ez.1.md) ✓
- **Blocks:** [sase-ez.5](sase-ez.5.md) ✓
