# GitHub Achievement Unlocks Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Create the strongest legitimate path toward the missing Pair Extraordinaire, Starstruck, and Galaxy Brain achievements while continuing useful public-repository work that also advances Pull Shark.

**Architecture:** Work in independent achievement lanes. Pair Extraordinaire is evidence-gated: only a real GitHub-linked human collaborator may be attributed. Starstruck is approached by improving the most discoverable public product repository rather than manufacturing stars. Galaxy Brain is prepared through existing repository Discussions, but accepted answers remain an external-human dependency.

**Tech Stack:** GitHub pull requests, Markdown documentation, GitHub Actions, Android/Kotlin repository documentation, GitHub Discussions.

**Spec:** `docs/superpowers/specs/2026-09-04-github-achievement-progression-design.md`

## Global Constraints

- No fake accounts, fabricated collaborators, meaningless PRs, bought stars, staged Discussions, review-policy bypasses, or weakened CI/security controls.
- Every merged PR must have a real repository reason and independently understandable scope.
- Preserve legitimate `Co-authored-by:` trailers only when a real second contributor materially contributed and the email is linked to that GitHub account.
- Treat Starstruck and Galaxy Brain as externally dependent; groundwork may be completed here but awards cannot be guaranteed.
- Public Sponsor remains excluded.

---

### Task 1: Audit Pair Extraordinaire eligibility without fabricating attribution

**Files:**
- Read-only audit of merged PRs and commits across `ORCHORDS/docs`, `ORCHORDS/OrchordsStudioAi`, `ORCHORDS/ORCHORDS`, and `ORCHORDS/OrchordsBrowserPilot`.

**Interfaces:**
- Consumes: GitHub PR author metadata, commit trailers, GitHub-linked contributor identities.
- Produces: one of two outcomes: a verified genuine qualifying collaborator path, or a documented external-human blocker.

- [ ] **Step 1: Search public ORCHORDS PR history for non-ORCHORDS, non-bot authors.**

Run the repository PR search excluding `ORCHORDS` and known bot authors.
Expected: identify a real external contributor if one exists; otherwise return an empty candidate set.

- [ ] **Step 2: Search merged commit history for account-linked human co-authors.**

Inspect `Co-authored-by:` trailers and reject AI/vendor/local-only identities or duplicate ORCHORDS identities.
Expected: only a real GitHub-linked human contributor is eligible.

- [ ] **Step 3: If a real contributor exists, verify the contribution is material and linked to a merged PR.**

Expected: GitHub visibly attributes both authors on a merged PR commit.

- [ ] **Step 4: If no real contributor exists, do not synthesize one.**

Record Pair Extraordinaire as blocked on genuine collaboration and move to Task 2.

### Task 2: Repair OrchordsStudioAi public onboarding and canonical repository links

**Files:**
- Modify: `ORCHORDS/OrchordsStudioAi/README.md`

**Interfaces:**
- Consumes: current canonical repository name `ORCHORDS/OrchordsStudioAi` and existing release/build workflows.
- Produces: a README whose badges and verification commands point at the actual public repository.

- [ ] **Step 1: Confirm the current README still references the legacy `ORCHORDS/OrchordsAI` path.**

Expected: Daily Build, Dependency Audit, attestation `--repo`, and signer-workflow references contain the legacy path.

- [ ] **Step 2: Create a temporary focused PR branch from current `main`.**

Branch name: `docs/canonical-studio-ai-links-20260905`.

- [ ] **Step 3: Replace only legacy repository URLs with canonical `ORCHORDS/OrchordsStudioAi` URLs.**

Exact replacements:
- `https://github.com/ORCHORDS/OrchordsAI/actions/workflows/daily-build.yml` → `https://github.com/ORCHORDS/OrchordsStudioAi/actions/workflows/daily-build.yml`
- `https://github.com/ORCHORDS/OrchordsAI/actions/workflows/dependency-audit.yml` → `https://github.com/ORCHORDS/OrchordsStudioAi/actions/workflows/dependency-audit.yml`
- `--repo ORCHORDS/OrchordsAI` → `--repo ORCHORDS/OrchordsStudioAi`
- `--signer-workflow ORCHORDS/OrchordsAI/.github/workflows/daily-build.yml` → `--signer-workflow ORCHORDS/OrchordsStudioAi/.github/workflows/daily-build.yml`

Do not change sponsorship terms, product naming, license, or unrelated documentation.

- [ ] **Step 4: Verify the branch diff is limited to canonical-link corrections.**

Expected: one changed file, no unrelated text changes, all replacement destinations are valid repository paths.

- [ ] **Step 5: Open a focused public PR.**

Title: `docs: point Studio AI README at canonical repository`

Body must explain the stale-path problem, list the corrected surfaces, and state that no product behavior changes.

- [ ] **Step 6: Check mergeability, review state, and applicable CI.**

Expected: no bypasses. If checks run, wait for their actual conclusion; fix failures rather than ignoring them.

- [ ] **Step 7: Merge only when repository gates permit it.**

Prefer squash merge for a clean `main` history if permitted.

- [ ] **Step 8: Re-fetch `main` and verify every legacy `ORCHORDS/OrchordsAI` README reference is gone.**

Expected: canonical repository references only.

### Task 3: Improve the organic Starstruck path without manufacturing stars

**Files:**
- Read: `ORCHORDS/OrchordsStudioAi/README.md`, repository metadata, topics, Discussions status.
- Modify only if a concrete discoverability defect is found after Task 2.

**Interfaces:**
- Consumes: public repository presentation and current star count.
- Produces: stronger first-run clarity and a clean public landing surface; independent users remain responsible for stars.

- [ ] **Step 1: Re-check the repository star count after the canonical-link PR lands.**

Expected baseline: record actual GitHub `stargazers_count`; do not infer achievement progress from follower counts.

- [ ] **Step 2: Audit the first-screen README for missing install/run/download guidance.**

Only create another PR if a real usability gap exists that is not already covered by `docs/BUILDING.md` or the current README.

- [ ] **Step 3: Do not create a second PR merely to increase Pull Shark count.**

If no meaningful additional gap exists, stop this lane until organic users star the repository.

### Task 4: Prepare the Galaxy Brain lane using real repository Discussions

**Files:**
- Read-only repository Discussion surface for `ORCHORDS/OrchordsStudioAi` and `ORCHORDS/OrchordsBrowserPilot`.

**Interfaces:**
- Consumes: genuine repository Q&A questions from other users.
- Produces: technically accurate answer drafts when a real question exists; posting/acceptance depends on available GitHub Discussion tooling and another user's acceptance.

- [ ] **Step 1: Confirm Discussions remain enabled on the two public product repositories.**

Expected: `has_discussions=true` on Studio AI and Browser Pilot.

- [ ] **Step 2: Look for genuine Q&A discussions from users other than ORCHORDS.**

Expected: use only real questions; do not seed/stage questions.

- [ ] **Step 3: If a genuine question exists, research and draft a complete answer grounded in source/docs.**

Expected: answer should solve the user's question independently of achievement value.

- [ ] **Step 4: If the connector lacks a Discussion reply action, stop at a ready-to-post draft.**

Do not substitute issue comments or fake Discussion activity.

### Task 5: Recalculate achievement state after the batch

**Files:**
- Read-only GitHub profile/activity evidence.

**Interfaces:**
- Consumes: merged PR counts, repository stars, genuine co-authored merged PR evidence, accepted Discussion answers.
- Produces: an evidence-only status report.

- [ ] **Step 1: Re-run merged-PR search for `author:ORCHORDS`.**

Record the searchable count, explicitly labeling it as GitHub Search history rather than GitHub's private achievement counter.

- [ ] **Step 2: Re-check public repository star counts.**

Record actual counts only.

- [ ] **Step 3: Report only achievements visible in the user's Achievements page as confirmed unlocked.**

Qualifying activity and visible awards must remain separate statuses.
