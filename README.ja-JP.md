# Open Design

Open Design はローカル優先のデザインワークベンチです。インストール済みの coding-agent CLI または設定済み BYOK プロバイダーを、再利用可能な Skill と Design System に接続します。生成物はプレビューに表示され、保存できます。

> **状態:** ソース構成と package scripts を確認しました。この README 更新ではインストール、テスト、外部プロバイダー、デプロイ、安全性、生成品質を検証していません。

## 構成

- apps/daemon/: ローカルサービスと CLI
- apps/web/: デザインワークスペースとプレビュー
- apps/desktop/: デスクトップシェル
- skills/ と design-systems/: 再利用可能な手順とデザイン資料

## 要件と起動

ルート package は Node.js 24.x と pnpm 10.33.2 を指定しています。Quickstart では macOS、Linux、WSL2 を主な環境としています。

    corepack enable
    pnpm install
    pnpm tools-dev run web

このコマンドはリポジトリの Quickstart に基づき、この更新では実行していません。デスクトップ起動や追加手順は [英語 Quickstart](QUICKSTART.md) を参照してください。

## データと制限

入力やプロジェクト情報が選択した Agent CLI または BYOK プロバイダーへ送られる場合があります。ローカル CLI でも推論が端末内だけで行われるとは限りません。生成物は再利用前に確認してください。この README はセキュリティや隔離の認証ではありません。

- [ドキュメント一覧](docs/README.md)
- [アーキテクチャ](docs/architecture.md)
- [コントリビューション](CONTRIBUTING.md)
- [ライセンス](LICENSE)