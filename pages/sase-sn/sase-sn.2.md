# Bead: sase-sn.2 — Stop round-tripping shorthand free text through \`\[\[...\]\]\`

[Bead Pages](../README.md) / [sase-sn](README.md) / sase-sn.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0c5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0c5.md) · **Assignee:** `sase-sn.2` · **Size:** medium
**Created:** 2026-08-24 06:11:47 EDT · **Closed:** 2026-08-24 06:36:12 EDT
**Plan:** [202608/xprompt\_text\_block\_args.md](https://github.com/sase-org/sase--plans/blob/main/202608/xprompt_text_block_args.md)

## Description

shorthand: bind `#name: text`, `#name:: text`, and `#name(args): text` payloads structurally during expansion so user prose is never re-serialized into source syntax and re-lexed.

## Notes

[2026-08-24T10:36:12Z · sase-sn.2--1] Auto-closed by `sase stitch create` after create_commit landed 4d0da0d4b ("fix(xprompt): bind shorthand text directly from source, not re-lexed"). No verification is implied by this note. Reopen with `sase bead open sase-sn.2`, or pass `-B|--do-not-close-bead` on mid-flight commits.

## Dependencies

- **Blocks:** [sase-sn.6](sase-sn.6.md) ✓ · ⧖ 2026-08-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-sn.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-sn.2.md) | [sase-sn.2](sase-sn.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4d0da0d`](https://github.com/sase-org/sase/commit/4d0da0d4be1c0ab5284946c3a6393c3d758a6302) | fix(xprompt): bind shorthand text directly from source, not re-lexed | [sase-sn.2](sase-sn.2.md) | 2026-08-24 06:35:32 EDT |
