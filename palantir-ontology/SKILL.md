---
name: palantir-ontology
description: Design Palantir-inspired local decision systems from messy business workflows, codebases, datasets, tickets, policies, and operating documents. Use when Codex needs to turn a real-world problem into an ontology-driven AI operating model with objects, actions, permissions, human review points, evaluation criteria, and an MVP implementation path.
---

# Palantir Ontology

## Overview

Turn a vague business problem or local context into a concrete `Decision System Spec` that resembles the useful parts of Palantir's public methodology without claiming proprietary access. Model the world as objects, signals, actions, permissions, and review boundaries; then produce an implementation-ready operating design that can run inside Codex, Claude Code, or a local toolchain.

## Core Principle

Design around the decision, not the prompt.

Treat prompts as implementation details inside a larger system that defines:
- what exists in the operating world
- what data matters
- what actions are allowed
- where human approval is required
- how success and failure will be evaluated

## When to Use

- Turn a business problem like triage, allocation, escalation, review, routing, scheduling, compliance, or operations planning into a local AI decision workflow
- Inspect a codebase, ticket queue, data schema, CSV export, policy set, runbook, PRD, or operating document and decide what ontology and action model would make it agent-ready
- Design a Palantir-like operating model locally without pretending to recreate Palantir's internal systems or private prompts
- Produce a reusable `Decision System Spec` for later implementation, evaluation, or GitHub publication
- Decide what data is missing, what human approvals are needed, and what the MVP should automate first

## Inputs

Accept one or both of these:
- `goal`: the business judgment or operating problem to solve
- `context`: local files, code, schemas, tickets, docs, or datasets that describe the world

If the user only gives a goal, infer the missing world model and explicitly list unknowns. If the user only gives data, infer the likely decision surfaces and suggest the most promising first use cases.

## Workflow

### Step 1: Define the decision surface

Reduce the request to a single operational decision.

Examples:
- "Which customer issues should escalate now?"
- "Which incidents require human review before deploy?"
- "Which claims can be auto-approved versus held?"
- "Which inventory movements should happen today?"

Use `references/methodology.md` for the canonical framing and selection rules.

### Step 2: Load only the minimum useful context

Inspect only the files, schemas, docs, or code needed to model the decision.

Prefer operating artifacts over summaries:
- queue exports
- runbooks
- policy docs
- schema definitions
- service code
- incident logs
- workflow screenshots or tables

Do not load everything by default. Emulate Palantir's controlled-context style by reading only the context that sharpens the decision.

### Step 3: Build the local ontology

Define the smallest useful operating model:
- `objects`: the core entities that matter
- `properties`: the fields that influence decisions
- `relations`: how the objects affect one another
- `states`: what can change over time
- `signals`: what evidence the system can observe

Use `references/ontology-patterns.md` to choose modeling patterns and avoid over-modeling.

### Step 4: Define actions and review boundaries

Translate the decision into executable or recommendable actions.

For each action, classify it as:
- `auto`: safe to execute automatically
- `recommend`: safe to recommend but not execute
- `review`: requires explicit human approval
- `forbidden`: never execute automatically

Use `references/action-guardrails.md` to design action boundaries, logs, and escalation rules.

### Step 5: Design the agent contract

Specify the local agent behavior without centering the entire design on prompting.

Define:
- mission
- visible objects and signals
- allowed tools
- output contract
- escalation rules
- failure conditions

Treat prompt text as one implementation detail inside this larger contract.

### Step 6: Produce the Decision System Spec

Use `assets/decision-system-spec-template.md` as the canonical output shape. The spec must include:
- Decision
- Objects
- Signals
- Actions
- Permissions
- Human review points
- Workflow
- Failure cases
- Evaluation plan
- Missing data
- MVP build plan

If useful, scaffold the file with the helper script:

```powershell
& 'C:\Users\sheng\.cache\codex-runtimes\codex-primary-runtime\dependencies\python\python.exe' `
  'C:\Users\sheng\.codex\skills\palantir-ontology\scripts\bootstrap_decision_spec.py' `
  --goal "Triage incidents for release readiness" `
  --context-file "docs\runbook.md" `
  --context-file "data\incident_export.csv" `
  --output "reports\decision-system-spec.md"
```

### Step 7: Stress-test the design

Before calling the design good, challenge it:
- What data is missing?
- What action is too risky to automate?
- What object definition is too broad?
- What review point will create bottlenecks?
- What failure mode would make the system unsafe or useless?

Use `references/industry-packs.md` to compare against industry-specific patterns when relevant.

## Output Format

Return a `Decision System Spec` in Markdown. The final output should be concise enough to implement and detailed enough to govern.

### Required sections

```markdown
# Decision System Spec

## 1. Decision
## 2. Objects
## 3. Signals
## 4. Actions
## 5. Permissions and Review
## 6. Workflow
## 7. Failure Cases
## 8. Evaluation Plan
## 9. Missing Data
## 10. MVP Build Plan
```

## Prerequisites

- No external API keys required for the skill itself
- Access to local files, repos, tickets, docs, or datasets improves quality
- Use the bundled Python runtime when running the helper script on Windows

## Resources

- `references/methodology.md` -- The core Palantir-inspired design method and operating principles
- `references/ontology-patterns.md` -- Patterns for objects, states, links, signals, and world modeling
- `references/action-guardrails.md` -- Action classes, approval boundaries, logging, and safety design
- `references/industry-packs.md` -- Industry-specific examples for manufacturing, healthcare, logistics, finance, and internal ops
- `assets/decision-system-spec-template.md` -- Canonical template for final output
- `scripts/bootstrap_decision_spec.py` -- Helper script to scaffold a Decision System Spec file from a goal and local context list

## Key Principles

1. Model the real decision before modeling the prompt.
2. Keep the ontology minimal but operational.
3. Make actions explicit and permissions visible.
4. Default to human review where risk is unclear.
5. Design for implementation, not just analysis.
