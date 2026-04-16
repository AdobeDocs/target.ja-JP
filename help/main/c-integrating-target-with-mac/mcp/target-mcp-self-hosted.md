---
solution: Target
product: target
title: Adobe Target MCP サーバーのセルフホスティング
description: Python、Docker、またはローカル開発環境を使用して、Adobe Target MCP サーバーの独自のインスタンスを実行する方法について説明します。
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta" type="Informative"
role: Developer
level: Experienced
hide: true
source-git-commit: 782256b734068075795d5e9c1f3f552ca48918e6
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 2%

---

# [!DNL Adobe Target] MCP サーバーをセルフホストします {#target-mcp-self-hosted}

>[!BEGINSHADEBOX]

目次：

* [MCP クライアントの操作](target-mcp.md)
* [MCP サーバーツールリファレンス](target-mcp-tools-reference.md)
* **[MCP サーバーをセルフホスト](target-mcp-self-hosted.md)**

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>セルフホスト型のデプロイメントは、[!DNL Adobe Target] MCP サーバーランタイムを完全に制御する必要がある開発者および上級ユーザーを対象としています。 ほとんどのユーザーには、ホスト エンドポイント （`https://targetmcp.adobe.io/mcp`）をお勧めします。 [MCP クライアントの操作](target-mcp.md)を参照してください。

このページでは、[!DNL Adobe Target] MCP サーバーの独自のインスタンスを複製、設定、実行する方法について説明します。 セルフホスティングは、ローカル開発環境やカスタムネットワーク設定が必要な場合、またはサーバーコードベースに組み込む場合に便利です。

## 前提条件 {#self-hosted-prereqs}

始める前に、次の項目を確認してください。

* **Python 3.13以降**
* **[uv](https://github.com/astral-sh/uv){target="_blank"}** – 高速Python パッケージとプロジェクトマネージャー

  ```bash
  curl -LsSf https://astral.sh/uv/install.sh | sh
  ```

* Adobe Experience Cloudへのアクセス権を持つアクティブな[!DNL Adobe Target] ライセンス
* **Artifactory credentials** （Adobe社内ユーザーのみ） – 社内依存関係のインストールに必要

## インストール {#self-hosted-install}

**1.リポジトリのクローンを作成します：**

```bash
git clone https://github.com/Adobe-TnT/target-mcp.git
cd target-mcp
```

**2.仮想環境を作成してアクティブ化します：**

```bash
uv venv --python 3.13
source .venv/bin/activate
```

**3.環境変数の設定：**

```bash
cp env.example .env
```

`.env`を開き、プレースホルダーの値を資格情報と組織の設定に置き換えます。

**4.依存関係のインストール：**

```bash
make uv-install
```

**5.サーバーを開始：**

ユースケースに合ったモードを選択します。

| モード | Command | 次の場合に使用 |
|---|---|---|
| StreamableHTTP （API サーバー） | `make run-api-server` | HTTP経由でのMCP クライアントの接続 |
| STDIO （ローカル MCP クライアント） | `make run-mcp-stdio` | ダイレクトプロセスコミュニケーションの使用 |

## MCP クライアントをローカルサーバーに接続する {#self-hosted-connect}

### カーソル

以下をカーソル MCP設定に追加します。 プレースホルダーの値を、実際のIMS トークンと組織IDに置き換えます。

```json
{
  "mcpServers": {
    "target-local": {
      "url": "http://localhost:8080/mcp",
      "headers": {
        "Authorization": "Bearer {IMS_USER_TOKEN}",
        "x-gw-ims-org-id": "{IMS_ORGANIZATION_ID}"
      }
    }
  }
}
```

### クロード・コード

ローカルサーバーを指すClaude Code MCP設定ファイルにエントリを追加します。

```json
{
  "mcpServers": {
    "target-local": {
      "url": "http://localhost:8080/mcp"
    }
  }
}
```

>[!NOTE]
>
>ローカルサーバーに接続する場合、認証ヘッダーを手動で渡す必要があります（上記のカーソルの例に示すように）。 OAuth ブラウザーフローは、ホストされている`https://targetmcp.adobe.io/mcp` エンドポイントでのみ使用できます。

## Docker デプロイメント {#self-hosted-docker}

リポジトリには、コンテナ化されたデプロイメント用のDocker Compose設定が含まれています。

**Docker Composeで実行：**

```bash
make run-dc
```

**Docker イメージを直接作成して実行します：**

```bash
make build
make run-docker
```

## API エンドポイント {#self-hosted-endpoints}

セルフホスト型サーバーは、次のHTTP エンドポイントを公開します。

| エンドポイント | 説明 |
|---|---|
| `/mcp` | AI クライアント用のMCP プロトコル エンドポイント |
| `/ping` | 生存率チェック — `"Pong"`を返します |
| `/health` | ヘルスチェック — `{"status": "healthy"}`を返します |
| `/validate` | 入力検証エンドポイント |
| `/authorize` | OAuth認証エンドポイント |
| `/token` | OAuth トークンエンドポイント |

**ヘルスチェックの例：**

```bash
curl http://localhost:8080/health
# Response: {"status": "healthy"}
```

## トラブルシューティング {#self-hosted-troubleshoot}

+++サーバーを起動できません

1. Python 3.13以降がインストールされていることを確認します：`python --version`
1. 仮想環境がアクティブ化されていることを確認してください：`source .venv/bin/activate`
1. `.env`のすべての環境変数が正しく設定されていることを確認してください。
1. すべての依存関係が存在することを確認するために、もう一度`make uv-install`を実行します。

+++

+++MCP クライアントから接続できません

1. サーバーが実行されていて、ポートにアクセスできることを確認してください：`curl http://localhost:8080/ping`
1. MCP クライアント設定のサーバーURLが、実行中のサーバーアドレスと一致することを確認します。
1. Cursorの場合、`Authorization` ヘッダーに有効で期限切れでないIMS トークンが含まれていることを確認します。

+++

+++依存関係のインストールに失敗する（Adobeの内部ユーザー）

1. Artifactoryの資格情報が正しく設定されていることを確認します。
1. 内部Artifactory インスタンスへのネットワーク接続を確認します。
1. チームのDevOpsまたはプラットフォームエンジニアリングの担当者に連絡して、アーティファクトアクセスを入手してください。

+++

## 関連リソース {#self-hosted-related}

* [MCP クライアントの操作](target-mcp.md) — ホストされたエンドポイントの設定とツール参照
* [ モデル コンテキスト プロトコルのドキュメント ](https://modelcontextprotocol.io/introduction){target="_blank"}
* [[!DNL Adobe Target] 管理者API リファレンス ](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
