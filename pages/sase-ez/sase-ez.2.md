# Bead: sase-ez.2 — Remove the Rust alias and re-prefix primitives

[Bead Pages](../README.md) / [sase-ez](README.md) / sase-ez.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sy](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sy/README.md) · **Assignee:** `sase-ez.2` · **Size:** large
**Created:** 2026-08-03 11:32:18 EDT · **Closed:** 2026-08-03 15:49:10 EDT
**Plan:** [202608/revert\_bead\_reprefix\_epic.md](https://github.com/sase-org/sase--plans/blob/main/202608/revert_bead_reprefix_epic.md)

## Description

core-revert: delete the sase-core bead re-prefix module, alias config field, and PyO3 migration bindings, restore pre-epic bead ID resolution semantics without regressing the retained single-pass detail read, and cut a patch release.

## Notes

[2026-08-03T20:00:57Z · sase-ez.2] PROPOSED FOLLOW-UP: Symvision cleanup — just check currently fails in lint (symvision) on unrelated unused public symbols load_xprompt_source_records in src/sase/xprompt_links.py and render_prompt_sections in src/sase/history/chat_prompt_sections.py; remove or privatize them in a follow-up.

[2026-08-03T20:26:07Z · sase-ez.2] Completed option (a): removed the alias-era Rust resolver/migration surface instead of retaining a reduced abstraction, while preserving the single-pass detail read. Rust gates passed: cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, cargo test --workspace, plus post-install symbol audit and targeted lookup/detail tests. Python gates: just install passed; bead/core-facade/binding-tool subset passed with 1509 tests; just check was run and failed only on unrelated Symvision unused public symbols recorded separately as PROPOSED FOLLOW-UP. Patch release observed: core commit 7de18f8 released through v0.17.16, and PyPI shows sase-core-rs 0.17.16 with all five expected files.

## Dependencies

- **Depends on:** [sase-ez.1](sase-ez.1.md) ✓
- **Blocks:** [sase-ez.5](sase-ez.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ez.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ez.2.md) | [sase-ez.2](sase-ez.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@7de18f8`](https://github.com/sase-org/sase-core/commit/7de18f854cb770b59140a5df6eddbb47b08f22cf) | fix(beads): remove abandoned prefix migration primitives | [sase-ez.2](sase-ez.2.md) | 2026-08-03 15:49:57 EDT |
| sase | [`a33aaa1`](https://github.com/sase-org/sase/commit/a33aaa1c22940db6db74d51049d4046f10ad4a9e) | test(beads): align dep rm missing-edge expectation | [sase-ez.2](sase-ez.2.md) | 2026-08-03 16:02:43 EDT |
