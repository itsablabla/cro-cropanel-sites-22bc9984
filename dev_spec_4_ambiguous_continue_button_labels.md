# Ambiguous CONTINUE button labels — dev spec
Site: nomadinternet.com · Priority 4 · High · Effort: Low (0.5-2 days)

## Problem
The submit button labeled only CONTINUE fails to communicate the next step, increasing cognitive effort at the interaction point.

## Evidence (from the live site)
> (see report)

## Current state
cta: CONTINUE; notes: Button label is vague.

## Required change
cta: Check My Coverage; notes: Descriptive action label.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Descriptive action label.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_ambiguous_continue_button_labels` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 315,206 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
