# Bead: sase-196.1 — Commit prompt-archive objects with their prompts

[Bead Pages](../README.md) / [sase-196](README.md) / sase-196.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ry.f0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ry.f0.md) · **Assignee:** `sase-196.1` · **Size:** medium
**Created:** 2026-09-25 09:05:34 EDT · **Closed:** 2026-09-25 10:21:45 EDT
**Plan:** [202609/agents\_sidecar\_orphan\_objects.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_sidecar_orphan_objects.md)

## Description

archive-objects: stage files/objects in both prompt-archive commit paths, never clean it, sweep hash-valid pending objects (including today's orphans), and quarantine invalid ones. Pending objects must not break the pre-commit pull.

## Notes

[2026-09-25T14:21:45Z · sase-196.1] Prompt-archive objects now publish with their prompts. New prompt_archive/archive_objects.py owns the files/objects root and the hash-valid sweep (canonical path, prefix match, regular file, sha256 == name); invalid pending files are moved to <git-dir>/sase-quarantine/objects/<utc-ts>/ and logged. git_ops.py splits REGENERABLE_ARCHIVE_PATHS (prompts, artifacts) from PUBLISHED_ARCHIVE_PATHS (adds files/objects); cleaning never touches objects and git_sync_transaction imports the published set. Both publication paths (publish.py and the full sync) commit pending objects as 'chore(agents): publish pending prompt-archive objects' before git pull --rebase; the full sync also commits export-written objects in their own commit so a rejected-push retry (reset --hard HEAD^) cannot delete them. Tests: pool-staged object committed with its prompt, incident-shape three orphans, quarantine, clean-never-deletes, two-clone remote-tracked object (pull would otherwise refuse), Rust layout pin, full-sync stage/failure/push-race retry. New tests fail on the old code. Verified with sase tool run check (lint gates + scoped tests) passing. PROPOSED FOLLOW-UP (phase archive-validation): _is_valid_archive_object and _pending_archive_objects are private now because symvision saw no non-test consumer; make them public when validate/doctor consume them.

## Dependencies

- **Blocks:** [sase-196.2](sase-196.2.md) ◐ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-196.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-196.1/README.md) | [sase-196.1](sase-196.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f648e88`](https://github.com/sase-org/sase/commit/f648e88e4870bc7024a49d873a1ef08f8382b427) | fix(agents-sync): commit prompt-archive objects with their prompts (sase-196.1) | [sase-196.1](sase-196.1.md) | 2026-09-25 10:22:50 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-196.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-196.1/README.md

<!-- sase:referenced-by:end -->
