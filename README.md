# dot-devcontainer-terraform-1.12

Terraform 1.12開発環境用のDockerコンテナプロジェクトです。

## 概要

このプロジェクトは、Terraform 1.12を使用したインフラストラクチャ・アズ・コード（IaC）の開発環境を提供するDockerコンテナを構築します。Fish shellを搭載したDebianベースのコンテナに、Terraform、tflint、trivyがインストールされています。

## 含まれるツール

- **Terraform 1.12**: インフラストラクチャ・アズ・コード（IaC）ツール
- **tflint**: Terraformコードのリンター
- **trivy**: セキュリティスキャナー
- **Fish shell**: ユーザーフレンドリーなコマンドラインシェル

## 使用方法

### コンテナイメージのビルド

ARM64アーキテクチャ用:
```bash
make test.build.arm64
```

AMD64アーキテクチャ用:
```bash
make test.build.amd64
```

### テスト

両方のアーキテクチャでビルドとテストを実行:
```bash
make test
```

ARM64のみ:
```bash
make test.arm64
```

AMD64のみ:
```bash
make test.amd64
```

### イメージの削除

ARM64イメージの削除:
```bash
make test.rmi.arm64
```

AMD64イメージの削除:
```bash
make test.rmi.amd64
```

## コンテナ情報

- **ベースイメージ**: `ghcr.io/bearfield/debian-fish:bookworm`
- **レジストリ**: `ghcr.io/bearfield/terraform:test.1.12`
- **対応アーキテクチャ**: ARM64, AMD64

## ライセンス

このプロジェクトのライセンスについては、[LICENSE](LICENSE)ファイルを参照してください。
