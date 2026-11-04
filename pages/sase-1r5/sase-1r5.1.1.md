# Bead: sase-1r5.1.1 — sase-core credential\_unconfirmed verdict for SSH publickey denials

[Bead Pages](../README.md) / [sase-1r5.1](sase-1r5.1.md) / sase-1r5.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1r5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1r5.md) · **Assignee:** `sase-1r5.1.1` · **Size:** medium
**Created:** 2026-11-04 06:54:52 EST · **Closed:** 2026-11-04 07:15:01 EST
**Plan:** [202611/github\_publickey\_retry.md](https://github.com/sase-org/sase--plans/blob/main/202611/github_publickey_retry.md)

## Description

core-verdict: in sase-core, classify SSH publickey denials on git and git_clone operations as a new non-retryable `credential_unconfirmed` verdict whose reason keeps the `authentication` category. Deploy-key refusals stay permanent, the retryability module becomes a facade, and table and parity tests cover the new verdict.

## Notes

[2026-11-04T12:15:01Z · sase-1r5.1.1] core-verdict done in sase-core: new credential_unconfirmed verdict for git/git_clone SSH publickey denials (retryable=false, reason keeps authentication category); deploy-key refusals stay permanent with precedence; retryability/mod.rs is now a facade with classify.rs + tests.rs; table tests (10) and parity tests (4, incl. new serialization shape) pass; sase tool run check gate VERDICT pass (exited_zero). Commit left for host finalizer; next phase can pin past this commit.

## Dependencies

- **Blocks:** [sase-1r5.1.2](sase-1r5.1.2.md) ◐ · ⧖ 2026-11-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1r5.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1r5.1.1/README.md) | [sase-1r5.1.1](sase-1r5.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@55532e2`](https://github.com/sase-org/sase-core/commit/55532e2d878dfc5415bdd695a1978cc5c5fb5a3c) | feat(retryability): credential\_unconfirmed verdict for SSH publickey denials | [sase-1r5.1.1](sase-1r5.1.1.md) | 2026-11-04 07:15:59 EST |
