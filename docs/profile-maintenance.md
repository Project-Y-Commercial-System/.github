# Maintaining the organization profiles

Use this guide when URLs, repositories, infrastructure, access, or ownership
changes. See the [profile plan](profile-plan.md) for scope.

## Where to edit

| Change | Destination |
| --- | --- |
| Public introduction | `.github/profile/README.md` |
| General plan or maintenance process | `.github/docs/` |
| Internal links, repo map, architecture, AWS/Grafana details | `.github-private/profile/README.md` |
| Sources, owners, review records, internal questions | `.github-private/docs/application-reference.md` |
| Full setup, release, or incident procedure | The repo that owns the service |

Every file in `.github` is public, including drafts. Keep internal drafts in the
private repo or its separate local checkout. Neither profile should contain
passwords, tokens, private keys, credential-bearing URLs, or temporary signed
links. Link to the approved access procedure instead.

## Triggers and responsibility

Update when domains, API URLs, downloads, repo names/lifecycle, owners, default
branches, release workflows, setup, shared dependencies, AWS accounts/regions,
dashboards, access methods, or escalation contacts change.

The person making the underlying change should update the hub in the same work
or link a follow-up. Proposed cadence: assign a hub maintainer and review links
and ownership monthly. Record the actual reviewer and date.

## Update procedure

1. Read the private application reference and owning repo’s docs, config, scripts,
   and workflows. Check the branch that deploys the environment; default branches
   can differ from deployment branches.
2. Update authoritative service docs first if stale. If code, docs, and deployment
   disagree, record the discrepancy and ask the owner to resolve it.
3. Edit the relevant homepage section. Prefer links to maintained procedures.
4. Update source, owner, review date, and verification level in the private
   reference. Mark unknown values explicitly.
5. Preview tables and diagrams; check relative links and anchors. Use absolute
   GitHub URLs for cross-repo/profile links.
6. Open application/tool links with intended access. Authentication redirects can
   be expected; a failed unauthenticated request does not prove a private link is
   stale. Do not deploy or modify databases to validate documentation.
7. Review the diff for audience and credentials. Linking to a private resource
   does not make surrounding text private.
8. After merging to the relevant default branch, inspect the actual organization
   page in Public and Member views. Only then record live verification.

## Reference record

Use this format in the private application reference. Actual internal values
belong there, not in this public guide.

| Entry | Value/link | Source path and branch | Owner | Reviewed | Verification |
| --- | --- | --- | --- | --- | --- |
| Example service — staging | Fill in privately | Config/runbook | Named owner/team | YYYY-MM-DD | Source checked / live checked / needs confirmation |

Keep a short decision log for repo replacements, environment relationships,
moved dashboards, and retired entry points. Git history covers routine wording.

## Brief for a future update

> Update organization profiles for: [describe changes]. Read the profile plan,
> this guide, and the private application reference. Verify against owning repos
> and deployed branches. Keep internal details in `.github-private` and `.github`
> public-safe. Update the relevant profile and source/review record. Leave unknown
> owners/access details marked. Report changes, checks, and remaining questions.
> Prepare local edits unless publication is requested.
