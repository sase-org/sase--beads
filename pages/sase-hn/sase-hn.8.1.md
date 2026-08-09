# Bead: sase-hn.8.1 — Make the terminology audit content-aware

[Bead Pages](../README.md) / [sase-hn.8](sase-hn.8.md) / sase-hn.8.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-hn.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hn.land/README.md) · **Assignee:** `sase-hn.8.1` · **Size:** medium
**Created:** 2026-08-09 00:10:56 EDT · **Closed:** 2026-08-09 00:26:25 EDT
**Plan:** [202608/patch\_terminology\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202608/patch_terminology_completion.md)

## Description

audit-classifier: replace path-prefix-only classification with content-aware rules, make skipped linked repos a hard error, and produce the authoritative defect list the sweep phases work from.

## Notes

[2026-08-09T04:26:25Z · sase-hn.8.1] Implemented content-aware Patch/stitch audit classification, default linked-repo missing checks with --allow-missing-linked-repos, scanned/missing repo reporting, and contract coverage. Verified: just install; pytest tests/test_patch_stitch_terminology_audit.py (8 passed); just _lint-symvision; just check (passed, scoped selected 36/2473). Regenerated /tmp/patch_audit_defects.json with ./tools/audit_patch_stitch_terminology --repo-root . --json (expected exit 1): scanned main and sase-core; missing sase-github, sase-telegram, sase-nvim, chezmoi; defects total 9431 by area: main:src/sase/ace/** 2333, main:src/sase/** excluding ace 1502, main:tests/** 5279, main:tools/** 1, sase-core 316. Retained classification counts: legacy-compatibility-boundary 437, legacy-data-test-fixture 1450, legacy-serialized-data 1714, stable-public-path 131, immutable-history 27, audit-contract 70.

[2026-08-09T04:27:38Z · sase-hn.8.1] Verified just install, pytest tests/test_patch_stitch_terminology_audit.py, just _lint-symvision, and just check passed. Regenerated /tmp/patch_audit_defects.json; audit scanned main and sase-core, reported missing linked repos sase-github, sase-telegram, sase-nvim, chezmoi, and found 9431 defects.

## Dependencies

- **Blocks:** [sase-hn.8.2](sase-hn.8.2.md) ◐ · ⧖ 2026-08-09
- **Blocks:** [sase-hn.8.3](sase-hn.8.3.md) ◐ · ⧖ 2026-08-09
- **Blocks:** [sase-hn.8.4](sase-hn.8.4.md) ✓ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-hn.8.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hn.8.1/README.md) | [sase-hn.8.1](sase-hn.8.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a4a3406`](https://github.com/sase-org/sase/commit/a4a3406795802e77f6d34c3564612f85e891df92) | fix: tighten patch terminology audit classification | [sase-hn.8.1](sase-hn.8.1.md) | 2026-08-09 00:28:33 EDT |
