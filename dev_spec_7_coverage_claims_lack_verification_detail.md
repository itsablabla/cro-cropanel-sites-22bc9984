# Coverage claims lack verification detail — dev spec
Site: nomadinternet.com · Priority 7 · Medium · Effort: Medium (2-5 days)

## Problem
Unsubstantiated coverage claims without a visible coverage map or verification explanation undermine trust in the coverage-check funnel.

## Evidence (from the live site)
> A section heading reads “You qualify for everything”.
> A section heading reads “Join America's Largest Wireless Internet Provider Featuring”.
> 3 distinct calls to action compete on the same page: “CHECK COVERAGE”, “SEE WHAT I QUALIFY FOR”, “CHECK MY COVERAGE”.

## Current state
cta: CHECK COVERAGE, SEE WHAT I QUALIFY FOR, CHECK MY COVERAGE; notes: Claims lack supporting detail.

## Required change
cta: CHECK MY COVERAGE; notes: Add coverage map and explanation of verification.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add coverage map and explanation of verification.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_coverage_claims_lack_verification_detail` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
