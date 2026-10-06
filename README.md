# So Ryo

[English](README.en.md)

マルチテナント B2B SaaS のフルスタックエンジニアです。フロントエンド（React / TypeScript）から始め、いまは
バックエンド（Scala / Play / Akka、MongoDB）、テスト自動化、CI まで担当しています。

実装の大部分を AI エージェント（Claude Code）に任せ、設計・裁定・検証を自分で行う開発をしています。
ここにあるリポジトリは、その実務で使ってきた方法を、公開できる形に作り直したものです。

## 取り組んできたこと

| 分野 | 内容 | 実務での実測値（コードは非公開） | 事例 ・ 再現 |
|---|---|---|---|
| 基盤統合 | グループ共通のアカウント・テナント基盤との統合。認可コード + PKCE、既存 API での Bearer の受理、ロールの導出、署名付き Webhook、テナント同期。すべて既定オフで段階的に有効化 | マージ済み PR 18 件（2026-08〜09） | [事例 01](https://github.com/MuneAkira6/engineering-case-studies/blob/main/01-platform-integration.md) ・ [idp-tenant-integration-demo](https://github.com/MuneAkira6/idp-tenant-integration-demo) |
| テスト自動化 | 機能仕様書を分母にしたカバレッジ台帳と、失敗を四つ（新しい赤・申告済みの赤・判定不能・緑に戻った）に分ける品質ゲート | UI カバレッジ 22.1% → 83.9%（既存の QA 資産を含む） | [事例 02](https://github.com/MuneAkira6/engineering-case-studies/blob/main/02-test-automation-and-quality-gates.md) ・ [regression-gate-demo](https://github.com/MuneAkira6/regression-gate-demo) |
| CI・開発体験 | self-hosted runner での PR コンパイルチェック、非決定的なビルド失敗の切り分け、devcontainer の改善、OSS ライセンス一覧の自動生成 | PR コンパイルチェック約 3 分、Actions の課金枠の使用なし | [事例 03](https://github.com/MuneAkira6/engineering-case-studies/blob/main/03-ci-and-developer-experience.md) ・ [ci-devex-toolkit](https://github.com/MuneAkira6/ci-devex-toolkit) |
| AI エージェント | 長命バス方式（無人で goal を回す）と、仕様駆動開発（spec-kit） | バス方式の運用 18 回・最長の無人区間 16 時間 37 分。仕様フォルダ 46 件 | [事例 04](https://github.com/MuneAkira6/engineering-case-studies/blob/main/04-unattended-goal-bus.md) ・ [事例 05](https://github.com/MuneAkira6/engineering-case-studies/blob/main/05-spec-driven-development.md) |
| 日々の AI 活用 | 評価つきのスキル、規則が決めて LLM は短い文だけを書く朝会ダイジェスト、チームへの展開 | 評価付きのスキル 7 個。朝会ダイジェストの消費は 1 日約 7k トークン | [事例 06](https://github.com/MuneAkira6/engineering-case-studies/blob/main/06-ai-in-daily-engineering.md) ・ [agent-skills-with-evals](https://github.com/MuneAkira6/agent-skills-with-evals) |
| その他 | レポートの N+1 の解消、スレッド枯渇によるデッドロック、ビルドツールの移行 | レポートの DB 要求を 1 回の出力あたり 2,055 回 → 16 回（1,000 人規模の合成データ、CSV はバイト一致） | [事例 07](https://github.com/MuneAkira6/engineering-case-studies/blob/main/07-other-work.md) ・ [labs](https://github.com/MuneAkira6/labs) |

## 二つの方法

- **長命バス + 無人 goal**（[goal-bus-kit](https://github.com/MuneAkira6/goal-bus-kit)）：ワーカーの会話が goal を
  実行し、goal 包を書いた長命の「バス」の会話が、goal の境界ごとに審査して次の指示を書きます。二つの Stop hook が、
  会話ではなくファイルを読んで進行を制御します。
- **仕様駆動開発**（[spec-driven-dev-playbook](https://github.com/MuneAkira6/spec-driven-dev-playbook)）：specs/ の
  フォルダを要件の正本にし、clarify では人が一件ずつ裁定し、判定は証拠つきで PASS / FAIL / BLOCKED / DEFERRED に
  分けます。

このポートフォリオのうち 6 つのリポジトリは、仕様と契約を先に書き、それ自体をバス方式で無人実装しました
（6 回の実行で判定 387 行、問題を直すための人の介入 1 回。デモの実測値です）。

## リポジトリ

| リポジトリ | 内容 |
|---|---|
| [goal-bus-kit](https://github.com/MuneAkira6/goal-bus-kit) | 長命バス方式を任意のリポジトリに導入するツールキット。hook、自己テスト、テンプレート、教訓 30 件、実走の記録 |
| [spec-driven-dev-playbook](https://github.com/MuneAkira6/spec-driven-dev-playbook) | 仕様駆動開発の手引きと、記入して使うテンプレート 10 本 |
| [idp-tenant-integration-demo](https://github.com/MuneAkira6/idp-tenant-integration-demo) | 既存の SaaS に IdP ログインを後付けする、動くデモ。仕様一式と無人実装の記録つき |
| [regression-gate-demo](https://github.com/MuneAkira6/regression-gate-demo) | Playwright の回帰スイート、手動テストシートを分母にしたカバレッジ、四分類の品質ゲート |
| [ci-devex-toolkit](https://github.com/MuneAkira6/ci-devex-toolkit) | OSS ライセンス一覧、2 リポジトリ・1 作業ツリー、PR コンパイルチェック、devcontainer の I/O 計測 |
| [agent-skills-with-evals](https://github.com/MuneAkira6/agent-skills-with-evals) | 評価つきのスキル 3 本（起動率のプローブ、検証つきの取得、朝会ダイジェスト）と、測った数字を都合の悪いものも含めて載せた記録 |
| [labs](https://github.com/MuneAkira6/labs) | 小さな 3 つの実験：レポートの N+1（金型とのバイト一致）、ブロッキング待機によるスレッド枯渇、webpack から Rsbuild への移行 |
| [engineering-case-studies](https://github.com/MuneAkira6/engineering-case-studies) | 上の取り組みの事例集（7 本） |

## 実務の規模

マージ済み PR 161 件、レビューした他のメンバーの PR 92 件（2025-10〜2026-09、実務での実測値）。

## 数字について

実務の数字には「実務での実測値（コードは非公開）」と書いています。デモの数字は、各リポジトリで実際に走らせた
結果だけです。二つは同じ表に混ぜていません。

## 技術

TypeScript ・ React ・ Node.js ・ Scala ・ Play Framework ・ Akka ・ MongoDB ・ Playwright ・ Vitest ・
GitHub Actions ・ Docker ・ Keycloak ・ Claude Code

## 言語

日本語（JLPT N1）・中国語（母語）・英語（読み書き・会話）

---

設計・レビュー・検証：So Ryo ／ 実装：AI エージェント（Claude Code）との協働
