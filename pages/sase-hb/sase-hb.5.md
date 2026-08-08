# Bead: sase-hb.5 — Cross-repository validation and canonical deployment

[Bead Pages](../README.md) / [sase-hb](README.md) / sase-hb.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.vh](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.vh/README.md) · **Assignee:** `sase-hb.5` · **Size:** small
**Created:** 2026-08-07 22:51:41 EDT · **Closed:** 2026-08-08 02:20:49 EDT
**Plan:** [202608/xprompt\_skill\_directories.md](https://github.com/sase-org/sase--plans/blob/main/202608/xprompt_skill_directories.md)

## Description

rollout-verification: prove the hard cutover end to end and deploy generated skills only from landed canonical sources.

## Notes

[2026-08-08T06:01:58Z · sase-hb.5] PROPOSED FOLLOW-UP: `sase xprompt show` still treats a pasted `/name` copied reference identically to `#name` (src/sase/xprompt/cli_show_resolve.py normalize_show_name), so `sase xprompt show /sase_plan` reports "unknown xprompt" instead of resolving via skill_name the way the new #skills/foo vs /foo split intends. Pre-existing behavior (unchanged by sase-hb.1-4, pinned by tests/xprompt/test_cli_show_resolve.py::test_normalize_show_name), not a regression, but now inconsistent with the documented skill_name contract and worth a small follow-up to resolve /name via skill_name lookup with a matching CLI help update.

[2026-08-08T06:20:49Z · sase-hb.5] Phase 5 rollout-verification complete. Re-audited enabled projects (sase, actstat, bob-cli) and chezmoi: no stray skill: declarations, no legacy xprompts/skills paths, bob_query.md confirmed migrated to home/sase/skills/. Exercised the public contract: #skills/sase_plan and #skills/bob_query resolve; old #sase_plan/#bob_query are unresolved with actionable diagnostics; /sase_plan and /bob_query resolve to unchanged provider targets. Recorded a PROPOSED FOLLOW-UP note for the pre-existing 'sase xprompt show /name' gap (unrelated regression, pinned by existing test). sase-core: cargo fmt --check, clippy -D warnings, and full cargo test --workspace all pass cleanly. sase repo: found and fixed a real gap where pyproject.toml still pinned sase-core-rs <0.20.0, excluding this epic's own core-contract breaking change (hb.1) from verification; bumped to >=0.20.0,<0.21.0, regenerated uv.lock, and updated the one golden-value test that tracked the old pin. just check (escalated to full suite via packaging-config rule) is fully green: fmt, all lints, SASE validation, committed plans, and the complete test suite (27600+ passed). sase doctor/validate show no skill/xprompt issues; sase validate's only relevant warning is the expected 'redeploy deferred until land' (sase skill init --force is correctly reserved for after this change lands on the canonical branch, per the plan). sase skill init --diff previewed cleanly, limited to expected content drift in sase_gate/sase_git_commit.

## Dependencies

- **Depends on:** [sase-hb.3](sase-hb.3.md) ✓ · ⧖ 2026-08-07
- **Depends on:** [sase-hb.4](sase-hb.4.md) ✓ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-hb.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hb.5/README.md) | [sase-hb.5](sase-hb.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4915790`](https://github.com/sase-org/sase/commit/4915790830164da6fe12de0acf13508e79419772) | build(deps): raise sase-core-rs floor to 0.20.0 | [sase-hb.5](sase-hb.5.md) | 2026-08-08 02:21:32 EDT |
