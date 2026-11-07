# Bead: sase-1rq.3.1.2 — Fix the known macOS-only test failures and the Google sign-in hang

[Bead Pages](../README.md) / [sase-1rq.3.1](sase-1rq.3.1.md) / sase-1rq.3.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1rq.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.3.md) · **Assignee:** `sase-1rq.3.1.2` · **Size:** medium
**Created:** 2026-11-07 08:10:12 EST · **Closed:** 2026-11-07 09:42:18 EST
**Plan:** [202611/bob\_cli\_ci\_green.md](https://github.com/sase-org/sase--plans/blob/main/202611/bob_cli_ci_green.md)

## Description

mac-known-failures: on the mac host, reproduce and fix the macOS-only failures already seen in CI. Lib: one case-insensitive-APFS test and three /var vs /private/var path tests. CLI: clipboard_status picking Alfred over the command provider. gcal_auth: 11 login tests each stall about 600 s because choose_flow picks the browser flow on macOS, so the paste-scripted tests wait out CONSENT_WINDOW. Make every Google login test family (gcal_auth, gmail_shell, and gkeep_auth if affected) select its flow deterministically on every OS.

## Notes

[2026-11-07T13:44:28Z · sase-1rq.3.1.2] PROPOSED FOLLOW-UP: install_ui live-runner PTY test test_real_cargo_install_transcript_uses_correct_phases_and_hides_chatter errors (StopIteration on compiling-dependencies frame) in just check-scripts on Linux; reproduces identically on clean base tree dbd30ec0, unrelated to mac-known-failures changes; likely environment-sensitive, needs owner triage

[2026-11-07T14:42:18Z · sase-1rq.3.1.2] mac-known-failures fixed and verified. tip dbd30ec0. macOS (final tree, CI-like env, nice -n 10): lib filters 5 passed/0.25s, cli clipboard_status 4/4 in 2.00s, gcal_auth 55/55 in 7.74s (<60s), gmail_shell 52/52 in 11.06s, gkeep_auth 14/14 in 1.99s. Linux: lib 5459/0, cli 3273/0, gcal_auth 55/55, gmail_shell 52/52 (also under symlinked TMPDIR simulating /var), gkeep_auth 14/14; just fmt/lint/check-release-tools clean. Fixes: (1) APFS test uses non-colliding B.md; (2) link.rs: canonicalize vault once in run_inner + relative_slashes canonicalizes prefix (production fix: callers expect vault-relative notes; scan/queue store canonical paths); worker tests compare canonical paths; (3) clipboard: no production bug, test finds command row by name (macOS diagnostics prepend Alfred/Clipy); (4) paste-scripted login tests pass -m, harness scrubs SSH/DISPLAY, shims open/xdg-open, 20s consent fail-fast; ssh/browser tests unchanged in intent (renamed login_without_manual to login_paste_flow_never_runs_interactive_auth_add). check-scripts has 1 pre-existing live-runner failure reproduced on clean base, recorded as PROPOSED FOLLOW-UP on this bead.

## Dependencies

- **Blocks:** [sase-1rq.3.1.3](sase-1rq.3.1.3.md) ✓ · ⧖ 2026-11-07
- **Blocks:** [sase-1rq.3.1.4](sase-1rq.3.1.4.md) ✓ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.3.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.3.1.2/README.md) | [sase-1rq.3.1.2](sase-1rq.3.1.2.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1rq.3.1.2][1] | Need the phase scope and design file | 4 |
| read-by | [agent:sase-1rq.3.1.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.3.1.2/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.3.1.land/README.md

<!-- sase:referenced-by:end -->
