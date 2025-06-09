# k8s-snowflake-ecshop

![418494398-7d6191fe-389b-4715-b94b-ab2d55acfa73](https://github.com/user-attachments/assets/351d26c5-089f-4f84-8906-8ffad77e4225)
![418342360-faf84f79-7dfc-4e96-9d1a-e34a868b7cad](https://github.com/user-attachments/assets/83a46485-4687-488c-baf7-d8febcffd5cc)
![418342384-4d15e1a6-d0b1-4bff-9645-8b146f78735c](https://github.com/user-attachments/assets/6d379f58-3bd0-40a2-a734-736b44074c25)
![418342382-ba7cb2ae-2d2e-478c-ae85-378b57500631](https://github.com/user-attachments/assets/b32ba636-b8de-4972-ae99-863d340eac9d)
![418342381-6e9ef42b-9abd-4000-9ef7-20e6522102c4](https://github.com/user-attachments/assets/e2459388-42a1-4745-b44d-704a0e54e86e)
![418342379-2e70797a-f1d6-4223-ad98-e64bdd4fba22](https://github.com/user-attachments/assets/86a54993-ba46-47d0-9716-673fe90823c3)
![418342378-ba3b09de-a68a-46f1-8153-fb2feefb6aca](https://github.com/user-attachments/assets/87d637c6-c4ed-4c61-b000-6700e95856fc)
![418342377-2fdb5b32-a236-4398-9059-c878b608287a](https://github.com/user-attachments/assets/d3dc4b7e-d476-4266-9184-ed2955e2a85d)
![418342371-4d81177e-c398-45fc-aeed-e02f297533ac](https://github.com/user-attachments/assets/2100f60d-8da4-473c-9b5c-5909105f3f6d)
![418342369-97197d77-4e02-45a2-92b3-be3f8191728f](https://github.com/user-attachments/assets/00f7a412-c00d-4cd2-a554-52f57b016eeb)
![418342364-83454fa7-a927-4a82-bd5c-db567ce85061](https://github.com/user-attachments/assets/76f733b5-7c82-4eba-aa5c-fcc8d6742a24)







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
