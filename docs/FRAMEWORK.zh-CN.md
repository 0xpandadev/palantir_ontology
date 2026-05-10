# 框架

## 一句话版本

把现实世界中混乱的业务流程，转换成一个带治理能力的 ontology-driven AI 决策系统。

## 设计主张

企业 AI 最常见的错误，是从这些东西开始：

- 模型
- prompt
- chatbot
- retrieval

真正应该先定义的是：

- decision
- decision 背后的 world model
- decision 产生的 actions
- 围绕这些 actions 的 permissions 和 review 边界

## 标准方法

### 1. 定义 decision

把问题压缩成一个明确的业务判断。

### 2. 定义 world

切出最小可用 ontology：

- objects
- states
- relations
- signals

### 3. 定义 actions

为每种判断结果，定义明确动作。

### 4. 定义 governance

把动作分成：

- auto
- recommend
- review
- forbidden

### 5. 定义 agent contract

明确：

- mission
- visible context
- tools
- output contract
- escalation rules

### 6. 定义 evaluation

测试：

- 缺失数据
- 边界情况
- 危险动作
- 失败成本
- 人工负担

## 这个框架想替代什么

它想替代这种弱模式：

`Files + Retrieval + Chat UI = "enterprise AI"`

改成这种强模式：

`Decision + Ontology + Actions + Guardrails + Evaluation = operable AI`

## 这里说的 “Palantir-inspired” 是什么意思

意思是借鉴这些公开可见的抽象：

- ontology 作为 operational world model
- action 作为一等输出
- permissions 和 review boundaries 作为核心设计原语
- 围绕真实业务工作流的 closed-loop 迭代

它**不**意味着：

- Palantir proprietary code
- 泄露 prompt
- 复制内部系统架构

## 最适合先做的目标

不要一开始就做巨大的平台。

先从一个满足以下条件的 decision 开始：

- 有明确业务价值
- 已有数据可用
- 风险边界可控
- 有人工 reviewer
- 有可观察结果

例子：

- incident escalation
- claims triage
- release readiness
- support prioritization
- inventory allocation

## 最实用的5个问题

如果一个设计无法回答这5个问题，它还不够成熟：

1. 系统到底在做什么判断？
2. 这个判断作用于哪个 object？
3. 这个判断依赖哪些 evidence？
4. 判断之后会触发什么 action？
5. 高风险情况由谁审批？
