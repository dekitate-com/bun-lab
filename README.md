# Monorepo

Bun workspace を使用した monorepo プロジェクトです。

## ディレクトリ構造

```
monorepo/
├── apps/          # アプリケーション
├── packages/      # 共有ライブラリ・パッケージ
├── package.json   # ルート設定
└── README.md
```

## セットアップ

```bash
# 依存関係のインストール
bun install

# 全てのパッケージをビルド
bun run build

# 全てのパッケージを開発モードで実行
bun run dev

# 全てのパッケージをテスト
bun run test
```

## Workspace の使用方法

### 特定のワークスペースでコマンドを実行

```bash
# 特定のアプリを実行
bun run --filter=app-name dev

# 特定のパッケージをビルド
bun run --filter=package-name build
```

### パッケージの追加

```bash
# 特定のワークスペースに依存関係を追加
bun add <package-name> --filter=workspace-name

# ルートに開発依存関係を追加
bun add -D <package-name>
```

### ワークスペース間の依存関係

`package.json` で他のワークスペースを参照：

```json
{
  "dependencies": {
    "@monorepo/shared-ui": "workspace:*"
  }
}
``` 