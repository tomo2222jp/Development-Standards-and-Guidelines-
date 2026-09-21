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

## テンプレート

- `templates/PRODUCT_CONTRACT.md`
- `templates/ACCEPTANCE.md`
- `templates/DECISIONS.md`

Version: 1.0  
Established: 2026-09-21
