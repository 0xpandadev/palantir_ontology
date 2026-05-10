# Example Use Cases

## 1. Incident Triage for Release Readiness

### Input
- on-call runbook
- incident export CSV
- service ownership map
- deployment policy

### What the skill should produce
- `Incident`, `Service`, `Deployment`, `Reviewer` objects
- signals such as severity, blast radius, unresolved dependencies, rollback readiness
- actions like `block_release`, `escalate`, `assign`, `request_review`
- review boundaries for high-impact systems

### Why it is useful
This turns scattered incident data into a governed release decision system rather than another ops chatbot.

## 2. Claims Review and Approval Routing

### Input
- claim records
- policy rules
- reviewer thresholds
- fraud heuristics

### What the skill should produce
- `Claim`, `PolicyRule`, `Reviewer`, `Exception` objects
- actions like `approve`, `hold`, `request_documentation`, `escalate_to_analyst`
- review rules based on amount, inconsistency, missing evidence, or risk score

### Why it is useful
It separates low-risk automation from high-risk judgment and makes approval boundaries explicit.

## 3. Customer Escalation Routing

### Input
- support tickets
- customer tier data
- SLA rules
- incident history

### What the skill should produce
- `Ticket`, `Customer`, `SLA`, `EscalationOwner` objects
- signals like age, severity, contract tier, renewal risk, repeated reopen count
- actions like `assign`, `escalate`, `notify_account_team`, `hold_for_review`

### Why it is useful
This creates a decision engine for who needs attention now, not just a summarizer for support logs.

## 4. Inventory Allocation

### Input
- order backlog
- warehouse inventory
- customer priority rules
- shipping constraints

### What the skill should produce
- `Order`, `InventoryPosition`, `Warehouse`, `Carrier` objects
- actions like `allocate`, `reroute`, `hold`, `expedite`
- review for large customers, constrained stock, or policy exceptions

### Why it is useful
It turns operational tradeoffs into explicit, auditable allocation logic.
