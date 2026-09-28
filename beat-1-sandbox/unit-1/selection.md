# Unit 1 — Issue Selection

Path: `beat-1-sandbox/unit-1/selection.md`

Record of the issue carried into Unit 2, and of the evaluation runs that produced
`eval-run.txt`. This file is graded at the path above; a copy kept anywhere else in
the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the
wrong label is not graded.

---

## Selected issue

**Issue link**

https://github.com/codepath/pathreview-ai301-fa26-s3/issues/57

**Verdict output**


[Your skill's live-mode output for this issue, pasted verbatim and ending with the
fenced JSON verdict block. A summary does not satisfy this field.]

**The verdict must record `accept` for this issue.** Choose an issue your own skill
accepts. If your skill rejects every candidate you try, that is a signal about your
rubric rather than about the issues: revise it and re-run — retries are unlimited and a
partial re-run costs about $0.20 — or run the skill on different candidates. Output
recording `reject` for the issue you chose earns no credit for this field.

```
issue-select grading result
Mode: live (candidate is inside the scoped source: codepath/pathreview-ai301-fa26-s3)
House rule applied: Path Review is a classroom, so classmates' claim comments do not block.

Issue #57 - "Tech detector counts vendored and build-output files, skewing language detection"
State: open. Labels: bug, good first issue, agent, tier-1.
Opened 2026-09-10 by Aburke225 (author_association: COLLABORATOR).
URL: https://github.com/codepath/pathreview-ai301-fa26-s3/issues/57

CHECKS

- maintainer-alive - pass
  All 5 last main commits are human (Aburke225, a COLLABORATOR): 3x 2026-09-16 (12d)
  and 2x 2026-08-24 (35d) - at least 2 within 90 days.

- maintainer-responsive (preferred) - fail
  Across the 8 most recently updated issues (some with 15-31 comments), zero first
  responses carry an Owner/Member/Collaborator association.

- repo-in-use - pass
  isArchived: false, last push 2026-09-16 (12 days ago, under 90); no releases, but the
  push arm satisfies the condition.

- scope-fits - pass
  One concrete bug with a runnable repro and two named failing tests; no umbrella list,
  no design debate, no linked PRs at all (so no abandoned attempts).

- unclaimed - pass
  assignees: [], zero linked PRs, zero PRs referencing 57; the two claim comments
  (ApoorvThite, BishalChhetri) are both NONE - classmates, ignored per house rule.

- contribution-policy - pass
  docs/CONTRIBUTING.md and the PR template mention no AI restriction; requirements are
  CI-green, tests, and removing the xfail marker.

- issue-well-specified (preferred) - pass
  Body gives observed 'JavaScript' vs expected 'Python', plus test_node_modules_excluded
  and test_build_directory_excluded.

VERDICT

Every required check passes -> accept. The one preferred miss is maintainer
responsiveness: the maintainer commits regularly but does not appear to reply in issue
threads, so expect no clarification - the issue body has to be enough, and here it is.

FIT NOTE

This lands squarely in your strongest language (Python), with a bounded _should_skip_file
path-matching fix, a reproducible case, and two existing tests that define "done" - the
kind of navigate-and-debug-a-real-codebase work you said you wanted, with no framework you
haven't touched. One caveat worth knowing before you start: BishalChhetri already posted a
full root-cause analysis on 2026-09-28 (the leading-slash patterns never match
repo-root-relative paths), so the diagnosis is public. Per the house rule that costs you
nothing - credit attaches to your PR - but do the reproduction yourself rather than taking
their write-up on faith.

```json
{
  "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/57",
  "checks": [
    {"name": "maintainer-alive", "grade": "pass",
     "evidence": "Last 5 main commits all by human COLLABORATOR Aburke225: 2026-09-16 (x3) and 2026-08-24 (x2), all within 90 days of 2026-09-28."},
    {"name": "maintainer-responsive", "grade": "fail",
     "evidence": "In the 8 most recently updated issues (up to 31 comments each), no comment has author_association OWNER, MEMBER, or COLLABORATOR."},
    {"name": "repo-in-use", "grade": "pass",
     "evidence": "isArchived=false; latestRelease=null but last push 2026-09-16, 12 days before capture (< 90)."},
    {"name": "scope-fits", "grade": "pass",
     "evidence": "Single concrete bug with a runnable repro and two named failing tests (test_node_modules_excluded, test_build_directory_excluded); no umbrella list, design debate, or prior linked PRs."},
    {"name": "unclaimed", "grade": "pass",
     "evidence": "assignees: [], no linked PRs and no PR referencing #57; the two claim comments are author_association NONE (classmates), ignored per the Path Review house rule."},
    {"name": "contribution-policy", "grade": "pass",
     "evidence": "docs/CONTRIBUTING.md and .github/PULL_REQUEST_TEMPLATE.md contain no AI restriction; only CI-green, tests, and xfail-marker removal are required."},
    {"name": "issue-well-specified", "grade": "pass",
     "evidence": "Body states observed 'JavaScript' vs expected 'Python' with reproduction code and the two failing test names."}
  ],
  "verdict": "accept"
}
```

```

---

## Eval iterations

Quote source text directly in each field below. Paraphrase does not satisfy them.

**Run history**

[The agreement score of each run you did, in order. A single run is a complete answer if
only one run occurred. **The last score in your list must match the agreement line in the
`eval-run.txt` you committed** — that file is the record of your final run.]

`agreement: 0/1 scored items`

One attempted full run stopped before producing an agreement score with:
`UnicodeEncodeError: 'charmap' codec can't encode character '\u2728' in position 11733: character maps to <undefined>`

`agreement: 1/1 scored items`

`agreement: 17/20 scored items  (bar: 18/20: below the bar)`

`agreement: 1/3 scored items`

`"agreement": [1, 2]`

`agreement: 2/3 scored items`

`agreement: 19/20 scored items  (bar: 18/20: PASS)`

**Issue analysis**

[One scored issue, identified by id (`issue-01` through `issue-20`; the `calib-`
issues are not scored). State your rubric's decision, the gold label, and the
reasoning that produced your rubric's result.]

`issue-19  accept  reject   NO     failed: scope-fits`

For `issue-19`, my rubric's decision was `reject` and the gold label was `accept`. The detailed result for my required `scope-fits` check stated:

`"Issue lists two unresolved potential causes plus three additional implementation suggestions (multi-processing, category-gated matching, separate-thread rewrite application) with 0 comments settling direction"`

Because `scope-fits` is a required check, that failure produced the overall `reject` result. I read the multiple possible causes and implementation directions as evidence that the path forward was not settled enough for a first contribution.

**Check rationale**

[One check from the `rubric.md` uploaded to `tools/issue-select/`, quoted as it is
currently written, with the reasoning behind its current form.]

> `| scope-fits | Issue body, comment thread, and linked-PR history. | Pass if the issue asks for one coherent outcome a newcomer can work toward, even if it spans multiple files, lists several implementation steps, or gives multiple possible root causes or implementation ideas for the same concrete bug. Multiple technical hypotheses do not count as unresolved design debate by themselves. Fail if it is an umbrella/tracking issue, a pure usage/support request, has unresolved product or feature-design debate, explicitly requires broad core-internals work beyond a bounded first contribution, or shows repeated abandoned implementation attempts (for example, 2 or more closed unmerged linked PRs) without a settled path forward. | required |`

I changed this check after my first full evaluation because the original version was too strict about issues that involved multiple files or multiple possible causes. I wanted it to distinguish one coherent outcome with several technical details from an issue that is genuinely broad, still being designed, or has a history of abandoned implementation attempts.

**Trade-offs**

[What the quoted check gives up. Any one of these is a complete answer: an issue whose
result it changes, a canary you re-ran with `--only`, a case you accept it will miss, or a
stated reason nothing changed elsewhere. "Nothing changed, and here is how I know" earns
the point in full when the reason follows.]

`issue-19  accept  reject   NO     failed: scope-fits`

The trade-off is that this check can still reject a concrete issue when its technical direction appears unsettled. `issue-19` remained the one disagreement in my final run. I accepted that miss instead of loosening the check further because the final evaluation reached `19/20 scored items  (bar: 18/20: PASS)` and passed every category floor. Further loosening the check could also allow genuinely broad or unresolved issues to pass.

---

## Selection rationale

Graded on whether all three are answered, in your own words. Not on how good the
reasoning is, and not on length — a short honest answer to each earns the full marks.
This is also the basis for the claim comment you write in Unit 2.

**Selection rationale**

[Answer all three:

1. The issue's fit to your interests and to the time available.
2. What the verdict identified correctly, and what you weighed that the rubric could
   not.
3. The anticipated difficulty in claiming it.]

1. Issue #57 fits my interests and the time available because it is a focused Python debugging task. The issue gives me a reproducible example and two named failing tests, `test_node_modules_excluded` and `test_build_directory_excluded`, so I have a clear way to reproduce the problem, make a targeted change, and verify the result. It also gives me the kind of experience I want with navigating and debugging an unfamiliar production codebase without requiring me to learn an entirely new framework first.

2. The verdict correctly identified that the repository is active, the issue has a bounded scope, there are no linked pull requests, the contribution policy does not restrict AI-assisted work, and the issue is well specified enough to work from. I also weighed my own comfort with Python and my goal of getting better at debugging unfamiliar code. My rubric can judge whether an issue is suitable, but it cannot fully measure which accepted issue I personally feel most prepared to understand and explain.

3. I expect the main difficulty in claiming the issue to be coordination with classmates. There are already classmate claim comments, and another student posted a root-cause analysis. The Path Review house rule means those comments do not block me, but I still need to reproduce and understand the problem myself instead of relying on someone else's diagnosis.

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/issue-select/`.
