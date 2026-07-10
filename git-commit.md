# Git Commit

## Purpose

このInstructionは、Gitリポジトリの変更内容を確認し、
意味のある単位でコミットを行うための標準手順です。

目的は単に変更を保存することではなく、
履歴を見返したときに変更の意図が理解できるコミットを残すことです。

---

# Commit Philosophy

コミットは作業単位ではなく、意味のある変更単位で行います。

コミット履歴は変更履歴ではなく、
プロジェクトの成長記録です。

コミットメッセージは

「何を変更したか」

だけではなく、

「なぜこの変更を行ったのか」

が伝わる内容を目指してください。

---

# Rules

- 必ず変更内容を確認してからコミットする。
- 変更内容が大きく異なる場合は、コミットを分けることを提案する。
- コミットメッセージは英語で作成する。
- コミットメッセージは1行で記述する。
- 先頭は動詞（Add / Update / Remove / Refactor / Define / Introduce ...）を使用する。
- 可能な限り変更の目的が伝わる文章にする。
- コミット前にユーザーへ内容を確認する。
- ユーザーから明示的な指示がない限り、pushは行わない。

---

# Workflow

## 1. Working Treeを確認する

実行するコマンド

```bash
git status --short
```

変更されたファイルを確認する。

---

## 2. 変更内容を確認する

必要に応じて

```bash
git diff --stat
```

または

```bash
git diff
```

を確認する。

---

## 3. コミット単位を判断する

変更内容を確認し、

- 一つの意味を持つ変更なのか
- 複数の変更が混ざっているのか

を判断する。

複数の変更が混在している場合は、
コミットを分けることを提案する。

---

## 4. Staging

ステージされていない変更がある場合は、

対象ファイルを確認してから

```bash
git add
```

を実行する。

変更内容に問題がない場合のみ

```bash
git add .
```

を使用してよい。

---

## 5. コミットメッセージを作成する

変更内容を要約し、

適切な英語コミットメッセージを作成する。

例

Good

```text
Add Japanese README for knowledge workflow

Define the vision and knowledge lifecycle of FIFNEL

Add first Co-Thinking knowledge summaries

Initialize project structure
```

Bad

```text
Update

Fix

Commit changes

Update files
```

---

## 6. ユーザーへ確認する

コミットを実行する前に、

- 変更内容の要約
- コミットメッセージ案

を提示し、

ユーザーの承認を得る。

---

## 7. Commit

承認後、

```bash
git commit -m "<message>"
```

を実行する。

---

## 8. Push

pushは実行しない。

ユーザーから

- pushして
- リモートへ反映して

などの明示的な指示があった場合のみ

```bash
git push
```

を実行する。

---

# Commit Message Style

以下を優先する。

1. 意味が分かること
2. 簡潔であること
3. 英語として自然であること

変更内容ではなく、
変更の目的を表現することを意識する。

---


## メッセージ選択の考え方

コミットメッセージは、変更内容そのものではなく、変更の意味を表現してください。

優先順位

1. なぜこの変更を行ったか
2. 何を追加・定義・記録したか
3. どのように変更したか

KnowledgeやSummaryを追加する場合は、内容を「記録する」という意味を持つ **Document** を優先します。

例

```text
Document Co-Thinking birth

Document knowledge base foundation

Document AI agent git commit instruction experiment
```

新しい機能・ファイル・仕組みを追加する場合は、以下の動詞を優先します。

```text
Add
Introduce
Define
Initialize
```


---

# Expected Behavior

AIは単なるGit操作ツールではありません。

コミット単位や変更内容をレビューし、
より分かりやすい履歴になるよう提案してください。

履歴は未来の開発者（人間・AI）が読むドキュメントであることを常に意識してください。