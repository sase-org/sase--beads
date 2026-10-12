# Bead: sase-1jx.13.2 — Make GitHub create and discovery correct

[Bead Pages](../README.md) / [sase-1jx.13](sase-1jx.13.md) / sase-1jx.13.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jx.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.land.md) · **Assignee:** `sase-1jx.13.2` · **Size:** medium
**Created:** 2026-10-12 14:55:56 EDT · **Closed:** 2026-10-12 15:31:39 EDT
**Plan:** [202610/new\_project\_wizard\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202610/new_project_wizard_landing_repairs.md)

## Description

gh-repairs: in sase-github, stop template creates from passing flags gh rejects, verify every requested setting after create, re-probe after a create timeout, paginate team and org lists, strip ports when matching hosts, fix numbered-copy and two-level host detection, keep Enterprise hosts in canonical refs, and document SASE_GITHUB_CLONE_TIMEOUT.

## Notes

[2026-10-12T19:31:39Z · sase-1jx.13.2] Verified in sase-github: template creates omit --add-readme/-g/-l/-t and reject those conflicts before any subprocess; post-create view checks hasIssuesEnabled, hasWikiEnabled, description, homepageUrl; create timeout 120s re-probes and reports exists; team and org-membership APIs use --paginate; parse_github_remote_url strips ports so ssh://git@github.com:22/... detects as gh; numbered copies match stripped origin identity while literal *_N repos do not; two-level layout stays github.com when the default host is Enterprise; non-default hosts keep host-qualified canonical refs that parse/clone/create/resolve accept; SASE_GITHUB_CLONE_TIMEOUT and onboarding hooks documented. sase tool run check 83ad10df1f4dad63cb066fcf6756e0db: 341 passed. epic-symbols: none.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jx.13.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.13.2/README.md) | [sase-1jx.13.2](sase-1jx.13.2.md) | 0 |
