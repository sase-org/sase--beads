# Bead: sase-s0.3 — Public exposure, parity, and release verification

[Bead Pages](../README.md) / [sase-s0](README.md) / sase-s0.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-rr.land.w1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-rr.land.w1.md) · **Assignee:** `sase-s0.3` · **Size:** small
**Created:** 2026-08-21 20:35:00 UTC · **Closed:** 2026-08-21 22:10:00 UTC
**Plan:** [202608/final\_directive\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202608/final_directive_completion.md)

## Description

surface_parity: reveal %final only after both clients are complete, then lock behavior with parity, visual, documentation, and full-repository checks.

## Notes

[2026-08-21T22:08:07Z · sase-s0.3] PROPOSED FOLLOW-UP: clean up stale pluggable_finalizers flag bead — just check fails in tools/check_feature_flags because live flag bead sase-ro has no registry definition for key pluggable_finalizers.

[2026-08-21T22:10:00Z · sase-s0.3] Verified %final is public in shared Rust directive name completion, ACE directive completion, and pre-argparse/editor candidate providers. Ran just install; cargo fmt --all -- --check; cargo test -p sase_core final_directive; .venv/bin/python -m pytest tests/ace/tui/widgets/test_directive_completion_candidates.py tests/ace/tui/widgets/test_finalizer_completion.py tests/completion/test_candidates_providers.py. just check was run and is blocked by existing feature-flag lint: live flag bead sase-ro has no definition for pluggable_finalizers; recorded PROPOSED FOLLOW-UP on this phase.

## Dependencies

- **Depends on:** [sase-s0.1](sase-s0.1.md) ✓ · ⧖ 2026-08-21
- **Depends on:** [sase-s0.2](sase-s0.2.md) ✓ · ⧖ 2026-08-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-s0.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-s0.3/README.md) | [sase-s0.3](sase-s0.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f618be6`](https://github.com/sase-org/sase/commit/f618be6a809dc0f13a62a2a0e8fba8ac26adc2af) | feat(completion): expose final directive completions | [sase-s0.3](sase-s0.3.md) | 2026-08-21 22:11:28 UTC |
