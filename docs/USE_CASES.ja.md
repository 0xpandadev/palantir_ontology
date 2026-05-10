# ユースケース集

## 1. リリース可否のためのインシデント・トリアージ

### 入力
- on-call runbook
- incident export CSV
- サービスオーナー情報
- デプロイポリシー

### この skill が設計すべきもの
- `Incident`, `Service`, `Deployment`, `Reviewer` などの objects
- severity, blast radius, 未解決依存関係, rollback readiness などの signals
- `block_release`, `escalate`, `assign`, `request_review` のような actions
- 影響の大きいシステムに対する review boundary

### なぜ有用か
単なる運用チャットではなく、散らばったインシデント情報を、ガバナンス付きのリリース判断システムへ変換できるからです。

## 2. 申請・請求審査の承認ルーティング

### 入力
- claim records
- policy rules
- reviewer thresholds
- fraud heuristics

### この skill が設計すべきもの
- `Claim`, `PolicyRule`, `Reviewer`, `Exception` の objects
- `approve`, `hold`, `request_documentation`, `escalate_to_analyst` などの actions
- 金額、矛盾、証拠不足、risk score に応じた review rule

### なぜ有用か
低リスク自動化と高リスク判断を切り分け、承認境界を明示できるからです。

## 3. 顧客エスカレーションのルーティング

### 入力
- support tickets
- customer tier data
- SLA rules
- incident history

### この skill が設計すべきもの
- `Ticket`, `Customer`, `SLA`, `EscalationOwner` の objects
- age, severity, contract tier, renewal risk, reopen count などの signals
- `assign`, `escalate`, `notify_account_team`, `hold_for_review` などの actions

### なぜ有用か
サポートログの要約ではなく、「今どの案件を誰が見るべきか」を決める decision engine になるからです。

## 4. 在庫配分

### 入力
- order backlog
- warehouse inventory
- customer priority rules
- shipping constraints

### この skill が設計すべきもの
- `Order`, `InventoryPosition`, `Warehouse`, `Carrier` の objects
- `allocate`, `reroute`, `hold`, `expedite` などの actions
- 大口顧客、在庫逼迫、ポリシー例外に対する review

### なぜ有用か
運用上のトレードオフを、明示的で監査可能な配分ロジックへ変換できるからです。
