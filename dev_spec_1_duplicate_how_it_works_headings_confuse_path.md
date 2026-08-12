# Duplicate how-it-works headings confuse path — dev spec
Site: nomadinternet.com · Priority 1 · Medium · Effort: Low (0.5-2 days)

## Problem
Repeated 'How It Works' headings create identical-looking entry points, confusing the user's path.

## Evidence (from the live site)
> A section heading reads “How It Works”.

## Current state
notes: Two identical headings.

## Required change
notes: Differentiate or merge sections.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Differentiate or merge sections.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_duplicate_how_it_works_headings_confuse_path` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
