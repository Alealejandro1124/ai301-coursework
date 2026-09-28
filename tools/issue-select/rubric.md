# Rubric: is this a good first issue?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever checks
you define here. It ships empty on purpose: the judgment is your work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where. Name the source
     (repo-facts block, issue body, comment thread, or the locations in
     references/evidence-guide.md). "The repo" is not a source; "the last
     5 default-branch commit dates" is.
   - Pass condition: a condition someone else could apply and get your
     answer. Prefer thresholds with numbers ("a maintainer commented
     within 30 days") over adjectives ("maintainer is responsive").
   - Weight: `required` (a fail here rejects the issue) or `preferred`
     (never changes the verdict; a nice-to-have that helps rank the
     issues you accept).

2. A verdict rule below the table: how the check grades combine into
   accept or reject, including how `unclear` is treated. The verdict
   space is binary. If you write no rule for `unclear`, the skill treats
   it as fail.

Cover what actually kills first contributions. The lecture named four
families: the maintainer is alive, the repo is in use, the scope fits a
newcomer, and nobody else is already on it. A rubric that ignores a family
will fail eval issues designed around that family.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| maintainer-alive | Repo facts: last 5 default-branch commit dates and commit authors. A bot commit counts only when it merged a human pull request. | Pass if at least 2 of the last 5 default-branch commits occurred within 90 days of the capture date and represent human maintainer activity or a bot merging a human PR. | required |
| maintainer-responsive | Repo facts: maintainer first-response sample from recently updated issues. | Pass if the sample shows at least one Owner, Member, or Collaborator first response within 30 days. | preferred |
| repo-in-use | Repo facts: archived flag, latest release date, and last push to any branch. | Pass if the repository is not archived and either its latest release was within 365 days or its last push was within 90 days of the capture date. | required |
| scope-fits | Issue body and comment thread, including maintainer comments. | Pass if the issue describes one bounded contribution, is not an umbrella/tracking issue or pure usage/support question, has no unresolved design debate, and no maintainer says the fix requires major/core-internals work. | required |
| unclaimed | Repo facts for this issue: assignees and linked PRs, plus claim comments in the issue thread. | Pass if there is no assignee, no open linked PR, and no claim comment from the last 30 days that still appears active. Closed unmerged PRs or clearly abandoned old claims do not fail this check. | required |
| contribution-policy | Repo facts: contribution policy, including CONTRIBUTING.md, dedicated AI policy files, and relevant PR/issue templates. | Pass unless the project explicitly bans AI-generated or AI-assisted contributions. Disclosure, testing, understanding, or human-review requirements pass. Silence also passes. | required |
| issue-well-specified | Issue body and maintainer comments. | Pass if the requested outcome is clear enough that a newcomer can tell what change is expected, such as a concrete bug, feature request, acceptance criteria, or maintainer clarification. | preferred |

## Verdict rule
<!-- State how the grades above combine into accept or reject, and how
unclear is treated. Example shape (write your own): "accept if every
required check passes; preferred checks never change the verdict, they
rank accepted issues; unclear counts as fail." -->

Accept only if every required check passes. Preferred checks never change the accept/reject verdict; they only help rank accepted issues. Treat `unclear` on a required check as a fail. Treat `unclear` on a preferred check as not passing that preference, without rejecting the issue.
