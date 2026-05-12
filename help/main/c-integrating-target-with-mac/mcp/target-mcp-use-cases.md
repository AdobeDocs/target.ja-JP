---
solution: Target
product: target
title: Adobe Target MCP Server - ユースケースとウォークスルー
description: Adobe Target MCP サーバーの一般的なユースケースとステップバイステップのプロンプトウォークスルーをご覧ください。
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta" type="Informative"
role: User, Developer
level: Beginner, Intermediate
source-git-commit: d5d7a57ce6a3188f02e680c24849d773cb53457a
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 1%

---

# [!DNL Adobe Target] MCP サーバー – ユースケースとウォークスルー {#target-mcp-use-cases}

>[!AVAILABILITY]
>
>[!DNL Adobe Target] MCP サーバーは、**パブリック Beta**&#x200B;のすべてのユーザーが利用できます。 現在、**Claude Web**、**Claude Desktop**、**Claude Code**、**Cursor**、および&#x200B;**ChatGPT**&#x200B;でサポートされています。

このページでは、クイックルックアップからマルチステップ分析およびレポートタスクまで、自然言語プロンプトを使用して[!DNL Adobe Target] MCP サーバーで達成できることについて説明します。

>[!IMPORTANT]
>
>Model Context Protocol （MCP）は新しいオープンソースの標準であり、セキュリティや信頼性に関するリスクが生じる可能性があります。 Adobe MCP サーバーの統合と関連ドキュメントは、いかなる保証も受けることなく、「現状のまま」提供されます。
>
>MCP クライアントまたはサーバーをAdobe製品に接続することは、お客様が選択した設定であり、お客様はMCP統合のセキュリティと適合性を評価する責任があります。 Adobeは、設定ミス、MCPの誤用、サードパーティ実装の脆弱性、またはMCP対応ワークフローを通じて実行された意図しないアクションから生じる問題については責任を負いません。
>
>リスクを軽減するために、Adobeでは、本番稼働前にサンドボックス環境で統合をテストし、MCPで開始されるすべてのアクションと応答を慎重にレビューおよび検証してから、確認または依存することを推奨しています。

## ユースケース {#mcp-use-cases}

次の例は、自然言語を使用して[!DNL Adobe Target] MCP サーバーを操作する方法を示しています。

| 目標 | プロンプト例 |
|---|---|
| **実験ステータス監査** | 「ホームページで現在アクティブなA/B テストは何ですか？ ステータス、トラフィックの割り当て、および各実行期間を表示します。」 |
| **パフォーマンスレビュー** | 「統計的有意性に達したアクティブなテストをすべて表示します。どのエクスペリエンスが成功していますか？」 |
| **収益分析** | 「AT4821 アクティビティの注文と収益レポートを取得し、どのエクスペリエンスが訪問者あたりの売上が最も多いかを要約します。」 |
| **A4T レポート** | 「チェックアウト最適化テスト用のA4T レポートを取得し、Analytics側のコンバージョンデータを要約します。」 |
| **アクティビティのインサイト** | 「私の「サマーセールバナー」テストのインサイトを得てください。パフォーマンスはどのような感じで、異常はありますか？」 |
| **オーディエンス管理** | 「モバイルユーザーをターゲットとしているすべてのオーディエンスをリストアップし、そのオーディエンスが関連するアクティビティを表示します。」 |
| **QAとプレビュー** | 「アクティビティ 12345のQA プレビューURLを生成して、アクティブ化する前にすべてのバリエーションを確認できるようにします。」 |
| **推奨事項のレビュー** | 「このアカウントで設定されたすべてのRecommendations基準を一覧表示し、使用中のアルゴリズムタイプを要約します。」 |
| **実装監査** | 「どのバージョンのat.jsが設定され、現在アクティブな応答トークンは何ですか？」 |
| **監査の変更** | 「過去30日間に行われたアクティビティの変更と98765の作成者をすべて表示します。」 |

## ユースケースのチュートリアル {#mcp-use-case-walkthroughs}

次のチュートリアルでは、[!DNL Adobe Target] MCP サーバーで自然言語プロンプトを使用して一般的なタスクを完了する方法を示します。

<!--
+++Creating an A/B test

**Prompt:**
"Create an A/B test called 'Homepage Hero Image Test' with two experiences: 'Control' showing the current hero and 'Variant' showing a new summer-themed hero image. Target the homepage mbox."

The AI assistant uses the `create_ab_activity` tool to create the activity with the configuration you described. The tool returns the new activity ID and a confirmation of the created experiences.

+++
-->

+++アクティビティパフォーマンスの確認

**プロンプト：**
「過去30日間の「チェックアウトフロー最適化」アクティビティのパフォーマンス指標を表示します。」

AI アシスタントは、`get_ab_performance_report`または`get_xt_performance_report`を使用して、指定された期間のコンバージョン率、訪問者数、その他の指標を取得します（アクティビティタイプによって異なります）。

+++

<!--
+++Managing offers

**Prompt:**
"Create an HTML offer called 'Summer Sale Banner' with a promotional banner that says '20% off all summer items'."

The AI assistant uses the `create_target_offer` tool to create the offer with your specified HTML content and returns a confirmation with the new offer ID.

+++

+++Building an audience

**Prompt:**
"Create an audience called 'Mobile Visitors from California' that targets users on mobile devices located in California."

The AI assistant uses the `create_target_audience` tool with the appropriate targeting rules derived from your description.

+++
-->

+++QA プレビューリンクの生成

**プロンプト：**
「アクティビティ 12345のプレビューURLを生成して、各エクスペリエンスをテストできます」

AI アシスタントは、`preview_activity` ツールを使用して、オーディエンスターゲティングをバイパスするクリック可能なURLを生成し、ブラウザーで各エクスペリエンスを直接表示できるようにします。

+++

<!--
+++Creating an Experience Targeting activity

**Prompt:**
"Create an Experience Targeting activity called 'Geo Personalization' that shows different hero banners to visitors from different regions."

The AI assistant uses `create_xt_activity` to build the activity with audience-based experience mapping according to the regions you describe.

+++

+++Scheduling an activity

**Prompt:**
"Update the schedule for activity 12345 to start on May 1st and end on May 31st."

The AI assistant uses the `update_activity_schedule` tool to apply the new start and end dates to the activity.

+++
-->

## 関連リソース {#mcp-use-cases-related}

* [概要](target-mcp.md)
* [基本を学ぶ](target-mcp-get-started.md)
* [MCP サーバーツールリファレンス](target-mcp-tools-reference.md)
* [モデル コンテキスト プロトコル ドキュメント](https://modelcontextprotocol.io/introduction){target="_blank"}
* [[!DNL Adobe Target]管理者API リファレンス](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
