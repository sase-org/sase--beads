# Bead: sase-1tc.1.1.1 — Rust-owned command substitution source policy

[Bead Pages](../README.md) / [sase-1tc.1.1](sase-1tc.1.1.md) / sase-1tc.1.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tc.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tc.1.md) · **Assignee:** `sase-1tc.1.1.1` · **Size:** medium
**Created:** 2026-11-17 11:31:49 EST · **Closed:** 2026-11-17 12:21:30 EST
**Plan:** [202611/cmdsub\_source\_provenance.md](https://github.com/sase-org/sase--plans/blob/main/202611/cmdsub_source_provenance.md)

## Description

source_policy: implement typed provenance, command-span planning, Python binding, and core/binding tests. Keep shell execution in Python and publish the containing core revision through host completion.

## Notes

[2026-11-17T17:21:30Z · sase-1tc.1.1.1] Implemented prompt_command_substitution in sase-core: typed provenance (human_source / admitted_definition / generated × human/agent launch), UTF-8 byte span planning, protected-range validation, and PyO3 bindings plan_prompt_command_substitution plus schema version. Core tests 19/19 and binding tests 4/4 passed, covering generated/rendered refusal, nested parens, escaped $(, unclosed spans, multiple commands, non-ASCII byte offsets, and invalid ranges. sase tool run check b7a25482c911ec6678bf4c2f39e6160c succeeded. Shell execution stays in Python; Python callers were not switched. sase-core-revision.txt is unchanged this phase so the next phase can ratchet the pin onto the published core commit before calling the binding.

## Dependencies

- **Blocks:** [sase-1tc.1.1.2](sase-1tc.1.1.2.md) ✓ · ⧖ 2026-11-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tc.1.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.1.1.1/README.md) | [sase-1tc.1.1.1](sase-1tc.1.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@1191f9a`](https://github.com/sase-org/sase-core/commit/1191f9a68e76b0c49d7da8768b7cf161edd42b1a) | feat: add prompt command-substitution source policy | [sase-1tc.1.1.1](sase-1tc.1.1.1.md) | 2026-11-17 12:22:29 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tc.1.1.1][1] | Need remaining bead notes, DECISIONS, and design file body | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.1.1.1/README.md

<!-- sase:referenced-by:end -->
