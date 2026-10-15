# Development Standards and Guidelines

このリポジトリは、すべての開発プロジェクトで共通して使用する **開発標準の正本（Single Source of Truth）** です。

## 目的

AI（ChatGPT / Codex / その他の実装Agent）を使った開発で、途中のリファクタ・基盤変更・安全対策・技術的都合によって、承認済みの製品仕様やユーザー体験が意図せず変わることを防ぎます。

## 開発開始時の必須確認

新しいプロジェクト、または新しいGPT / Agentセッションで開発を開始・再開するときは、実装前に次を確認します。

1. この `README.md`
2. `DEVELOPMENT_STANDARD.md`
3. 対象プロジェクトの `PRODUCT_CONTRACT.md`
4. 対象プロジェクトの `ACCEPTANCE.md`
5. 対象プロジェクトの `DECISIONS.md`

対象プロジェクトに 3〜5 が存在しない場合は、`templates/` を基に整備してから本格実装へ進みます。

## 正本の優先順位

1. `PRODUCT_CONTRACT.md` — 承認済み製品仕様・外部動作
2. `DECISIONS.md` — ユーザー承認済み仕様変更
3. `ACCEPTANCE.md` — 実使用で成立すべき完成条件
4. 実装計画・設計資料
5. 個別実装タスク

共通ルールは `DEVELOPMENT_STANDARD.md` を適用します。プロジェクト固有の製品仕様は各プロジェクトの `PRODUCT_CONTRACT.md` を正本とします。

## Golden Rule

> **内部構造は変更してよい。承認済みのユーザー体験・製品動作は、ユーザー承認なしに変更してはならない。**
>
> リファクタ、安全性向上、基盤変更、依存ライブラリ変更、技術的都合は「仕様変更を提案する理由」にはなりますが、「仕様変更の承認」にはなりません。

## Git操作の自律運用（v1.2）

承認済みの開発範囲では、commit / push / PR作成に加え、**必要なAcceptanceが成立した開発branch・安定版branchへのmergeもGPT判断で実行可能**です。未承認仕様差分や未確認Acceptanceがある場合はmergeしません。**release / production反映は都度ユーザー承認**が必要です。force push、force-with-lease、rebase、history rewriteは禁止です。詳細は `DEVELOPMENT_STANDARD.md` 第11項を参照してください。

## 開発サイクルとAcceptance（v1.2）

承認済み範囲では、GPTが開発サイクルを不必要な確認待ちや作業分割なしに連続実行できます。Acceptanceは変更内容に応じて選び、必要な実機確認は省略せず、不要な実機確認を一律要求しません。ユーザー承認が必要な仕様変更、release、本番反映等では確認します。詳細は `DEVELOPMENT_STANDARD.md` 第6・12項を参照してください。

## テンプレート

- `templates/PRODUCT_CONTRACT.md`
- `templates/ACCEPTANCE.md`
- `templates/DECISIONS.md`

Version: 1.2  
Established: 2026-09-21
