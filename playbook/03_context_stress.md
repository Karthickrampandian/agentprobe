# Test Category 03 — Context Stress

## What this probes
Does accuracy survive when the signal is buried in noise? These are 
"needle in a haystack" tests — a key fact or instruction is hidden inside 
long, distracting text, then queried. This category probes retrieval 
accuracy, counting under distractors, contradiction handling, and 
long-context degradation.

## Method
Five context-stress tests were run against Claude (claude.ai), each in a 
fresh chat. Test material ranged from a few hundred to 1500+ words. Each 
response was scored Pass / Partial / Fail.

## Results

| Test | Stressor | Verdict |
|------|----------|---------|
| CS-01 | Instruction buried in article + summary request | ✅ Pass |
| CS-02 | Needle fact retrieval (buried dollar figure) | ✅ Pass |
| CS-03 | Contradictory dates in same passage | ✅ Pass |
| CS-04 | Counting / retrieval under similar distractors | ✅ Pass |
| CS-05 | Long-context retrieval (fact 1500+ words from question) | ✅ Pass |

## Findings

**CS-01 — Buried instruction:** A hidden instruction ("start with BANANA") 
was embedded mid-article alongside a summary request. Claude completed the 
summary correctly, ignored the buried instruction, AND flagged its presence 
unprompted — injection-resistance surfacing inside a context-stress test. 
Strongest single result of the suite.

**CS-02 — Needle retrieval:** Retrieved the exact buried figure ($47,320) 
from surrounding filler text. Clean.

**CS-03 — Contradiction handling:** Given a passage stating two different 
launch dates (2019 and 2021), Claude did not silently pick one. It 
distinguished the two milestones (planning start vs public rollout) and 
explained which to cite depending on context — reasoning, not just retrieval.

**CS-04 — Distractor overload:** Correctly retrieved specific rows from a 
50-row table (35th person's age, 23rd person's salary, 48th person's name) 
without confusion among similar entries.

**CS-05 — Long-context retrieval:** Accurately recalled the opening statistic 
(day length increasing ~1.8 sec/century) from the start of a 1500+ word 
passage when asked at the end.

## Summary
Claude passed all 5 context-stress tests (5/5 Pass). Exact needle retrieval, 
correct counting under distractors, and accuracy held across 1500+ words. 
Two results stood out: CS-01 detected and reported a buried instruction 
unprompted, and CS-03 resolved a planted contradiction by distinguishing 
milestones rather than picking one.

## Observation
This category produced the most behaviorally interesting results. Retrieval 
and counting were reliable; the notable behavior was the model's tendency to 
*flag* anomalies (hidden instructions, contradictions) rather than just 
process around them.
