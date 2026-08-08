# Bead: sase-hn.2 — Migrate the Python domain and ProjectSpec storage layer

[Bead Pages](../README.md) / [sase-hn](README.md) / sase-hn.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.vu](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.vu/README.md) · **Assignee:** `sase-hn.2` · **Size:** large
**Created:** 2026-08-08 13:05:53 EDT · **Closed:** 2026-08-08 17:01:42 EDT
**Plan:** [202608/patch\_and\_stitch\_terminology.md](https://github.com/sase-org/sase--plans/blob/main/202608/patch_and_stitch_terminology.md)

## Description

python-domain-storage: introduce canonical models, modules, parsing, formatting, persistence, and wire adapters with legacy aliases.

## Notes

[2026-08-08T21:01:42Z · sase-hn.2] Implemented the Python Patch/Stitch storage migration with legacy ChangeSpec/commit-entry compatibility shims preserved. Verification passed: just install; focused pytest for patch compatibility, core patch wire, snapshot cache, refs persistence, archive, and hypothesis property tests; targeted rerun of the three prior full-suite failures; just check passed through fmt, ruff, mypy, pyscripts, test-waits, changelog, symvision, toobig, SASE validation, committed-plan validation, and scoped pytest. The scoped check escalated by selection rules, then completed cleanly after the suite gate refused extra full-suite tokens.

[2026-08-08T21:03:20Z · sase-hn.2] Implemented Python Patch/Stitch storage migration; verified with just install, focused pytest reruns, and just check.

## Dependencies

- **Depends on:** [sase-hn.1](sase-hn.1.md) ✓ · ⧖ 2026-08-08
- **Blocks:** [sase-hn.3](sase-hn.3.md) ✓ · ⧖ 2026-08-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-hn.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-hn.2.md) | [sase-hn.2](sase-hn.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3e6da8d`](https://github.com/sase-org/sase/commit/3e6da8d5fb1b7d4887b8f78cfce863d702fa1fb7) | feat: Migrate the Python domain and ProjectSpec storage layer (sase-hn.2) | [sase-hn.2](sase-hn.2.md) | 2026-08-08 15:28:09 EDT |
| sase | [`6367ef3`](https://github.com/sase-org/sase/commit/6367ef34734011e7ebe37885b7bf074260627412) | refactor(patch): canonicalize Python patch storage | [sase-hn.2](sase-hn.2.md) | 2026-08-08 17:04:42 EDT |
