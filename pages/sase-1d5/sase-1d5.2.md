# Bead: sase-1d5.2 — Secret scanning on newly created public sidecars (sase-github)

[Bead Pages](../README.md) / [sase-1d5](README.md) / sase-1d5.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tz](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tz.md) · **Assignee:** `sase-1d5.2` · **Size:** small
**Created:** 2026-09-30 01:57:10 EDT · **Closed:** 2026-09-30 02:05:46 EDT
**Plan:** [202609/public\_bead\_attachments.md](https://github.com/sase-org/sase--plans/blob/main/202609/public_bead_attachments.md)

## Description

push_protection: honor a new sdd_secret_scanning provider option by enabling GitHub secret scanning and push protection, best effort, right after sase-github creates a public repo, with tests and docs.

## Notes

[2026-09-30T06:05:34Z · sase-1d5.2] PROPOSED FOLLOW-UP: sase-github just check / sase tool run check cannot resolve deps in this sandbox (only sase-core-rs>=0.34.23 available vs sase>=0.17.0 pin <0.33.0); verified equivalent gates (ruff, full pytest, mypy) via parent checkout venv instead

[2026-09-30T06:05:46Z · sase-1d5.2] Implemented sdd_secret_scanning provider option: PATCH enables secret scanning+push protection only for newly created public repos, best-effort with stderr warning; private/adopted repos untouched; docs in configuration.md. Verified: 13 new tests pass, full suite 258 passed, ruff+format+mypy clean.

## Dependencies

- **Blocks:** [sase-1d5.8](sase-1d5.8.md) ◐ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1d5.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1d5.2/README.md) | [sase-1d5.2](sase-1d5.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-github | [`sase-github@7288df7`](https://github.com/sase-org/sase-github/commit/7288df7c0e401839ce2f96a684839c131b0d454a) | feat(sdd): enable secret scanning on newly created public sidecars | [sase-1d5.2](sase-1d5.2.md) | 2026-09-30 02:06:53 EDT |
