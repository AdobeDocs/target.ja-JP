---
solution: Target
product: target
title: MCP クライアントの操作
description: MCP サーバーを使用してAdobe TargetをMCP クライアントに接続する方法について説明します
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta" type="Informative"
role: User, Developer
level: Beginner, Intermediate
hide: true
source-git-commit: 75f0dddcf65e9708aa564335974de1b6c3fd58ca
workflow-type: tm+mt
source-wordcount: '2267'
ht-degree: 1%

---

# MCP クライアントの操作 {#target-mcp}

>[!BEGINSHADEBOX]

目次：

* **[MCP クライアントの操作](target-mcp.md)**
* [MCP サーバーツールリファレンス](target-mcp-tools-reference.md)
* [MCP サーバーのセルフホスト](target-mcp-self-hosted.md)

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>[!DNL Adobe Target] MCP サーバーは現在、**Claude Web**、**Claude Desktop**、**Claude Code**、および&#x200B;**Cursor**&#x200B;で利用できます。 MCP互換アプリケーションのサポートは、今後のリリースで追加される予定です。

[!DNL Adobe Target] MCP統合により、A/B テスト、パーソナライゼーションアクティビティ、および推奨事項の条件を、AI アシスタントから直接検査、分析、および管理できます。 [!DNL Target]の読み取りと書き込みのAPIを平易な言語のワークフローに変換します。テスト ポートフォリオの監査、パフォーマンスレポートの確認、オーディエンスとオファーの管理、UIの操作やAPI呼び出しの記述を行うことなく、管理されたアクションを実行します。 このページでは、統合がどのように機能するのか、何ができるのか、どのように始めればよいのかについて説明します。

## モデル コンテキスト プロトコルとは何ですか？ {#mcp-overview}

マーケティング部門と最適化部門は、日々の作業を合理化するために、チャットベースのアプリケーションや開発者ツール（Anthropic Claude、OpenAI ChatGPT、Cursor、Microsoft Copilot Studioなど）への依存度を高めています。 これらのアプリケーションは、**Model Context Protocol （MCP）**&#x200B;をサポートしています。これは、アプリケーションがバックエンドツールを大規模言語モデル（LLM）に統一された方法で公開できるようにするオープンスタンダードです。

[!DNL Adobe Target]は、MCP互換アプリケーション内で実験、パーソナライゼーション、およびレコメンデーション操作を直接表示するMCP サーバーを提供するようになりました。 [!DNL Adobe Target]は、意思決定と実行のレイヤーとして機能し、AI アシスタントが推論と説明を処理します。これにより、複数の製品画面を移動したり、[!DNL Adobe Target] REST APIに対してクエリを記述したりすることなく、最適化インサイトに迅速にアクセスできます。

## 主な能力 {#mcp-capabilities}

[!DNL Adobe Target] MCP サーバーは、アクティビティ、オーディエンス、オファー、推奨事項、および実装設定に対する読み取りアクセスと書き込みアクセスの両方を提供します。 統合を活用することで、次のことが可能になります。

* **実験の調査と監査** - UIを移動することなく、任意のアクティビティのステータス、パフォーマンス、変更履歴、QA プレビューリンクを取得します。
* **結果を分析** - A/B、XT、AP、および自動ターゲットアクティビティのパフォーマンス、収益、およびA4T レポートを取得します。
* **アクティビティの管理** - A/B アクティビティおよびXT アクティビティを作成、更新およびアクティブ化し、トラフィックの分割、バリアント、スケジュール、優先度を調整します。
* **オーディエンスとオファーの管理** - オーディエンス、HTML オファーおよびJSON オファーを一覧表示、検査、作成します。
* **推奨事項の条件を確認** – 条件とカートベースのアルゴリズムを一覧表示および検査します。
* **監査の実装** - at.js設定、応答トークン、エンティティごとのリビジョン履歴を確認します。

>[!NOTE]
>
>書き込み操作（作成、更新、アクティブ化、非アクティブ化）には、安全性の注釈が含まれます。 ユーザーの明示的な確認がなければ、変更は実行されません。

## 利用可能なツール {#mcp-tools}

[!DNL Adobe Target] MCP サーバーは52個のツールを公開しています。 読み取りツールは、表示権限を持つ接続されているすべてのユーザーが利用できます。書き込みツールには編集者または承認者の役割が必要です。

### アクティビティツール – 読み取り

| ツール | 説明 |
|---|---|
| `list_target_activities` | 状態、タイプ、名前、日付、優先度、mbox、ワークスペースによるサーバーサイドフィルタリングを使用して、アクティビティを一覧表示します |
| `list_all_target_activities` | フィルターに一致するすべてのアクティビティを取得し、結果を通じて自動的にページ分割します |
| `get_ab_activity` | 特定のA/B アクティビティの詳細 |
| `get_xt_activity` | 特定のエクスペリエンスのターゲット設定（XT）アクティビティの詳細を取得 |
| `get_abt_activity` | 特定のAutomated Personalization（AP）アクティビティの詳細を取得 |

### アクティビティツール – 書き込み

| ツール | 説明 |
|---|---|
| `create_ab_activity` | 新しいA/B テストアクティビティの作成 |
| `create_xt_activity` | 新しいエクスペリエンスのターゲット設定（XT）アクティビティの作成 |
| `create_activity_from_modifications` | JavaScriptの修正からXT アクティビティを作成する |
| `update_ab_activity` | 既存のA/B アクティビティの更新 |
| `update_xt_activity` | 既存のXT アクティビティの更新 |
| `update_abt_activity` | 既存のAutomated Personalization アクティビティの更新 |
| `update_activity_state` | アクティビティのアクティブ化、非アクティブ化、一時停止、アーカイブ |
| `update_activity_schedule` | アクティビティの開始日と終了日の更新 |
| `update_activity_priority` | アクティビティの優先度の更新 |
| `update_activity_name` | アクティビティの名前を変更 |
| `add_activity_variant` | アクティビティへの新しいバリアント（エクスペリエンス）の追加 |
| `update_traffic_split` | バリエーション間のトラフィック配分を更新 |
| `update_variant_offer` | バリエーションのオファーまたはVEC修正を変更する |
| `remove_activity_variant` | アクティビティからのバリアントの削除 |

### オファーツール

| ツール | 説明 |
|---|---|
| `list_target_offers` | サーバーサイドのフィルタリングと並べ替えによるオファーのリスト |
| `list_all_target_offers` | 一致するすべてのオファーを取得フィルター、自動ページネーション |
| `get_target_offer` | 特定のオファーの詳細 |
| `create_target_offer` | 新しいHTML オファーの作成 |
| `create_target_json_offer` | 新しいJSON オファーの作成 |
| `update_target_offer` | 既存のHTML オファーの更新 |

### オーディエンスツール

| ツール | 説明 |
|---|---|
| `list_target_audiences` | サーバーサイドのフィルタリングと並べ替えにより、オーディエンスを一覧表示 |
| `create_target_audience` | オプションのターゲティングルールでオーディエンスを作成する |

### Mboxと位置情報ツール

| ツール | 説明 |
|---|---|
| `list_target_mboxes` | フィルタリングと並べ替えを使用したmboxのリスト |
| `list_all_target_mboxes` | フィルターに一致するすべてのmboxを取得し、自動ページネーションします |
| `get_target_mbox` | 特定のmboxの詳細を名前で取得 |
| `list_target_mbox_profile_attributes` | mboxに関連付けられたすべてのプロファイル属性のリスト |

### プロパティ

| ツール | 説明 |
|---|---|
| `list_target_properties` | すべてのTarget プロパティを一覧表示 |

### レポートとインサイトのツール

| ツール | 説明 |
|---|---|
| `get_ab_performance_report` | A/B、自動配分または自動ターゲットアクティビティのパフォーマンスレポートを取得します |
| `get_ab_orders_report` | A/Bまたは自動ターゲットアクティビティの注文と収益レポートの取得 |
| `get_xt_performance_report` | XT アクティビティのパフォーマンスレポートを取得 |
| `get_xt_orders_report` | XT アクティビティの注文と収益レポートの取得 |
| `get_apt_performance_report` | APまたは自動ターゲットアクティビティのパフォーマンスレポートを取得 |
| `get_activity_insights` | アクティビティを名前で検索し、詳細なパフォーマンスインサイトを取得します |
| `get_a4t_report` | アクティビティのAnalytics for Target （A4T）レポートを取得 |

### レコメンデーションツール

| ツール | 説明 |
|---|---|
| `list_target_criteria` | Recommendationsの条件をすべて一覧表示 |
| `get_target_criteria` | 特定のRecommendations条件の詳細を取得 |
| `update_target_criteria_cart` | Recommendations カート ベースの条件の更新 |

### 実装ツールと設定ツール

| ツール | 説明 |
|---|---|
| `get_atjs_settings` | AT.js設定と設定を取得する |
| `get_atjs_versions` | 利用可能なAT.js バージョンの取得 |
| `list_target_response_tokens` | Target テナント内のすべての応答トークンのリスト |
| `create_target_response_token` | 新しいカスタム応答トークンの作成 |

### 監査ツールとリビジョンツール

| ツール | 説明 |
|---|---|
| `get_target_revisions` | 作成者でフィルタリングされたリソースタイプの監査ログを取得します |
| `get_target_entity_revisions` | IDで特定のエンティティのすべてのリビジョンを取得 |

### ユーティリティ

| ツール | 説明 |
|---|---|
| `preview_activity` | Target アクティビティのQA プレビューURLの生成 |
| `create_page_delivery_segment` | VEC アクティビティターゲティング用のページ配信セグメントの作成 |
| `list_target_templates` | 利用可能なMCP リソースとテンプレートのリスト |
| `debug_token_info` | 現在のOAuth トークンのスコープとクレームを調べます |

## ユースケース {#mcp-use-cases}

次の例は、自然言語を使用して[!DNL Adobe Target] MCP サーバーを操作する方法を示しています。

| 目標 | プロンプト例 |
|---|---|
| **実験ステータス監査** | 「ホームページで現在アクティブなA/B テストは何ですか？ ステータス、トラフィックの割り当て、および各実行期間を表示します。」 |
| **パフォーマンスレビュー** | 「統計的有意性に達したアクティブなテストをすべて表示します。どのエクスペリエンスが成功していますか？」 |
| **収益分析** | 「AT4821 アクティビティの注文と収益レポートを取得し、どのエクスペリエンスが訪問者あたりの売上が最も多いかを要約します。」 |
| **A4T レポート** | 「チェックアウト最適化テスト用のA4T レポートを取得し、Analytics側のコンバージョンデータを要約します。」 |
| **アクティビティ管理** | 「アクティビティ 98765を一時停止し、アクティビティの優先度を20011111に更新します。」 |
| **アクティビティのインサイト** | 「私の「サマーセールバナー」テストのインサイトを得てください。パフォーマンスはどのような感じで、異常はありますか？」 |
| **オーディエンス管理** | 「モバイルユーザーをターゲットとしているすべてのオーディエンスをリストアップし、そのオーディエンスが関連するアクティビティを表示します。」 |
| **QAとプレビュー** | 「アクティビティ 12345のQA プレビューURLを生成して、アクティブ化する前にすべてのバリエーションを確認できるようにします。」 |
| **推奨事項のレビュー** | 「このアカウントで設定されたすべてのRecommendations基準を一覧表示し、使用中のアルゴリズムタイプを要約します。」 |
| **実装監査** | 「どのバージョンのat.jsが設定され、現在アクティブな応答トークンは何ですか？」 |
| **監査の変更** | 「過去30日間に行われたアクティビティの変更と98765の作成者をすべて表示します。」 |

## ユースケースのチュートリアル {#mcp-use-case-walkthroughs}

次のチュートリアルでは、[!DNL Adobe Target] MCP サーバーで自然言語プロンプトを使用して一般的なタスクを完了する方法を示します。

+++A/B テストの作成

**プロンプト：**
> 「Homepage Hero Image Test」というA/B テストを作成し、現在のヒーローを表示する「Control」と、新しい夏テーマのヒーロー画像を表示する「Variant」の2つのエクスペリエンスを使用します。 ホームページ mboxをターゲットにします。」

AI アシスタントは`create_ab_activity` ツールを使用して、説明した設定を使用してアクティビティを作成します。 ツールは、新しいアクティビティ IDと、作成されたエクスペリエンスの確認を返します。

+++

+++アクティビティパフォーマンスの確認

**プロンプト：**
> 「過去30日間の「チェックアウトフロー最適化」アクティビティのパフォーマンス指標を表示します。」

AI アシスタントは、`get_ab_performance_report`または`get_xt_performance_report`を使用して、指定された期間のコンバージョン率、訪問者数、その他の指標を取得します（アクティビティタイプによって異なります）。

+++

+++オファーの管理

**プロンプト：**
> 「夏セールのバナー」というHTMLのオファーを作成し、「すべての夏アイテムが20% オフ」というプロモーションバナーを表示します。」

AI アシスタントは`create_target_offer` ツールを使用して、指定したHTML コンテンツでオファーを作成し、新しいオファーIDで確認を返します。

+++

+++オーディエンスの構築

**プロンプト：**
> 「カリフォルニア在住のモバイルデバイス上のユーザーをターゲットとする、「カリフォルニアからのモバイル訪問者」と呼ばれるオーディエンスを作成します。」

AI アシスタントは、説明から導き出された適切なターゲティングルールで`create_target_audience` ツールを使用します。

+++

+++QA プレビューリンクの生成

**プロンプト：**
> 「アクティビティ 12345のプレビューURLを生成して、各エクスペリエンスをテストできます」

AI アシスタントは、`preview_activity` ツールを使用して、オーディエンスターゲティングをバイパスするクリック可能なURLを生成し、ブラウザーで各エクスペリエンスを直接表示できるようにします。

+++

+++Experience Targeting アクティビティの作成

**プロンプト：**
> 「異なる地域の訪問者に対して異なるヒーローバナーを表示する、「Geo Personalization」と呼ばれるエクスペリエンスターゲティング活動を作成します。」

AI アシスタントは`create_xt_activity`を使用して、説明した地域に従って、オーディエンスベースのエクスペリエンスマッピングを使用してアクティビティを構築します。

+++

+++アクティビティのスケジューリング

**プロンプト：**
> 「5月1日から5月31日に終了する活動12345のスケジュールを更新します。」

AI アシスタントは`update_activity_schedule` ツールを使用して、新しい開始日と終了日をアクティビティに適用します。

+++

## 前提条件 {#mcp-prerequisites}

[!DNL Adobe Target] MCP サーバーをMCP クライアントに接続する前に、次の点を確認してください。

* Adobe Experience Platform組織のアクティブな[!DNL Adobe Target] ライセンス （Adobe Experience Cloud サブスクリプション）があります。
* サポートされているMCP互換アプリケーション（現在、Claude Web、Claude Desktop、Claude Code、またはCursor）があります。
* Adobe Admin Consoleで[!DNL Adobe Target]権限が設定されています：
   * **Observer**&#x200B;の役割：読み取り専用ツール
   * **編集者**&#x200B;の役割：読み取り+作成ツール
   * **承認者**&#x200B;の役割：ツールの読み取り+作成+有効化/無効化

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

1. 操作に必要な権限が[!DNL Adobe Target]にあることを確認します（[前提条件](#mcp-prerequisites)を参照）。
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

## よくある質問 {#mcp-faq}

+++どのMCP クライアントがサポートされていますか？

[!DNL Adobe Target] MCP サーバーは現在、**Claude Web**、**Claude Desktop**、**Claude Code**、および&#x200B;**Cursor**&#x200B;で利用できます。 今後のリリースで、MCP互換アプリケーションのサポートが追加される可能性があります。
+++

+++MCP経由でアクセスできる[!DNL Adobe Target] オブジェクトは何ですか？

アクティビティ（A/B、XT、AP）、オーディエンス、オファー、プロパティ、mbox、Recommendations条件、応答トークン、at.js設定、A4T レポート、およびエンティティのリビジョン履歴にアクセスできます。 読み取りと書き込みの両方が52のツールでサポートされています。書き込み操作には、適切な役割と明示的な確認が必要です。
+++

+++MCP サーバーはアクティビティを作成または変更できますか？

はい。サーバーは、読み取り操作に加えて、アクティビティの作成、一時停止、優先順位の更新、トラフィック分割の調整などを可能にする書き込み操作を公開します。 書き込み操作は、[!DNL Adobe Target] UIと同じ権限モデルに従います。変更を行うには適切な役割が必要です。ユーザーの明示的な確認がなければ、アクションは実行されません。
+++

+++MCP サーバーを使用するには開発者アクセス権が必要ですか？

いいえ。MCP サーバーは、マーケティングとテクノロジーの両方のペルソナ向けに設計されています。 マーケターは、サポートされているMCP クライアントで自然言語プロンプトを使用してMarketoとやり取りできます。一方、開発者は、Claude CodeやCursorなどのツールで自然言語プロンプトを使用できます。
+++

+++[!DNL Adobe Target] データはMCP クライアントプロバイダーに送信されますか？

プロンプトを送信すると、MCP クライアントは、関連するコンテキスト（MCP サーバーから返された[!DNL Adobe Target] データを含む）をモデルに送信して処理する場合があります。 本番データに接続する前に、MCP クライアントプロバイダーのプライバシーおよびデータ処理ポリシーを確認してください。 Adobeのデータ処理は、[Adobe プライバシーポリシー](https://www.adobe.com/jp/privacy.html)および[&#x200B; データ保護条件](https://www.adobe.com/go/dpt-ww)に準拠しています。
+++

+++書き込み操作によって、ライブアクティビティに意図しない変更が生じる可能性がありますか？

書き込みツールには、安全注釈と確認ゲートが含まれます。 アクティビティのアクティブ化、優先順位の変更、トラフィック割り当ての更新など、状態を変更するアクションの前に、サーバーは、影響を受けるオブジェクト、トラフィックへの影響の推定、必要な明示的な承認手順を示す構造化された確認を表示します。 確認されるまで変更は行われません。
+++

+++[!DNL Adobe Target]でどのような権限が必要ですか？

少なくとも、**Observer**&#x200B;の役割によってすべての読み取りツールへのアクセスが許可されます。 **編集者**&#x200B;の役割により、アクティビティ、オーディエンス、オファーの作成が可能になります。 アクティビティをアクティブ化、非アクティブ化、またはアーカイブするには、**承認者**&#x200B;の役割が必要です。 現在のアクセス レベルが不明な場合は、[!DNL Adobe Target]管理者にお問い合わせください。
+++

+++複数のTarget組織またはプロパティでMCP サーバーを使用できますか？

MCP サーバーは、認証されたAdobe IMS資格情報に関連付けられている組織に対する操作をスコープします。 その組織内で複数のプロパティにアクセスできる場合は、`list_target_properties` ツールを使用してプロパティでクエリを実行し、それに応じて後続のリクエストをフィルタリングできます。
+++

## 関連リソース {#mcp-related}

* [MCP サーバーツールリファレンス](target-mcp-tools-reference.md)
* [&#x200B; [!DNL Adobe Target] MCP サーバーのセルフホスト](target-mcp-self-hosted.md)
* [&#x200B; モデル コンテキスト プロトコルのドキュメント &#x200B;](https://modelcontextprotocol.io/introduction){target="_blank"}
* [[!DNL Adobe Target] 管理者API リファレンス &#x200B;](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
* [&#x200B; カーソルのドキュメント &#x200B;](https://docs.cursor.com/){target="_blank"}
