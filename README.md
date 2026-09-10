# references

AI / software / operations / architecture に関する **reference knowledge base**。

この repository は正本（canonical source）ではありません。設計判断や実装状態を直接支配せず、ChatGPT や他の Actor が再利用できる観測・解釈・比較・運用知見を蓄積します。

## Purpose

- 会話や実験から得た再利用可能な知見を durable に残す
- 「何を知っているか」だけでなく、由来・確度・鮮度を残す
- 将来の model routing / architecture / operations 判断に使える材料を増やす
- 正本 repository や private operational state と reference knowledge を分離する
- AI や runtime を交換しても再利用できる一般化された経験知を増やす

## Boundary

この Public repository には以下を保存しません。

- API keys / credentials / secrets
- 個人情報・機微情報
- private repository の非公開内容
- 未公開の内部運用情報
- 正本として扱う必要がある project state

Project 固有の知見を書く場合も、Public に置いて問題ない抽象度へ落とします。

## Knowledge states

各 reference は原則として次のいずれかを持ちます。

- `raw` — 観測しただけで未整理
- `candidate` — 再利用価値がありそうだが未検証
- `validated` — 複数の証拠や実運用で妥当性を確認
- `superseded` — より新しい知見に置き換え済み
- `rejected` — 誤り・不適合として残す

## Provenance

各記録には可能な範囲で以下を残します。

- observed_at
- source_type
- source
- topic
- status
- confidence
- applicability
- notes

会話由来の知識は `source_type: chat-derived` とし、事実・解釈・仮説を混同しません。

## Structure

```text
references/
├─ README.md
├─ schema/
│  └─ reference-entry.md
├─ knowledge/
│  ├─ README.md
│  ├─ architecture/
│  ├─ ai-routing/
│  ├─ economics/
│  ├─ insight/
│  ├─ operations/
│  └─ platform/
└─ intake/
   └─ README.md
```

`intake/` は未整理の観測置き場、`knowledge/` は再利用可能な形へ整理した知見です。`knowledge/README.md` はカテゴリと昇格ルールの案内です。

## Rule of thumb

> Reference is evidence for a decision, not authority for a decision.

正本・Human authority・実環境の状態を、この repository の記述だけで上書きしません。
