# Duplicate forms create dead ends — dev spec
Site: nomadinternet.com · Priority 3 · High · Effort: Medium (2-5 days)

## Problem
Multiple identical CONTINUE forms on the same page create ambiguity about which form advances the funnel and risk duplicate submissions.

## Evidence (from the live site)
> (see report)

## Current state
cta: Multiple CONTINUE forms; notes: Duplicate forms on same page.

## Required change
cta: Single CONTINUE form; notes: Only one submission path per view.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Only one submission path per view.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_duplicate_forms_create_dead_ends` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 315,206 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
