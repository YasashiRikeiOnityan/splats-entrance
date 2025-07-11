# SPLATS ENTRANCE - 来客受付×入館証貸出サービス

本リポジトリは来客受付×入館証貸出サービスのソースコード及び開発ドキュメントを管理します。

## 概要

SPLATS ENTRANCEは、来客受付システムと社員証貸し出しシステムを統合した社内システムです。クラウド型物品管理システム「SPLATS」と連携し、入館証と社員証の自動管理を実現します。

## フォルダ構成

```txt
splats-entrance/
├── .cursor/              # Cursor IDE設定
│   └── .cursorrules     # Cursor rules設定
├── docs/                 # ドキュメント
│   ├── api/             # API仕様書
│   ├── design/          # 設計資料
│   └── deployment/      # デプロイ手順
├── frontend/             # フロントエンド (Next.js)
│   ├── src/
│   │   ├── components/ # コンポーネント
│   │   ├── pages/      # ページ
│   │   ├── hooks/      # カスタムフック
│   │   ├── utils/      # ユーティリティ
│   │   └── types/      # TypeScript型定義
│   ├── public/          # 静的ファイル
│   ├── package.json
│   └── next.config.js
└── backend/              # バックエンド (AWS サーバーレス)
    ├── functions/        # Lambda関数
    │   ├── visitor/     # 来客関連API
    │   ├── employee/    # 社員関連API
    │   ├── splats/      # SPLATS連携API
    │   └── shared/      # 共通ライブラリ
    ├── infrastructure/   # IaC (CloudFormation/CDK)
    ├── schemas/          # DynamoDBスキーマ
    └── tests/            # テストコード
```

## バージョン

| バージョン | 機能 | リリース日 |
| :--: | :-- | :--: |
| Ver1.0.0 | サービス開始 | |
