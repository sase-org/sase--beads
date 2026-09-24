# Bead: sase-18f.7 — Make the split\_file xprompt keep symvision and mypy green

[Bead Pages](../README.md) / [sase-18f](README.md) / sase-18f.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0rh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0rh.md) · **Assignee:** `sase-18f.7` · **Size:** small
**Created:** 2026-09-24 17:19:01 EDT · **Closed:** 2026-09-24 19:02:37 EDT
**Plan:** [202609/green\_just\_check.md](https://github.com/sase-org/sase--plans/blob/main/202609/green_just_check.md)

## Description

split-file-prompt: expand the built-in split_file xprompt that toobig routine agents run. It must forbid cross-module private imports, keep the public import paths, and require the split agent to run and fix symvision, mypy, and toobig before finishing. Close sase-180.

## Notes

[2026-09-24T23:02:37Z · sase-18f.7] split_file xprompt keeps all phase clauses (no cross-module _private imports, public import path preserved, monkeypatch targets, symvision+mypy+toobig run plus sase tool run check). Fixed the wrap-brittle test_packaged_split_file_requires_import_safe_verification to match against whitespace-normalized content (the 88-col prose wrap broke 2 single-line assertions). Verified: all 17 tests in tests/test_xprompt_inline_code.py pass, ruff format check and ruff check clean. sase-180 left for the land agent to close on this evidence.

## Dependencies

- **Blocks:** [sase-18f.9](sase-18f.9.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18f.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18f.7/README.md) | [sase-18f.7](sase-18f.7.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b2137e8`](https://github.com/sase-org/sase/commit/b2137e84c907c2c5bfe4a6055c64ba93abd216b1) | feat(xprompts): strengthen split-file constraints | [sase-18f.7](sase-18f.7.md) | 2026-09-24 18:13:01 EDT |
| sase | [`c77912a`](https://github.com/sase-org/sase/commit/c77912a38cf508deb9dc75e1fd3864b0d738fe6f) | fix(tests): normalize whitespace in xprompt inline-code wrap assertions | [sase-18f.7](sase-18f.7.md) | 2026-09-24 19:04:43 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-18f.7][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18f.7/README.md

<!-- sase:referenced-by:end -->
