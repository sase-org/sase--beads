# Bead: sase-1co.2 — Shared alternation scanner, Python binding, and LSP highlighting

[Bead Pages](../README.md) / [sase-1co](README.md) / sase-1co.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u1.md) · **Assignee:** `sase-1co.2` · **Size:** medium
**Created:** 2026-09-29 16:22:03 EDT · **Closed:** 2026-09-29 17:15:54 EDT
**Plan:** [202609/midword\_alternation.md](https://github.com/sase-org/sase--plans/blob/main/202609/midword_alternation.md)

## Description

core-scan-lsp: in sase-core, add one alternation scanner with its wire record and a code-point-offset Python binding. Add an unclosed-alternation editor diagnostic and xprompt LSP semantic tokens with new stable modifiers, plus unit and JSON-RPC tests.

## Notes

[2026-09-29T21:15:54Z · sase-1co.2] core-scan-lsp done in sase-core: shared alternation scanner with wire record, alternation_scan binding with code-point offsets, unclosed-alternation diagnostic, LSP semantic tokens with alternation/separator modifiers. Verified: sase tool run check green (273s), plus focused scanner/diagnostic/binding/semantic/JSON-RPC tests.

## Dependencies

- **Depends on:** [sase-1co.1](sase-1co.1.md) ✓ · ⧖ 2026-09-29
- **Blocks:** [sase-1co.3](sase-1co.3.md) ✓ · ⧖ 2026-09-29
- **Blocks:** [sase-1co.5](sase-1co.5.md) ✓ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1co.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1co.2/README.md) | [sase-1co.2](sase-1co.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@1e51ff3`](https://github.com/sase-org/sase-core/commit/1e51ff3ce9c53ee1a4bc9f52c3642ac4eea8f423) | feat(alternation): shared scanner, binding, diagnostic, and LSP tokens | [sase-1co.2](sase-1co.2.md) | 2026-09-29 17:17:17 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1co.2][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1co.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1co.2/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1co.land/README.md

<!-- sase:referenced-by:end -->
