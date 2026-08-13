# Bead: sase-l3.4 — Doctor, inventory, and binary-collision safety

[Bead Pages](../README.md) / [sase-l3](README.md) / sase-l3.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.zu](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.zu.md) · **Assignee:** `sase-l3.4` · **Size:** small
**Created:** 2026-08-13 14:42:03 EDT · **Closed:** 2026-08-13 17:51:09 EDT
**Plan:** [202608/grok\_provider.md](https://github.com/sase-org/sase--plans/blob/main/202608/grok_provider.md)

## Description

identity: wire Grok into `sase doctor` and `sase agent-cli` install/update/version surfaces, and make the contested `grok` executable name fail loudly and actionably instead of silently launching an unrelated binary.

## Notes

[2026-08-13T21:51:09Z · sase-l3.4] Wired Grok into sase doctor and agent-cli surfaces: added grok to _PROVIDER_SETUP_FALLBACKS (install/auth hints), added a grok-specific identity advisory to the providers.cli_version deep doctor check that flags a resolved 'grok' executable whose --version output doesn't match Grok Build's real shape (grok X.Y.Z (<hash>) [<channel>]) rather than a loose substring, and documented the npm-trampoline (~/.grok/bin/) in a code comment. Verified live against the real Grok Build 1.0.3 binary installed on this machine: sase agent-cli list shows it correctly, sase doctor --deep -C providers.cli_version passes it, and sase agent-cli update grok --dry-run resolves via the self-managed 'grok update' path (same pattern as Claude Code). Initially used a 'grok build'/'xai' substring marker but discovered via the real binary that its --version output is just 'grok 1.0.3 (<hash>) [stable]' with no such text, which would have been a false-positive WARN on every real install — replaced with a verified regex. Added/updated 3 tests (doctor setup hint, identity-mismatch, identity-OK against real format); just check passes.

[2026-08-13T21:52:43Z · sase-l3.4] Added grok to _PROVIDER_SETUP_FALLBACKS in checks_providers.py; added Grok identity advisory regex check to providers.cli_version deep doctor check in checks_deep_providers.py (regex derived from real Grok Build 1.0.3 --version output: 'grok 1.0.3 (1a29d5bc12) [stable]'); added npm-trampoline comment to grok.py llm_install_metadata. Verified end-to-end against real installed grok binary via sase agent-cli list, sase doctor --deep -C providers.cli_version, and sase agent-cli update grok --dry-run. Added 3 tests; just check passes.

## Dependencies

- **Depends on:** [sase-l3.3](sase-l3.3.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-l3.7](sase-l3.7.md) ✓ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-l3.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-l3.4/README.md) | [sase-l3.4](sase-l3.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`fbcf643`](https://github.com/sase-org/sase/commit/fbcf64399ee06d516bc4298a22afe71956595bf0) | fix(doctor): flag grok executables that aren't Grok Build | [sase-l3.4](sase-l3.4.md) | 2026-08-13 17:53:42 EDT |
