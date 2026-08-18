# Bead: sase-p3.15.3 — Publish sase-research-artifacts and retire the git fallback

[Bead Pages](../README.md) / [sase-p3.15](sase-p3.15.md) / sase-p3.15.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-p3.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-p3.land.md) · **Assignee:** `sase-p3.15.3` · **Size:** small
**Created:** 2026-08-18 04:37:38 EDT · **Closed:** 2026-08-18 19:07:50 EDT
**Plan:** [202608/required\_plugin\_install\_repair.md](https://github.com/sase-org/sase--plans/blob/main/202608/required_plugin_install_repair.md)

## Description

publish-research-artifacts: fix the red release-please Publish workflow in sase-research-artifacts, cut the first PyPI release, then pin it in `plugins.required` and retire the git-repo fallback branch it needed.

## Notes

[2026-08-18T17:37:47Z · sase-pt.land] INTEGRATION NOTE from sase-pt.land (landing epic sase-pt, 2026-08-18): the first two clauses of this phase's description -- 'fix the red release-please Publish workflow in sase-research-artifacts' and 'cut the first PyPI release' -- are now DONE, delivered by epic sase-pt rather than this phase. Facts to build on rather than re-derive: root cause of the red Publish workflow was an invalid/rotated SASE_RELEASE_TOKEN repo secret (release-please got 401 Bad credentials until the secret was re-saved on sase-research-artifacts, updated_at 2026-08-18T15:36:13Z); release-please then opened PR #1 (https://github.com/sase-org/sase-research-artifacts/pull/1), which was squash-merged as 253aa62; the resulting Publish run 32160158404 went green end to end (release/build/install-smoke/publish all success). Git tag v0.2.0 = 253aa62, GitHub release https://github.com/sase-org/sase-research-artifacts/releases/tag/v0.2.0, PyPI files sase_research_artifacts-0.2.0-py3-none-any.whl (sha256=4bf695c94a91e7c4aba4d85ad223ec6b113a6dbba063173df07968a02ae9026e) and the matching sdist, both verified live on PyPI as of this note. Remaining scope for this phase, not yet done by sase-pt: pin sase-research-artifacts to a real version (e.g. >=0.2.0) in sase/sase.yml plugins.required (currently unpinned at line 284) and retire/simplify the git-repo fallback branch in tools/setup_required_plugins now that PyPI actually carries the distribution. Caveat carried over from sase-pt.4: the published wheel's Requires-Dist sase>=0.17.0 cannot resolve from a naive 'pip install sase-research-artifacts' yet because PyPI's sase package is still 0.16.0 -- CI/just install work around this with an --overrides file; this phase should account for that if the fallback-retirement work changes how CI installs the plugin. Not editing plugins.required or the fallback code myself -- that is this phase's own scope and I do not want to blind-edit another epic's in-flight work.

[2026-08-18T23:06:49Z · sase-p3.15.3] PROPOSED FOLLOW-UP: flake tests/completion/test_install_zsh.py::test_real_zsh_zcompile_and_registration — xdist full suite (14 workers, 33773 items) asserted result.registered is True but got None; 6/6 serial reruns on the same tree passed. Not caused by this phase (no completion files in the diff).

[2026-08-18T23:07:06Z · sase-p3.15.3] PROPOSED FOLLOW-UP: just check lint(toobig) fails on tests/_suite_gate.py (1197 lines, limit 1000) on current master; this phase did not touch that file. Remaining check stages (validate, plans, tests) were run separately.

[2026-08-18T23:07:22Z · sase-p3.15.3] PROPOSED FOLLOW-UP: naive `uv pip install sase-research-artifacts` cannot resolve because wheel 0.2.0 Requires-Dist sase>=0.17.0 while PyPI sase is still 0.16.0. just install is unaffected (setup_required_plugins uses --no-deps). Publish sase 0.17.0 or relax the plugin constraint.

[2026-08-18T23:07:50Z · sase-p3.15.3] Pinned plugins.required to sase-research-artifacts>=0.2.0 and removed the sase-org git fallback from tools/setup_required_plugins (checkout then PyPI only; import verification kept; --no-deps retained so the wheel's Requires-Dist sase>=0.17.0 does not re-resolve PyPI sase 0.16.0). Verified: PyPI 0.2.0 wheel sha256=4bf695c94a91e7c4aba4d85ad223ec6b113a6dbba063173df07968a02ae9026e; just install from this workspace (no linked checkout) installed 0.2.0 from PyPI and import sase_research_artifacts succeeded; sase doctor -C plugins.required OK; sase plugin show reports Latest v0.2.0; uv pip install --no-deps sase-research-artifacts>=0.2.0 in a scratch venv installed 0.2.0; targeted tests 20 passed; remaining just check stages after pre-existing toobig on tests/_suite_gate.py: validate OK, 33760 passed / 1 unrelated zsh-completion flake (6/6 serial reruns passed). No --epic-symbol leftovers.

[2026-08-18T23:09:45Z · sase-p3.15.3] Pinned plugins.required to sase-research-artifacts>=0.2.0 and removed the sase-org git fallback from tools/setup_required_plugins (checkout then PyPI only; import verification kept; --no-deps retained so the wheel's Requires-Dist sase>=0.17.0 does not re-resolve PyPI sase 0.16.0). Verified: PyPI 0.2.0 wheel sha256=4bf695c94a91e7c4aba4d85ad223ec6b113a6dbba063173df07968a02ae9026e; just install (no linked checkout) installed 0.2.0 from PyPI; import sase_research_artifacts succeeded; sase doctor -C plugins.required OK; sase plugin show reports Latest v0.2.0; scratch venv uv pip install --no-deps 'sase-research-artifacts>=0.2.0' installed 0.2.0; targeted tests 20 passed. No --epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-p3.15.1](sase-p3.15.1.md) ✓ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p3.15.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p3.15.3/README.md) | [sase-p3.15.3](sase-p3.15.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`155ba10`](https://github.com/sase-org/sase/commit/155ba102bb8638f291377d6c8f39c89a64155baf) | feat(plugins): pin sase-research-artifacts\>=0.2.0 and drop git fallback | [sase-p3.15.3](sase-p3.15.3.md) | 2026-08-18 19:10:38 EDT |
