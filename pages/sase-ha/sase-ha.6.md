# Bead: sase-ha.6 — ACE styling and provider badges

[Bead Pages](../README.md) / [sase-ha](README.md) / sase-ha.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ve](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ve/README.md) · **Assignee:** `sase-ha.6` · **Size:** small
**Created:** 2026-08-07 20:46:07 EDT · **Closed:** 2026-08-07 22:03:01 EDT
**Plan:** [202608/muse\_provider.md](https://github.com/sase-org/sase--plans/blob/main/202608/muse_provider.md)

## Description

polish: give Muse a Meta-blue provider palette, an emoji badge, and a family color so agent rows, model labels, and integrations render it as a known provider instead of the neutral fallback.

## Notes

[2026-08-08T02:02:44Z · sase-ha.6] PROPOSED FOLLOW-UP: tests/doctor/test_checks_providers.py::test_setup_hint_points_script_installs_at_the_install_subcommand fails on master (unrelated to this phase) — setup_hint() for muse returns auth "run `muse login`, or set META_API_KEY" but the test expects the generic "follow the muse authentication flow" string. Confirmed pre-existing by reproducing with this phase's diff stashed out.

[2026-08-08T02:03:01Z · sase-ha.6] Added a Meta-blue _ProviderStyle (name #0064E0/model #4A9DFF/secondary #1877F2) for muse and meta in provider_styles.py, the infinity-loop badge for muse/meta in provider_badges.py, and _PROVIDER_FAMILY_COLORS[meta]=#0064E0 in registry.py, matching the plan exactly; left custom_model_input_modal.py's placeholder untouched per the plan's explicit guidance since Muse model ids are flat. Verified: just install; just test-visual (560 passed, 1 pre-existing failure in frontmatter_panel_raw_diagnostics reproduced identically with this diff stashed out, so unrelated); just check (all lint gates green; test-scoped 9119 passed, 1 pre-existing failure in test_checks_providers.py also reproduced on master with the diff stashed out, unrelated to this phase and noted as a follow-up).

## Dependencies

- **Depends on:** [sase-ha.2](sase-ha.2.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-ha.7](sase-ha.7.md) ✓ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ha.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ha.6/README.md) | [sase-ha.6](sase-ha.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`90b17d8`](https://github.com/sase-org/sase/commit/90b17d824596216df6f0cee97ec5a363f6cbd333) | feat(ace): give Muse a Meta-blue provider palette and badge | [sase-ha.6](sase-ha.6.md) | 2026-08-07 22:03:48 EDT |
