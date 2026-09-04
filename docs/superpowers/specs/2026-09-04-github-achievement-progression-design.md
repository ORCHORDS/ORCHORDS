# GitHub Achievement Progression Design

Date: 2026-09-04
Owner: ORCHORDS

## Goal

Advance every realistically obtainable non-paid GitHub profile achievement through legitimate project work, without fake accounts, fabricated collaborators, meaningless PRs, bought stars, staged Discussions, review-policy bypasses, or CI/security weakening.

## Current verified baseline

- Pull Shark: 817 merged PRs authored by ORCHORDS; next community-tracked tier is 1,024, leaving 207 legitimate merged PRs.
- Quickdraw: already visible and repeatedly re-qualified by sub-five-minute real maintenance PRs; no higher tier to pursue.
- Pair Extraordinaire: already visible; higher tiers depend on genuine co-authored merged PRs.
- YOLO: multiple recent ORCHORDS-authored PRs were merged with zero submitted reviews; GitHub profile rendering may lag.
- Starstruck: current public ORCHORDS repositories checked are at 2 stars each; independent users must supply the remaining stars.
- Galaxy Brain: OrchordsStudioAi has Discussions enabled and is the natural ORCHORDS discussion surface; accepted answers still depend on other users.
- Public Sponsor: excluded because it requires payment.
- Experimental achievements such as Open Sourcerer / Heart On Your Sleeve are treated as bonus outcomes only, never as a reason for spam.

## Repository scope

Use all current public ORCHORDS repositories where there is genuine work:

1. ORCHORDS/docs
2. ORCHORDS/OrchordsStudioAi
3. ORCHORDS/ORCHORDS
4. ORCHORDS/OrchordsBrowserPilot

Private repositories may still contribute to Pull Shark when normal product work genuinely requires PRs, but public-repo work is preferred when it also improves discoverability and experimental achievement coverage.

## Lane A — Pull Shark x4

Primary target: move from 817 to 1,024 legitimate merged PRs.

Method:
- Solve real open issues and maintenance gaps already present in repositories.
- Prefer small, independently verifiable slices when that matches the underlying issue structure.
- Every PR must have a concrete project reason, clear scope, and evidence appropriate to the change.
- Do not split one atomic change into artificial PR fragments solely to increase count.
- Merge only when the repository's actual required gates are satisfied.
- Re-check the merged-PR count periodically rather than assuming progress.

## Lane B — Pair Extraordinaire tiers

Method:
- Preserve valid `Co-authored-by:` trailers whenever a real second contributor materially contributed.
- Never add a fake person, bot identity, vendor name, or duplicate ORCHORDS identity merely to trigger the badge.
- Prefer already-existing real collaboration history before seeking new qualifying events.
- Count only co-authored commits that land through merged PRs and are recognized by GitHub attribution.

## Lane C — Starstruck

Primary promotional target: OrchordsStudioAi, unless later repository metrics show another public project has stronger organic traction.

Method:
- Improve first-screen README clarity, install/run instructions, screenshots/demo material where useful, examples, topics, description, releases, contribution guidance, and canonical links.
- Cross-link related public ORCHORDS projects only where relevant.
- Do not buy stars, use alternate accounts, run star exchanges, or solicit irrelevant communities.
- Measure genuine star count after meaningful public-product improvements.

## Lane D — Galaxy Brain

Primary surface: OrchordsStudioAi because Discussions is enabled.

Method:
- Use real Q&A discussions only.
- Provide technically accurate, researched answers where ORCHORDS has genuine expertise.
- Never stage questions, ask for acceptance, coordinate acceptance, or answer from sockpuppets.
- Accepted-answer count is an external-human dependency and cannot be guaranteed from this connector alone.

## Lane E — YOLO / Quickdraw

These have no higher tiers.

Method:
- Do not farm repeated copies.
- Preserve legitimate qualifying history when normal maintenance naturally meets the trigger.
- Treat additional qualifying events only as redundancy while waiting for GitHub profile processing.

## Lane F — Experimental achievements

Open Sourcerer / Heart On Your Sleeve or other experimental achievements are opportunistic only.

Method:
- Public-repo PR work may naturally add qualifying history.
- Reactions are used only when they are normal, useful GitHub interaction.
- Never generate reaction spam or low-value cross-repo churn.

## Execution loop

For each batch:

1. Inspect live main, open issues, recent commits, existing PRs, and CI state.
2. Select the smallest genuine high-value issue slice that is currently actionable.
3. Verify the repository's current workflow and merge policy before changing anything.
4. Implement with tests or documentation checks appropriate to the change.
5. Open a focused PR when a PR is the repository's normal path and achievement progress would legitimately result.
6. Wait for the applicable checks; fix failures rather than bypassing them.
7. Merge only after the real gates pass.
8. Re-check main and the merged-PR total before beginning the next slice.
9. Periodically re-check public star counts, Discussion availability, and visible achievement state where accessible.

## Integrity constraints

Never:
- create fake contributors or sockpuppets;
- manufacture dummy issues/PRs/commits;
- self-star through controlled accounts;
- buy stars or accepted answers;
- weaken CodeQL, Dependabot, required checks, branch protection, review requirements, or security controls to earn a badge;
- close broad issues merely because one achievement-friendly slice landed;
- claim a badge is visible unless GitHub's profile display is actually observed.

## Success criteria

- Pull Shark reaches the next tier through useful merged work.
- Pair Extraordinaire advances only when genuine collaboration supports the next threshold.
- At least one public ORCHORDS project materially improves its discoverability toward Starstruck.
- Galaxy Brain answers, when possible, are real, useful, and independently accepted.
- YOLO processing is re-checked but not spam-farmed.
- Public Sponsor remains intentionally excluded.
- Repository quality, CI health, and security posture are better after the program than before it.
