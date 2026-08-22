# Bead: sase-s1.2 — Make CLI and skills rendering assertions environment-independent

[Bead Pages](../README.md) / [sase-s1](README.md) / sase-s1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0al](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0al.md) · **Assignee:** `sase-s1.2` · **Size:** small
**Created:** 2026-08-22 12:30:20 UTC · **Closed:** 2026-08-22 13:19:50 UTC
**Plan:** [202608/restore\_github\_actions.md](https://github.com/sase-org/sase--plans/blob/main/202608/restore_github_actions.md)

## Description

portable-cli-contracts: reuse portable metavar assertions and tolerate Rich line wrapping while retaining the tested user-facing contracts.

## Notes

[2026-08-22T13:19:50Z · sase-s1.2] Portable CLI/skills assertions: pipe, memory, completion, and proc help tests now use assert_metavar_option_documented with actual metavars (MODEL/TOKEN/TEXT, {json,markdown,rich}, FILE/DIR, NAME) so both argparse 3.12 and 3.13+ spellings pass; helper unit tests still fail on a missing option or wrong metavar. Retired skills source and live paths are compared after collapsing wrap whitespace and Rich table borders, so long CI tmp paths folded at column 160 still match, while a missing path still fails. No production CLI help or skills rendering changed. Verified on Python 3.14 (all 84 tests in the modified files) plus a long-TMPDIR reproduction of the retired-drift wrap; 3.12 metavar spellings covered by helper unit tests. just check lint/fmt/mypy/symvision passed; init memory --check failed on pre-existing chezmoi home drift unrelated to this phase. Escalated full suite (core-identity-changed from just install) failed only on missing sase-xprompt-lsp (sase-s1.1) and the wrap assertion, which is now fixed.

## Dependencies

- **Blocks:** [sase-s1.6](sase-s1.6.md) ◐ · ⧖ 2026-08-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-s1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-s1.2/README.md) | [sase-s1.2](sase-s1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b05d2d5`](https://github.com/sase-org/sase/commit/b05d2d5bfd33209dea439a79cd68ccd99a83fc38) | test(cli): make help and skills assertions environment-independent | [sase-s1.2](sase-s1.2.md) | 2026-08-22 13:25:33 UTC |
