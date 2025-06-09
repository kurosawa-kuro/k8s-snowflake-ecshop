# k8s-snowflake-ecshop


![418342364-83454fa7-a927-4a82-bd5c-db567ce85061](https://github.com/user-attachments/assets/f82ba512-9b35-4a05-a9fa-eca59e1d942b)


![418342369-97197d77-4e02-45a2-92b3-be3f8191728f](https://github.com/user-attachments/assets/e65de102-2ff9-46e6-b9e3-bc4f109fe852)

![418342371-4d81177e-c398-45fc-aeed-e02f297533ac](https://github.com/user-attachments/assets/84e14e90-7c82-40da-8ee9-d7d740e97235)

![418342377-2fdb5b32-a236-4398-9059-c878b608287a](https://github.com/user-attachments/assets/37fb972c-b0e8-4747-bb56-ea9c76660139)





![418342378-ba3b09de-a68a-46f1-8153-fb2feefb6aca](https://github.com/user-attachments/assets/e12b988c-5434-43c7-adf2-655a295c6afb)

![418342379-2e70797a-f1d6-4223-ad98-e64bdd4fba22](https://github.com/user-attachments/assets/f0a63d10-1150-48be-b754-7b2f80431495)

![418342381-6e9ef42b-9abd-4000-9ef7-20e6522102c4](https://github.com/user-attachments/assets/237372b6-9ff2-470f-9fd1-2e8bd0fabe87)

![418342382-ba7cb2ae-2d2e-478c-ae85-378b57500631](https://github.com/user-attachments/assets/93dbdfca-e8e7-4348-8236-0cf5a0cb0e21)

![418342384-4d15e1a6-d0b1-4bff-9645-8b146f78735c](https://github.com/user-attachments/assets/c0c16fe4-d1a0-4685-9a77-af2217d14225)

![418342360-faf84f79-7dfc-4e96-9d1a-e34a868b7cad](https://github.com/user-attachments/assets/07541549-75ce-4077-bae0-716f3ad7151c)

![418494398-7d6191fe-389b-4715-b94b-ab2d55acfa73](https://github.com/user-attachments/assets/a7df4f7f-e76f-4ce8-b6fc-20b96420daf0)



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
