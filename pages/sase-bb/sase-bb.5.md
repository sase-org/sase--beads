# Bead: sase-bb.5 — Published pages, ACE Plans tab, mobile bridge, and declaration

[Bead Pages](../README.md) / [sase-bb](README.md) / sase-bb.5

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-bb.5` · **Size:** small
**Created:** 2026-07-30 14:53:58 UTC · **Closed:** 2026-07-30 17:25:54 UTC
**Plan:** [202607/spec\_artifact\_references.md](https://github.com/sase-org/sase--plans/blob/main/202607/spec_artifact_references.md)

## Description

surfaces: render bead references on published pages and in the ACE Plans detail panel, return them through the mobile bridge, and let `sase artifact create` attach the reference it just minted to a bead.

## Notes

[2026-07-30T17:25:54Z · sase-bb.5] Implemented the four surfaces phase: (1) bead pages render a '## References' section from issue.refs, hosted-linked via plan_url/bead_url/agent_url/commit_url where the resolver can produce a URL and md-escaped plain text otherwise, including for unparseable entries; (2) the ACE Plans detail panel adds a 'References' property row and a preview-markdown block, rendering stored references verbatim with no resolution on any render path; (3) stored references joined plans_filtering's haystack so the Plans filter matches them, matching sase bead search; (4) the mobile bridge returns a new 'refs' field on the bead detail wire, resolved where this machine resolves and stored-form otherwise; (5) sase artifact create gained -b/--bead (bare = SASE_BEAD_ID, or an explicit id) which attaches the minted file: reference through the same sase bead ref add write path, failing before the artifact is created when the id is missing or unknown. Verified: just check fully green (fmt, keep-sorted, ruff, mypy, pyscripts, changelog, symvision, toobig, SASE validation, 24k+ tests); new tests cover page rendering with zero/one/unresolvable/unparseable references plus the escaping assertion, the Plans-detail row and filter corpus, the mobile helper's resolved and unresolved shapes, and artifact create --bead for bare, explicit, missing-environment, and unknown-bead cases; three ACE PNG goldens regenerated for the one-row detail-panel shift after inspecting the diffs; live sase store read-only checks (sase bead ref list, sase bead doctor) show no artifact references and only pre-existing sase-9z design-reference findings.

## Dependencies

- **Depends on:** [sase-bb.3](sase-bb.3.md) ✓
- **Blocks:** [sase-bb.6](sase-bb.6.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-bb.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-bb.5/README.md) | [sase-bb.5](sase-bb.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`87ece3e`](https://github.com/sase-org/sase/commit/87ece3ee34d613780923e2d9d9a2f0349ff12f0a) | feat(artifact): surface bead references and attach on create | [sase-bb.5](sase-bb.5.md) | 2026-07-30 17:27:18 |
