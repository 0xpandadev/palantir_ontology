# 使用案例

## 1. 面向发布决策的事故分诊

### 输入
- on-call runbook
- incident export CSV
- 服务归属图
- 部署策略

### 这个 skill 应该产出
- `Incident`, `Service`, `Deployment`, `Reviewer` 等 objects
- severity、blast radius、未解决依赖、rollback readiness 等 signals
- `block_release`, `escalate`, `assign`, `request_review` 等 actions
- 对高影响系统的 review boundary

### 为什么有用
它把零散的事故信息，变成一个有治理能力的发布判断系统，而不是另一个 ops 聊天机器人。

## 2. 理赔审核与审批分流

### 输入
- claim records
- policy rules
- reviewer thresholds
- fraud heuristics

### 这个 skill 应该产出
- `Claim`, `PolicyRule`, `Reviewer`, `Exception` objects
- `approve`, `hold`, `request_documentation`, `escalate_to_analyst` 等 actions
- 基于金额、矛盾、缺失证据或风险分的 review rules

### 为什么有用
它能把低风险自动化与高风险人工判断清晰分开，并明确审批边界。

## 3. 客户升级路由

### 输入
- support tickets
- customer tier data
- SLA rules
- incident history

### 这个 skill 应该产出
- `Ticket`, `Customer`, `SLA`, `EscalationOwner` objects
- 工单时长、严重性、合同等级、续约风险、重复 reopen 次数等 signals
- `assign`, `escalate`, `notify_account_team`, `hold_for_review` 等 actions

### 为什么有用
它不是简单总结支持日志，而是构建一个“现在谁最该被处理”的 decision engine。

## 4. 库存分配

### 输入
- order backlog
- warehouse inventory
- customer priority rules
- shipping constraints

### 这个 skill 应该产出
- `Order`, `InventoryPosition`, `Warehouse`, `Carrier` objects
- `allocate`, `reroute`, `hold`, `expedite` 等 actions
- 面向大客户、库存紧张、策略例外的 review 机制

### 为什么有用
它把运营中的取舍，转化为明确、可审计的库存分配逻辑。
