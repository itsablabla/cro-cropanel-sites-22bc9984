# Pricing shown before qualification — dev spec
Site: nomadinternet.com · Priority 5 · Medium · Effort: Low (0.5-2 days)

## Problem
Displaying prices before coverage confirmation creates premature commitment barriers and confusion about applicable plans.

## Evidence (from the live site)
> $99.95 /month
> $129.95 /month
> $0.00 (one-time)
> $99.99 (one-time)

## Current state
notes: Prices shown prominently before qualification.

## Required change
notes: Sequence qualification before pricing or label as examples.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Sequence qualification before pricing or label as examples.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_pricing_shown_before_qualification` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
