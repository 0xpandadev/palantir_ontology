# Framework

## The idea in one sentence

Turn messy real-world operations into a governed, ontology-driven AI decision system.

## Design thesis

The common mistake in enterprise AI is to begin with:

- a model
- a prompt
- a chatbot
- retrieval

The correct starting point is:

- the decision
- the world model behind the decision
- the actions tied to that decision
- the review and permission boundaries around those actions

## The canonical method

### 1. Define the decision

Reduce the problem to a single business judgment.

### 2. Define the world

Model the minimal ontology:

- objects
- states
- relations
- signals

### 3. Define the actions

Map every decision outcome to a concrete action.

### 4. Define governance

Classify actions:

- auto
- recommend
- review
- forbidden

### 5. Define the agent contract

Specify:

- mission
- visible context
- tools
- output contract
- escalation rules

### 6. Define evaluation

Test:

- missing data
- edge cases
- unsafe actions
- failure costs
- operator burden

## What this framework is trying to replace

It is trying to replace this weak pattern:

`Files + Retrieval + Chat UI = "enterprise AI"`

with this stronger pattern:

`Decision + Ontology + Actions + Guardrails + Evaluation = operable AI`

## What “Palantir-inspired” means here

It means adopting the useful public abstractions:

- ontology as an operational world model
- actions as first-class outputs
- permissions and review boundaries as design primitives
- closed-loop iteration around real workflows

It does **not** mean:

- proprietary Palantir code
- leaked prompts
- internal architecture replication

## Recommended first implementation target

Do not begin with a giant platform.

Begin with one decision that has:

- clear business value
- available data
- bounded risk
- human reviewers available
- visible outcomes

Examples:

- incident escalation
- claims triage
- release readiness
- support prioritization
- inventory allocation

## Practical rule

If the design cannot answer these five questions, it is not ready:

1. What exactly is the decision?
2. What object is the decision acting on?
3. What evidence is the decision based on?
4. What action follows the decision?
5. Who approves the risky cases?
