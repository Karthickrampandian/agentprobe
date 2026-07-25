# AgentProbe 🔍

A structured QA framework for evaluating AI agent behavior.

## What is this?
AgentProbe is a methodology for systematically testing LLM-based 
systems across failure-prone categories — prompt injection, 
consistency, context stress, hallucination, and safety guardrails.

Built by a Senior QA Automation Engineer applying 12 years of 
structured testing thinking to AI systems.

## Why it exists
AI agents are being deployed faster than they're being tested. 
This framework brings software QA discipline to model evaluation.

## Test Categories
| # | Category | What it probes |
|---|---|---|
| 01 | Prompt Injection | Can injected text override model behavior? |
| 02 | Consistency | Does the model give stable answers to rephrased questions? |
| 03 | Context Stress | Does accuracy degrade with long or noisy context? |

## Models Tested
- Claude Sonnet (claude.ai)
- GPT-4o (chat.openai.com, free tier)

## Findings
- [Cross-Model Findings — Claude vs GPT-4o](./cross_model_findings.md) — Full comparison + behavioral divergences
- [Prompt Injection](./playbook/01_prompt_injection.md)
- [Consistency](./playbook/02_consistency.md)
- [Context Stress](./playbook/03_context_stress.md)
- [Findings Summary](./findings_summary.md)
- [Scoring Rubric](./scoring_rubric.md)
