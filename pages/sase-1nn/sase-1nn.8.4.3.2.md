# Bead: sase-1nn.8.4.3.2 — Repair the Master Gate and Full CI test-lane reds

[Bead Pages](../README.md) / [sase-1nn.8.4.3](sase-1nn.8.4.3.md) / sase-1nn.8.4.3.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.13x](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.13x.md) · **Assignee:** `sase-1nn.8.4.3.2` · **Size:** medium
**Created:** 2026-10-24 16:37:48 EDT · **Closed:** 2026-10-24 17:06:52 EDT
**Plan:** [202610/v0\_18\_1\_release\_unblock.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_1_release_unblock.md)

## Description

gate-tests: add the missing monitor --weight completion metadata and regenerate the CLI completion snapshot, verify the autonomy contract cluster is resolved, and fix every deterministic or recurring non-visual Full CI failure.

## Notes

[2026-10-24T21:06:44Z · sase-1nn.8.4.3.2] PROPOSED FOLLOW-UP: Triage the isolated ACE image modal resize timeout in tests/ace/tui/modals/test_preview_panel_image_modal.py::test_image_modal_resize_rerenders_with_new_viewport. It failed once in Full CI run 40109539212, test job 120943525406 at SHA 7b1b43755821fb4b6fe9ab8f51d09fcff0e46879; bead search found no exact task owner. Existing epic triage owner: sase-1nn.8.4.

[2026-10-24T21:06:52Z · sase-1nn.8.4.3.2] Added monitor start weight integer completion metadata and regenerated the CLI snapshot; fixed recurring archive readiness and pulse focus failures. Verified focused completion tests (379 passed), autonomy and gate-capacity suites (254 passed), archive tests (6 passed), just fix, and sase tool run check (succeeded). Latest Full CI test jobs passed; the remaining visual-test failure belongs to the separate visual phase. Ran epic-symbols (none remained) and recorded the one-off image-modal CI follow-up for the sase-1nn.8.4 land agent.

## Dependencies

- **Blocks:** [sase-1nn.8.4.3.4](sase-1nn.8.4.3.4.md) ◐ · ⧖ 2026-10-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nn.8.4.3.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nn.8.4.3.2/README.md) | [sase-1nn.8.4.3.2](sase-1nn.8.4.3.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e788b17`](https://github.com/sase-org/sase/commit/e788b1718a92758732fa043df6b3a09a217cc4b1) | fix(ace): stabilize archive tests and monitor completion hints | [sase-1nn.8.4.3.2](sase-1nn.8.4.3.2.md) | 2026-10-24 17:07:52 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1nn.8.4.3.2][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nn.8.4.3.2/README.md

<!-- sase:referenced-by:end -->
