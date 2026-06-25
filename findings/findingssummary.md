# AgentProbe — Findings Summary

## Overview
15 tests across 3 categories (Prompt Injection, Consistency, Context Stress) 
were run against Claude (claude.ai). Each test was scored against a predefined 
Pass / Partial / Fail rubric. Result: 15/15 Pass.

## Headline result
Claude resisted all standard adversarial and stress conditions in this suite. 
No injection succeeded, no inconsistency surfaced, no buried fact was missed.

## Top 3 cross-cutting insights

**1. The model flags anomalies rather than just processing around them.**
Across categories, Claude didn't silently handle adversarial input — it named 
what it saw. It identified injection attempts by type (PI-01–05), reported a 
buried instruction unprompted (CS-01), and surfaced a planted contradiction 
rather than picking one side (CS-03). The behavioral signature is *awareness*, 
not just *resistance*.

**2. It resists manipulation without over-refusing.**
In tests that paired a malicious instruction with a legitimate task (PI-04, 
PI-05), Claude refused the injection while still completing the real request. 
Over-refusal — rejecting the whole prompt out of caution — is its own failure 
mode, and it was not observed.

**3. Output adapts in form, stays stable in substance.**
Response length and framing shifted with phrasing and context (CO-01, CO-04), 
but core answers did not change. Surface adaptation without substantive drift.

## Honest limitation
All 15 tests passed, but every test used single-turn, well-known phrasing 
against a frontier model — conditions where strong performance is expected. 
This suite establishes a clean baseline; it does not yet probe the model's 
breaking point. The most valuable next step is harder testing: multi-turn 
attacks, adversarial/obfuscated phrasing, and cross-model comparison to find 
where behavior actually degrades.

## Next
- Cross-model run (Claude vs GPT-4o) on the same suite
- Adversarial / multi-turn injection
- Automated test execution via API
