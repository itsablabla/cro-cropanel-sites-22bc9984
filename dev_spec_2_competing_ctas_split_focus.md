# Competing CTAs split focus — dev spec
Site: nomadinternet.com · Priority 2 · Urgent · Effort: Medium (2-5 days)

## Problem
Multiple CTAs with no hierarchy create choice overload and dilute the primary conversion path.

## Evidence (from the live site)
> CHECK COVERAGE | CHECK IF IT WORKS AT MY ADDRESS | SEE MY OPTIONS | GET STARTED | START CHAT | SEE WHAT I QUALIFY FOR | CHECK MY COVERAGE
> 7 distinct calls to action compete on the same page: “CHECK COVERAGE”, “CHECK IF IT WORKS AT MY ADDRESS”, “SEE MY OPTIONS”, “GET STARTED”, “START CHAT”, “SEE WHAT I QUALIFY FOR”, “CHECK MY COVERAGE”.

## Current state
cta: Multiple CTAs: CHECK COVERAGE, CHECK IF IT WORKS AT MY ADDRESS, SEE MY OPTIONS, GET STARTED, START CHAT, SEE WHAT I QUALIFY FOR, CHECK MY COVERAGE; notes: No clear hierarchy among CTAs.

## Required change
cta: Single primary CTA: CHECK MY COVERAGE; notes: Secondary actions as subtle links.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Secondary actions as subtle links.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_competing_ctas_split_focus` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 124,891 visitors per variant to detect a 8.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
