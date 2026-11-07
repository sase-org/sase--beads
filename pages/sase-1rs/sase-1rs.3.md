# Bead: sase-1rs.3 — Setup wizard, PKCE login, and the token broker

[Bead Pages](../README.md) / [sase-1rs](README.md) / sase-1rs.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.19n](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.19n.md) · **Assignee:** `sase-1rs.3` · **Size:** medium
**Created:** 2026-11-07 10:55:59 EST · **Closed:** 2026-11-07 13:31:17 EST
**Plan:** [202611/spotify\_agent\_access.md](https://github.com/sase-org/sase--plans/blob/main/202611/spotify_agent_access.md)

## Description

auth: implement the setup wizard and a PKCE login that accepts either a loopback callback or a pasted redirect. Add the locked, rotation-safe token broker with six-month expiry tracking, plus status and logout.

## Notes

[2026-11-07T18:30:51Z · sase-1rs.3] Seams for later phases. api: TokenBroker (auth/broker.py) implements TokenProvider; call access_token(scopes, force_refresh=True) exactly once after a 401; current_record().account_id gives the envelope account_id. reads (dashboard/doctor): store.login_status(config) returns LoginState plus store_info (path, modes, private) with no network. lifecycle (auth renew/complete): flows.start_login(config, record.scopes, purpose="renewal") + store.save_pending/load_pending (load_pending returns None once past 14 days); flows.parse_redirect raises RedirectProblem (.retryable for garbage/state_mismatch) and flows.finish_login raises RedirectProblem(CODE_REJECTED) on a used or expired code, so both map to {status: "retry"}; finish_login resets authorized_at and clears needs_reauth. Every auth -j answer is auth-status@1 (setup/login/logout add an action object).

[2026-11-07T18:30:56Z · sase-1rs.3] Scaffold-file edit (unavoidable, minimal): tests/test_cli.py LEAVES dropped the five implemented auth stubs (auth, auth status, auth setup, auth login -w, auth logout -y); renew/complete stay for lifecycle. New test-only fake tests/fakes/accounts.py (token endpoint plus GET /v1/me, MockTransport and loopback server) stands in until the api phase fake lands; it can stay or be folded into tests/fakes/spotify.py. Added auth setup -c/--client-id for non-interactive setup, plus a best-effort, warning-only probe of the authorize page for a bad client ID or redirect URI.

[2026-11-07T18:31:11Z · sase-1rs.3] PROPOSED FOLLOW-UP: Check the auth setup probe strings against live Spotify during rollout — probe_client in cli/auth.py looks for "Invalid client" and "Invalid redirect URI" on a 400 authorize page. It only ever warns, so a wording mismatch yields check=unknown and never blocks setup.

[2026-11-07T18:31:17Z · sase-1rs.3] Implemented auth setup (wizard, -c/--client-id, format check, warning-only probe), auth login [-w] (PKCE S256 with a 64-char verifier, loopback 127.0.0.1 listener racing a pasted redirect, state check, kind access_denied handling, GET /me, wrong_account refused without saving, account pinned on first login, QR on terminals), the locked rotation-safe TokenBroker (fresh-token reuse, flock with a 30 s timeout and re-read, rotation persisted, authorized_at untouched by refresh, invalid_grant -> needs_reauth + reauth_required with no retry, bounded backoff -> network_unavailable, scope_missing hint auth login --write), auth status (auth-status@1), and auth logout (itemized list, y/N or -y, purge under lock, revoke link). Tests cover RFC 7636 vectors, state mismatch, pasting a full URL, a bare query, or garbage, an 8-process race doing exactly one refresh (mutation-checked: fails without the under-lock re-read), rotation, invalid_grant, file modes 0600/0700, and wrong account. sase tool run check passes: ruff, format, mypy --strict, codespell, and 432 tests at 97.97% coverage (auth modules 99%). docs/getting-started.md filled (Premium, dashboard setup, local, SSH paste, tunnel, write upgrade, logout).

## Dependencies

- **Depends on:** [sase-1rs.2](sase-1rs.2.md) ✓ · ⧖ 2026-11-07
- **Blocks:** [sase-1rs.5](sase-1rs.5.md) ✓ · ⧖ 2026-11-07
- **Blocks:** [sase-1rs.7](sase-1rs.7.md) ✓ · ⧖ 2026-11-07
- **Blocks:** [sase-1rs.8](sase-1rs.8.md) ◐ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rs.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rs.3/README.md) | [sase-1rs.3](sase-1rs.3.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1rs.2][1] | Check whether the parallel auth phase has started work that could conflict with the scaffold commit | 1 |
| read-by | [agent:sase-1rs.3][2] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1rs.4][3] | Check parallel phases' notes for API assumptions on the api phase | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rs.2/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rs.3/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rs.4/README.md

<!-- sase:referenced-by:end -->
