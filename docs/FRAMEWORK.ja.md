# フレームワーク

## 一文で言うと

現実の複雑な業務を、ガバナンス付きの ontology-driven AI decision system に変換するための方法論です。

## 設計思想

企業AIでよくある間違いは、最初に

- モデル
- prompt
- チャットボット
- retrieval

から入ってしまうことです。

本来、最初に定義すべきなのは

- decision
- その decision を支える world model
- その decision に紐づく action
- その action を囲む review / permission

です。

## 正式な流れ

### 1. Decision を定義する

問題を、1つの業務判断に圧縮する。

### 2. World を定義する

最小の ontology を切る。

- objects
- states
- relations
- signals

### 3. Actions を定義する

判断結果ごとに、どの action が続くかを明示する。

### 4. Governance を定義する

action を次に分類する。

- auto
- recommend
- review
- forbidden

### 5. Agent contract を定義する

次を決める。

- mission
- visible context
- tools
- output contract
- escalation rules

### 6. Evaluation を定義する

次を test する。

- 欠損データ
- 境界ケース
- 危険な action
- 失敗コスト
- 運用者負荷

## このフレームが置き換えたいもの

この弱い形：

`Files + Retrieval + Chat UI = "enterprise AI"`

を、

この強い形：

`Decision + Ontology + Actions + Guardrails + Evaluation = operable AI`

へ置き換えることです。

## ここでいう “Palantir-inspired” とは

次の公開概念を取り入れることです。

- ontology を operational world model として扱う
- action を first-class output にする
- permissions と review boundary を設計単位にする
- 現実業務を中心に closed-loop で回す

逆に、意味しないものは次です。

- Palantir の proprietary code
- 漏洩 prompt
- 内部構造の複製

## 最初に実装すべき対象

最初から巨大プラットフォームを作らないことです。

まずは、次を満たす 1 decision から始める。

- 明確な事業価値がある
- 必要データがある
- リスクが限定されている
- 人間レビュー担当がいる
- 結果が見える

例:

- incident escalation
- claims triage
- release readiness
- support prioritization
- inventory allocation

## 実務上の5つの問い

次の5問に答えられないなら、設計はまだ甘いです。

1. 何を判断しているのか
2. その判断は何の object に作用するのか
3. その判断は何の evidence に基づくのか
4. その判断の後にどの action が起きるのか
5. 危険ケースは誰が承認するのか
