# k8s-snowflake-ecshop








# ポートフォリオ戦略（最新版）

以前共有したリポジトリ **data-driven-fargate-ecshop** を、ここ数か月で学んだ内容をフィードバックし、**超実践向きポートフォリオ**へパワーアップする予定です。作業期間は **約 2 か月** を見込んでいます。

リポジトリ: [https://github.com/kurosawa-kuro/data-driven-fargate-ecshop](https://github.com/kurosawa-kuro/data-driven-fargate-ecshop)

## 目的

採用担当者に対して、次のようなスキルを「この人なら任せられる」と確信させることがゴールです。

* **マイクロサービスアーキテクチャ** による複雑なシステム設計・運用
* **Kubernetes** を用いたコンテナオーケストレーションと自動スケーリング
* **データパイプライン** の設計・構築
* **DWH（Snowflake）** を中心としたデータ基盤整備
* **BI／DX** に対応した分析・可視化環境の提供

## アプリケーションタイプ

* **EC ショップアプリ**（UI は Amazon クローンを流用）

## パワーアップ内容（UI はそのまま活用）

1. **Kubernetes 対応**（開発環境: kind ／ 本番環境: EKS を想定）
2. **Athena → Snowflake へ移行**し、大規模データ分析に対応
3. **バックエンドを Spring Boot (Java) に刷新**

   * 高速処理が求められる一部サービスは **Go** で実装

## アーキテクチャ

* **マイクロサービスアーキテクチャ**

  * 各サービスは独立デプロイ可能（CI/CD は Argo CD + GitOps）
  * API ゲートウェイ／サービスメッシュ（Istio 予定）で通信を統制
* **Event‑Driven Design**（Kafka）でサービス間連携を疎結合化
* **Observability**: Prometheus + Grafana + Loki で監視／ログ集約
* **Data Pipeline**: CDC → Snowflake → dbt → BI（Superset, Metabase など）
* **Security & Compliance**: IAM、Secret Manager、Vault、OPA Gatekeeper

## 追加予定機能

* **バックオフィス / 商品状態管理画面**

  * 在庫／注文／配送状況をリアルタイムに可視化
  * トレーサビリティ確保のため、ブロックチェーン（Hyperledger Fabric）連携を検討

---

※ 上記はロードマップ案です。スコープや優先順位は進捗に応じて調整します。
