---
solution: Target
product: target
title: Adobe Target MCP サーバーの基本を学ぶ
description: 前提条件、クライアント設定、トラブルシューティングなど、Adobe Target MCP サーバーをAI アシスタントに接続する方法について説明します。
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta" type="Informative"
role: User, Developer
level: Beginner, Intermediate
source-git-commit: d5d7a57ce6a3188f02e680c24849d773cb53457a
workflow-type: tm+mt
source-wordcount: '734'
ht-degree: 0%

---

# [!DNL Adobe Target] MCP サーバーの基本を学ぶ {#target-mcp-get-started}

>[!AVAILABILITY]
>
>[!DNL Adobe Target] MCP サーバーは、**パブリック Beta**&#x200B;のすべてのユーザーが利用できます。 現在、**Claude Web**、**Claude Desktop**、**Claude Code**、**Cursor**、および&#x200B;**ChatGPT**&#x200B;でサポートされています。

このページでは、[!DNL Adobe Target] MCP サーバーをAI アシスタントに接続し、設定を確認するために必要なすべての手順について説明します。

>[!IMPORTANT]
>
>Model Context Protocol （MCP）は新しいオープンソースの標準であり、セキュリティや信頼性に関するリスクが生じる可能性があります。 Adobe MCP サーバーの統合と関連ドキュメントは、いかなる保証も受けることなく、「現状のまま」提供されます。
>
>MCP クライアントまたはサーバーをAdobe製品に接続することは、お客様が選択した設定であり、お客様はMCP統合のセキュリティと適合性を評価する責任があります。 Adobeは、設定ミス、MCPの誤用、サードパーティ実装の脆弱性、またはMCP対応ワークフローを通じて実行された意図しないアクションから生じる問題については責任を負いません。
>
>リスクを軽減するために、Adobeでは、本番稼働前にサンドボックス環境で統合をテストし、MCPで開始されるすべてのアクションと応答を慎重にレビューおよび検証してから、確認または依存することを推奨しています。

## 前提条件 {#mcp-prerequisites}

[!DNL Adobe Target] MCP サーバーをMCP クライアントに接続する前に、次の点を確認してください。

* Adobe Experience Platform組織のアクティブな[!DNL Adobe Target] ライセンス （Adobe Experience Cloud サブスクリプション）があります。
* サポートされているMCP互換アプリケーション（現在、Claude Web、Claude Desktop、Claude Code、Cursor、またはChatGPT）があります。
* Adobe Admin Consoleで[!DNL Adobe Target]権限が設定されています。 Public Betaでは、23の使用可能なツールはすべて読み取り専用です。 **Observer**&#x200B;以上の役割は、MCP サーバーを使用するのに十分です。

>[!NOTE]
>
>書き込みツール（作成、更新、アクティブ化、非アクティブ化）は、パブリック Betaのパブリック MCP カタログを介して公開されません。 現時点では、編集者と承認者のロール権限によって追加のツールが使用されることはありません。 書き込みアクセスは、今後のリリースで利用できるようになります。

## [!DNL Adobe Target] MCP サーバーを接続します {#mcp-connect}

>[!NOTE]
>
>[!DNL Adobe Target] MCP サーバーは、認証にOAuth 2.0を使用しています。 Target MCP ツールを初めて使用すると、Adobe Experience Cloudにリダイレクトされてログインし、組織を選択し、要求された権限を付与します。 静的な認証情報は必要ありません。

**Claude DesktopまたはClaude Webから接続するには：**

1. MCP クライアント設定を開き、新しいMCP サーバーを追加します。
1. サーバーURLを入力してください：`https://targetmcp.adobe.io/mcp`
1. プロンプトが表示されたら、Adobe Experience Cloud資格情報を使用してAdobe IMSOAuth ログインを行います。
1. 認証されると、あらゆるツールをすぐに利用できるようになります。 「アクティブなすべてのTarget アクティビティを一覧表示」を試して、接続を確認します。

**クラウドコードから接続するには：**

Claude Code MCP設定に次を追加します。

```json
{
  "mcpServers": {
    "adobe-target": {
      "url": "https://targetmcp.adobe.io/mcp"
    }
  }
}
```

初回使用時にプロンプトが表示されたら、OAuth ブラウザーフローを完了します。

**カーソルから接続するには：**

1. **カーソル**&#x200B;を開き、**設定** → **MCP** → **新しいグローバル MCP サーバーを追加**&#x200B;に移動します。
1. 次の設定を追加します。

```json
{
  "mcpServers": {
    "target": {
      "type": "streamable-http",
      "url": "https://targetmcp.adobe.io/mcp"
    }
  }
}
```

1. 設定を保存します。 [!DNL Target] MCP サーバーは、使用可能なMCP サーバーに表示されます。

>[!TIP]
>
>間違った組織のアクティビティやデータが表示された場合は、Adobe Experience Cloudから完全にログアウトし、MCP サーバーを再接続して、再認証中に正しい組織を慎重に選択します。

## トラブルシューティング {#mcp-troubleshooting}

+++OAuth フローが失敗するか、正しくリダイレクトされません

1. Adobe Experience Cloudから完全にログアウトします。
1. adobe.com ドメインのブラウザーCookieを消去します。
1. 認証フローを再試行します。
1. プロンプトが表示されたら、正しい組織を選択します。
+++

+++間違った組織のアクティビティまたはデータが表示される

1. Adobe Experience Cloudから完全にログアウトします。
1. クライアント設定でMCP サーバーを切断して再接続します。
1. 再認証時に、正しい組織を慎重に選択します。
+++

+++ツールがエラーメッセージを返す

1. [!DNL Adobe Target]に&#x200B;**Observer**&#x200B;以上の役割があることを確認します（[前提条件](#mcp-prerequisites)を参照）。
1. 参照されるリソース（アクティビティ、オファー、オーディエンス）が組織内に存在することを確認します。
1. アクティビティ IDおよびその他のIDが正しいことを確認します。
+++

+++MCP サーバーに接続できません

1. インターネット接続を確認します。
1. クライアント設定でMCP サーバーのURLが正しく入力されていることを確認します。
1. MCP クライアント設定のサーバーを削除して再追加してみてください。
+++

## セキュリティと権限 {#mcp-security}

[!DNL Adobe Target] MCP サーバーは、Adobe ユーザーアカウントが表示または変更する権限を持つデータにのみアクセスできます。 すべての操作では、[!DNL Target]の役割の割り当てとワークスペースの権限が尊重されます。

サーバーは次のOAuth スコープを要求します。

* `AdobeID` – 基本的なAdobe ID
* `openid` — OpenID Connect認証
* `additional_info.projectedProductContext` — テナントの検出
* `read_organizations` – 組織レベルの操作
* `additional_info.roles` – 役割ベースのアクセス制御

OAuth トークンは、各リクエストのAdobe IMSに対して検証され、MCP サーバーによって永続的に保存されず、すべての通信でHTTPSが使用されます。

## 関連リソース {#mcp-get-started-related}

* [概要](target-mcp.md)
* [ユースケースとチュートリアル](target-mcp-use-cases.md)
* [MCP サーバーツールリファレンス](target-mcp-tools-reference.md)
* [モデル コンテキスト プロトコル ドキュメント](https://modelcontextprotocol.io/introduction){target="_blank"}
* [[!DNL Adobe Target]管理者API リファレンス](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
