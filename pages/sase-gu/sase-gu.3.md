# Bead: sase-gu.3 — Remove the legacy list form

[Bead Pages](../README.md) / [sase-gu](README.md) / sase-gu.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.um](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.um/README.md) · **Assignee:** `sase-gu.3` · **Size:** medium
**Created:** 2026-08-07 09:34:38 EDT · **Closed:** 2026-08-07 11:24:53 EDT
**Plan:** [202608/split\_sidecar\_config.md](https://github.com/sase-org/sase--plans/blob/main/202608/split_sidecar_config.md)

## Description

drop_legacy: delete the legacy list branch from the schema, parser, memory validator, and CI bootstrap tool so repos.sidecar is a closed builtin/custom object, and land it as a breaking change.

## Notes

[2026-08-07T15:24:30Z · sase-gu.3] PROPOSED FOLLOW-UP: `just check-full` SASE validation fails pre-existing (unrelated to sase-gu) — `init memory --check` and `init skills --check` report drift in ~/.local/share/chezmoi/home (7 memory/shim files, 5 sase_gate SKILL.md files); confirmed identical on a stashed clean tree.

[2026-08-07T15:24:53Z · sase-gu.3] drop_legacy landed: schema oneOf array branch deleted and sidecarRepoEntry folded back into sidecarRepo (repos.sidecar is now a closed builtin/custom object); _sidecar_config_entries list branch and the {role,slug} token-intersection merge in _merged_sidecar_entries_cached removed along with the now-unused _sidecar_entry_tokens; init_memory _sidecar_repos_raw and tools/ci_bootstrap_sidecars _sidecar_entries now hard-error on a list; doctor config.repos legacy-list problem kept and reworded as a required migration; compatibility-window wording removed from docs/configuration.md and docs/init.md. Tests migrated to the mapping form across 10 modules; added schema + parser cases asserting the list form is now rejected/ignored. Verified: just fmt, then just check-full lint gates all pass (fmt py/md, keep-sorted, ruff, mypy, pyscripts, changelog, symvision, toobig), validate-committed-plans passes, full suite 26899 passed / 7 skipped. 'sase doctor -C config.repos' reports OK and 'sase repo list' still shows agents, beads, plans, sase--research. The only check-full failure is SASE validation (init memory/skills chezmoi drift), confirmed pre-existing on a stashed clean tree and recorded as a PROPOSED FOLLOW-UP. Not committed — left for the epic land agent; plan asks for feat(repos)! with a BREAKING CHANGE footer.

## Dependencies

- **Depends on:** [sase-gu.2](sase-gu.2.md) ✓ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gu.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gu.3/README.md) | [sase-gu.3](sase-gu.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a56da1e`](https://github.com/sase-org/sase/commit/a56da1e6c340d283ae33ce6aea20639daefd8ca9) | feat(repos)!: remove the legacy list form of repos.sidecar | [sase-gu.3](sase-gu.3.md) | 2026-08-07 11:26:06 EDT |
