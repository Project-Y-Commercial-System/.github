# Organization profile plan

Drafted: 2026-10-05. Decision: public overview plus members-only team hub.

## Purpose and audience

Give teammates one starting point to open the application, find the right repo,
set up development, and reach operational tools. Keep the homepage short and
link to repository documentation for detailed procedures.

| View | Repository/path | Content |
| --- | --- | --- |
| Public | Public `.github/profile/README.md` | Product introduction and pointer to Member view |
| Member | Private `.github-private/profile/README.md` | Application links, repo map, development, operations, and help |

GitHub requires `.github-private` to have **private** visibility; internal
visibility does not work. Members can switch between Public and Member views.
The profile does not grant access to linked repos, AWS, or Grafana.
See [GitHub’s profile documentation](https://docs.github.com/en/organizations/collaborating-with-groups-in-organizations/customizing-your-organizations-profile).

## Member homepage layout

Use this order so frequent links appear first:

| Section | Include | Authoritative source |
| --- | --- | --- |
| Open the application | Prod/staging web, API, driver web, mobile downloads | Environment config and release docs |
| Application overview | Small data-flow diagram, API/client relationships, shared environment resources | Architecture and database docs |
| Repo map | Purpose, stack, lifecycle, and read-first documentation | Repo README, AGENTS.md, docs index |
| Working with repos | Clone layout, setup links, API contract, checks, release guidance | Setup docs, scripts, workflows |
| Operations | Grafana/dashboards, CloudWatch, AWS account/regions, sign-in and access guidance | Infra and observability runbooks |
| Help | Owners, access requests, incident/escalation channel | Confirmed team contacts |
| Updates | Review date and maintenance link | Private application reference |

Use descriptive links and explicit environment labels. Briefly explain role
requirements. Link to maintained runbooks instead of copying long procedures.

## Supporting documentation

Keep this plan and the [maintenance guide](profile-maintenance.md) here.
Keep a populated `docs/application-reference.md` in `.github-private` containing
source paths/branches, owners, review dates, verification levels, open questions,
and significant decisions. Application repos remain authoritative for setup,
implementation, and deployment; the profile is the navigation aid across them.

## Rollout

1. Review local public profile and private hub drafts.
2. Confirm URLs, owners, access contacts, AWS sign-in method, and repo lifecycle.
   Check live links using the intended access.
3. Create `.github-private` with private visibility and suitable team read access.
   Copy the private draft there, never into this public repository.
4. Publish each profile on its repository’s default branch.
5. Check the organization page signed out and signed in as an ordinary member.
   Verify linked private resources with that member’s permissions.
6. Optionally pin the six repos most useful to members.

Repository publication is tracked in Git history. The private application
reference tracks remaining ownership, access, and service verification work.
Profile pins are optional and are managed separately by organization owners.

## Completion criteria

- Members can reach the intended environments and operational tools directly.
- Contributors can find the repo to change and its setup instructions.
- Shared staging/production dependencies are clear in the private overview.
- Owners and access/escalation contacts are recorded without guessing.
- Public files contain only information intended for everyone.
- Links work and future changes have a repeatable update process.
