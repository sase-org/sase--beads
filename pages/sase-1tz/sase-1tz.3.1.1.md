# Bead: sase-1tz.3.1.1 — Add the prompt\_prose artifact-link origin and a host-origin binding contract test

[Bead Pages](../README.md) / [sase-1tz.3.1](sase-1tz.3.1.md) / sase-1tz.3.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.3.md) · **Assignee:** `sase-1tz.3.1.1` · **Size:** medium
**Created:** 2026-11-20 09:19:05 EST · **Closed:** 2026-11-20 11:52:27 EST
**Plan:** [202611/defects\_wire\_swap\_telegram\_bundles\_triage.md](https://github.com/sase-org/sase--plans/blob/main/202611/defects_wire_swap_telegram_bundles_triage.md)

## Description

prose_wire: add PromptProse to sase-core's ArtifactLinkOriginWire with the automatic, commit-scoped semantics sase already relies on, and move the pin. Give sase one constant listing every host-produced origin, and round-trip each through sase_core_rs.artifact_link_validate_row in a contract test. Record what the "wire is stale" skew message means.

## Notes

[2026-11-20T16:38:39Z · sase-1tz.3.1.1] Skew message (plan item 6): "sase_core_rs artifact-reference wire is stale: expected 3, got 4" comes from the existing version-skew guard _require_artifact_ref_schema (src/sase/artifact_ref_operations.py:347-355). It compares ARTIFACT_REF_WIRE_SCHEMA_VERSION (now 5, src/sase/artifact_ref_wire.py:9) with sase_core_rs.artifact_ref_wire_schema_version(), so it covers only the artifact-ref wire. It fires when Python and the binding come from different installs, which is an F7 update-window symptom owned by swap_launch_guards, not by this phase. The artifact-link row wire has no such guard, and a schema-version guard is the wrong tool for this drift class: adding an origin is additive and leaves ARTIFACT_LINK_ROW_SCHEMA_VERSION at 2, and bumping it would invalidate every stored v2 row. The new contract test catches origin drift at the CI pin. It does not catch install skew where a newer sase runs against an older in-window sase-core-rs, because tools/probe_core_floor detects only missing binding names, not enum variants. Follow-up recorded separately.

[2026-11-20T16:38:45Z · sase-1tz.3.1.1] PROPOSED FOLLOW-UP: make artifact-link origin support a probeable capability. Expose ArtifactLinkOriginWire::ALL through a binding (for example artifact_link_origin_names). Then tools/probe_core_floor, sase doctor, or the publication job can fail fast with "installed sase-core-rs lacks origin X; update" instead of a serde "unknown variant" on every pass, and the published sase-core-rs floor ratchets past the PromptProse release. Today a newer sase with an older in-window core still rejects prompt_prose rows, and the capability-based floor probe cannot see enum variants.

[2026-11-20T16:38:50Z · sase-1tz.3.1.1] Measurement (athena, read-only, 2026-11-20 ~11:45 EST). BEFORE:
(1) ~/.sase/projects/gh_sase-org__sase/agents-publication-outbox.json: 3 of 3565 items fail with "referenced-by cites event for plan:202611/research_commit_gap.md: row is not a valid ArtifactLinkRowWire dict: unknown variant `prompt_prose`". All 3 are bbugyi200.athena.sase-1tj.land run 20261118151943 at primary_revision 7ac2081b30d402317f261b968934d720ab9db019, bd8616817d90d840b68ba5858bf44af12f9d1573, and 78225fda5148b332a5baedabe821bf37ec73136b, each with attempts=3, quarantined=true, terminal=false.
(2) referenced-by-outbox.json in the same project: 3 prompt_prose items, all quarantined. 1 has the same unknown-variant error (plan:202609/accepted_gate_reclaim.md). 2 fail on an unrelated dirty hidden plans clone.
(3) artifact-links.json: 0 prompt_prose rows of 59,881. research_commit_gap has only a read row and a derived implements row, with no cites row.
(4) ~/.sase/axe/error_digests: 1 digest (digest_20261118_155618.txt) with 3 prompt_prose lines, all for research_commit_gap.
(5) pub_standing: ~/.sase/agent_publication/standing_alerts.json is {"alerts": {}}. No standing alert exists for this family because quarantine stopped the retries. The would-be alert key is project gh_sase-org__sase plus the normalized signature "referenced-by cites event for plan:202611<path>: row is not a valid artifactlinkrowwire dict: unknown variant `prompt_prose`, ...", whose notification dedup key is agent-publication-standing:gh_sase-org__sase:7d2596a1ff71abac.
AFTER INSTALL: quarantined items do not retry on their own. A human runs `sase agent sync -p sase -q -l 1 -k bbugyi200.athena.sase-1tj.land@<rev>` once for each of the 3 revisions above, or `sase agent sync -p sase -q` to also clear the accepted_gate_reclaim referenced-by quarantine. Then confirm all of the following:
- python3 -c "import json,pathlib;p=pathlib.Path.home()/'.sase/projects/gh_sase-org__sase';print(sum('prompt_prose' in (i.get('last_error') or '') for i in json.loads((p/'agents-publication-outbox.json').read_text())['items']),[r for r in json.loads((p/'artifact-links.json').read_text())['rows'] if r.get('origin')=='prompt_prose' and 'research_commit_gap' in r.get('target_ref','')])" prints 0 and exactly one cites row with origin prompt_prose.
- A second sync leaves that row's uses unchanged, so the family drained once.
- grep -c prompt_prose ~/.sase/agent_publication/standing_alerts.json prints 0.

[2026-11-20T16:52:27Z · sase-1tz.3.1.1] Verified: sase-core gains ArtifactLinkOriginWire::PromptProse (prompt_prose). It is automatic, commit-scoped, and usage-bearing like prompt_ref and is never relabeled, with an exhaustive ALL plus serde/from_name round-trip tests, prompt_prose upsert and cutover-observation tests, and a binding test that validates every ALL origin. sase-core sase tool run check passed (run 7d69ffa0). sase gains src/sase/sdd/artifact_link_origins.py: ARTIFACT_LINK_HOST_ORIGINS plus derived automatic, curated, commit-scoped, usage-bearing, and machine-trusted subsets, and all 7 literal call sites now point at it. tests/sdd/test_artifact_link_host_origins_contract.py round-trips each host origin through the real sase_core_rs.artifact_link_validate_row and artifact_link_upsert_row. Against the old binding it failed with the exact production error (unknown variant prompt_prose); against the rebuilt binding it passes (21 passed). Docs and CLI help now list prompt_prose. sase tool run check passed on the final tree (run bee22576; the earlier run f8f820b6 escalated to the full suite and was green). The host moves the pin through revision_pin when it commits both repos. Skew-guard analysis, athena before-numbers, and after-install commands are in the notes, plus one PROPOSED FOLLOW-UP (an origin capability probe).

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.3.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.1/README.md) | [sase-1tz.3.1.1](sase-1tz.3.1.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@0939137`](https://github.com/sase-org/sase-core/commit/0939137425c091bbbbbdc37b524e971268c16614) | feat(artifact-link): add prompt\_prose origin to ArtifactLinkOriginWire | [sase-1tz.3.1.1](sase-1tz.3.1.1.md) | 2026-11-20 11:53:27 EST |
| sase | [`eca97ab`](https://github.com/sase-org/sase/commit/eca97ab5a75ec31ff224af02472c03198a21f9e3) | feat(artifact-links): add host-origin constant and prompt\_prose binding contract test | [sase-1tz.3.1.1](sase-1tz.3.1.1.md) | 2026-11-20 11:55:13 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.3.1.1][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1tz.3.1.land][2] | Need the child scope and notes | 1 |
| read-by | [agent:sase-1uj.land][3] | Trace completion snapshot proposal to the prompt_prose CLI help change | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.land/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1uj.land/README.md

<!-- sase:referenced-by:end -->
