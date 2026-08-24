# Bead: sase-sn.3 — Silence and sharpen expansion-failure reporting

[Bead Pages](../README.md) / [sase-sn](README.md) / sase-sn.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0c5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0c5.md) · **Assignee:** `sase-sn.3` · **Size:** small
**Created:** 2026-08-24 06:11:48 EDT · **Closed:** 2026-08-24 06:41:04 EDT
**Plan:** [202608/xprompt\_text\_block\_args.md](https://github.com/sase-org/sase--plans/blob/main/202608/xprompt_text_block_args.md)

## Description

diagnostic: keep the best-effort unresolved-reference pre-scan from printing a fatal expansion error it then swallows, and make an argument-binding failure name the call and the surplus positional that caused it.

## Notes

[2026-08-24T10:41:04Z · sase-sn.3] Verified: scan_query_for_unresolved_references uses process_xprompt_references(raise_on_error=True) so a failed expand raises XPromptError and the pre-scan emits no print_status; default expansion still prints and sys.exits. Surplus positionals name the xprompt, received-vs-declared counts, and the landed input (e.g. wait). just check passed (scoped escalated to full suite; 53 targeted tests passed).

## Dependencies

- **Blocks:** [sase-sn.6](sase-sn.6.md) ✓ · ⧖ 2026-08-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-sn.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-sn.3/README.md) | [sase-sn.3](sase-sn.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d0ea16e`](https://github.com/sase-org/sase/commit/d0ea16ef8eac7043636b4292237d1efc2b92ba9a) | fix(xprompt): silence swallowed expansion errors and name surplus bindings | [sase-sn.3](sase-sn.3.md) | 2026-08-24 06:42:04 EDT |
