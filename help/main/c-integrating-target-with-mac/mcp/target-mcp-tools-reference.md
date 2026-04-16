---
solution: Target
product: target
title: Adobe Target MCP サーバーツールリファレンス
description: Adobe Target MCP サーバーが公開する39の公開ツールすべてに関する完全なパラメーターリファレンスです。
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta" type="Informative"
role: Developer, User
level: Intermediate, Experienced
hide: true
source-git-commit: d24958d17ff62e957a8d3d6602abfcc8dfd67e46
workflow-type: tm+mt
source-wordcount: '2688'
ht-degree: 15%

---

# [!DNL Adobe Target] MCP サーバーツール リファレンス {#target-mcp-tools-reference}

>[!BEGINSHADEBOX]

目次：

* [MCP クライアントの操作](target-mcp.md)
* **[MCP サーバーツール リファレンス](target-mcp-tools-reference.md)**
* [MCP サーバーのセルフホスト](target-mcp-self-hosted.md)

>[!ENDSHADEBOX]

このページは、[!DNL Adobe Target] MCP サーバーによって公開されているすべての公開ツールの完全なリファレンスです。 各ツールには、説明、パラメーターの詳細、戻り値、自然言語プロンプトの例が表示されます。 セットアップ手順とユースケースについては、[MCP クライアントの操作](target-mcp.md)を参照してください。

>[!NOTE]
>
>ここでは公開ツールのみが文書化されています。 内部ツールとエージェントのみのツールは除外されます。 読み取りツールは、**Observer**&#x200B;以上の役割を持つ接続されているすべてのユーザーが利用できます。書き込みツールには、**編集者**&#x200B;または&#x200B;**承認者**&#x200B;の役割が必要です。

## アクティビティツール {#tools-activities}

+++list_target_activities

サーバーサイドのフィルタリングと並べ替えで[!DNL Adobe Target] アクティビティを一覧表示します。

ページ分割されたアクティビティのリストを取得します。 すべてのフィルターは、[!DNL Target]管理者APIによってサーバーサイドで適用されます。 サーバーは、1 ページにつき最大200個のアクティビティを返します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `limit` | 整数 | × | 返されるアクティビティの最大数（サーバーの最大数：200） |
| `offset` | 整数 | × | ページネーションのためにスキップするアクティビティの数 |
| `sort_by` | string | × | 並べ替えフィールド。 降順の`-`のプレフィックス （例：`-modifiedAt`）。 オプション：`id`, `name`, `state`, `priority`, `startsAt`, `endsAt`, `lifetimeStart`, `lifetimeEnd`, `createdAt`, `createdBy`, `modifiedAt`, `modifiedBy`, `type`, `thirdPartyId` |
| `state` | string | × | アクティビティの状態でフィルター：`approved` （ライブ/アクティブ）、`deactivated` （非アクティブ）、`paused`、`saved` （ドラフト） |
| `activity_type` | string | × | タイプ別のフィルター：`ab` （A/B テスト）、`xt` （エクスペリエンスのターゲット設定）、`abt` （Automated Personalization） |
| `name_contains` | string | × | 名前にこの文字列が含まれるアクティビティをフィルターする（大文字と小文字を区別しない） |
| `starts_after` | string | × | ISO 8601日 – この日付以降の活動 |
| `starts_before` | string | × | ISO 8601日 – この日付より前に開始された活動 |
| `modified_after` | string | × | ISO 8601日 – この日付以降に変更された活動 |
| `ends_after` | string | × | ISO 8601日 – この日付以降に終了する活動 |
| `ends_before` | string | × | ISO 8601日付 – この日付より前に終了する活動 |
| `workspace` | string | × | ワークスペース IDでフィルター |
| `segment_id` | string | × | オーディエンスセグメント IDでフィルター |
| `profile_attribute_id` | string | × | プロファイル属性IDでフィルター |
| `priority` | 整数 | × | 正確な優先度の値（0 ～ 999）でフィルタリング |
| `mbox` | string | × | mbox/場所名でフィルター |
| `offer_id` | string | × | オファーIDでフィルター |
| `view_id` | string | × | SPA ビューIDでフィルター |

**は、**&#x200B;個のJSON オブジェクトを`activities` （`id`、`name`、`state`、`type`、`priority`、`modifiedAt`、`startsAt`、`endsAt`を含むオブジェクトのリスト）および`total`を返します（合計数、返されるページサイズを超える場合があります）。

**プロンプトの例：** 「最も最近変更された順に並べ替えられたすべてのアクティブなA/B テストを一覧表示する」

+++

+++get_ab_activity

A/B アクティビティの詳細。

エクスペリエンス、場所、指標、ターゲティングルールなど、特定のA/B テストの完全な設定を取得します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `activity_id` | 整数 | ○ | A/B アクティビティの一意のID |

**戻り値：** メタデータ（名前、状態、優先度、日付）、エクスペリエンス、場所とオファー、目標と指標、ターゲティングルールなど、アクティビティの詳細を表示します。

**プロンプトの例：** 「A/B アクティビティの詳細を取得12345る」

+++

+++get_xt_activity

エクスペリエンスのターゲット設定（XT）アクティビティに関する詳細情報を取得します。

オーディエンスエクスペリエンスのマッピング、場所、指標など、特定のXT アクティビティの完全な設定を取得します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `activity_id` | 整数 | ○ | XT アクティビティの一意の識別子 |

**返品数：** メタデータ、オーディエンスマッピングでのエクスペリエンス、場所とオファー、目標と指標を含む完全なアクティビティの詳細。

**プロンプトの例：** 「エクスペリエンスのターゲット設定アクティビティの詳細を取得12345ます。」

+++

+++get_abt_activity

Automated Personalization（AP）アクティビティの詳細を確認します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `activity_id` | 整数 | ○ | AP アクティビティの一意のID |

**戻り値：** メタデータ、エクスペリエンス、場所、アルゴリズム設定を含むアクティビティの詳細を表示します。

**プロンプトの例：** 「自動Personalization アクティビティ 12345の詳細を取得する」

+++

+++create_ab_activity

新しいA/B テストアクティビティを作成します。

エクスペリエンス、オファー、ターゲティングなど、指定した設定で新しいA/B テストを作成します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `name` | string | ○ | アクティビティの名前 |
| `state` | string | × | 初期状態：`approved`、`deactivated`または`saved` （デフォルト：`saved`） |
| `priority` | 整数 | × | アクティビティの優先度（0 ～ 999、デフォルト：0） |
| `starts_at` | string | × | アクティビティ開始日（ISO 8601） |
| `ends_at` | string | × | アクティビティ終了日（ISO 8601） |
| `experiences` | 配列 | ○ | エクスペリエンス設定のリスト |
| `locations` | 配列 | ○ | 場所/mbox設定のリスト |
| `goals` | object | × | プライマリおよび副次目標指標 |
| `audiences` | 配列 | × | ターゲットオーディエンス設定 |
| `workspace_id` | string | × | アクティビティのWorkspace ID |

**戻り値：**&#x200B;作成されたアクティビティ オブジェクトに、割り当てられたIDが含まれています。

**プロンプトの例：** 「ホームページヒーローテスト」と呼ばれるA/B テストを作成し、2つのエクスペリエンスでホームページヒーローイメージをホームページヒーローボックスでテストします。」

+++

+++create_xt_activity

新しいエクスペリエンスのターゲット設定（XT）アクティビティを作成します。

ターゲティングルールに基づいて、異なるオーディエンスに異なるエクスペリエンスを配信するXT アクティビティを作成します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `name` | string | ○ | アクティビティの名前 |
| `state` | string | × | 初期状態：`approved`、`deactivated`または`saved` （デフォルト：`saved`） |
| `priority` | 整数 | × | アクティビティの優先度（0 ～ 999、デフォルト：0） |
| `starts_at` | string | × | アクティビティ開始日（ISO 8601） |
| `ends_at` | string | × | アクティビティ終了日（ISO 8601） |
| `experiences` | 配列 | ○ | オーディエンスマッピングによるエクスペリエンス設定のリスト |
| `locations` | 配列 | ○ | 場所/mbox設定のリスト |
| `goals` | object | × | プライマリおよび副次目標指標 |
| `workspace_id` | string | × | アクティビティのWorkspace ID |

**戻り値：**&#x200B;作成されたアクティビティ オブジェクトに、割り当てられたIDが含まれています。

**プロンプトの例：** 「異なる地域の訪問者に異なるコンテンツを表示する、「Geo Personalization」というエクスペリエンスのターゲット設定アクティビティを作成します。」

+++

+++update_ab_activity

既存のA/B アクティビティを更新します。

読み取り/変更/書き込みパターンを使用：現在の状態を取得し、変更をマージして検証し、更新を送信します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `activity_id` | 整数 | ○ | 更新するアクティビティの一意のID |
| `activity` | object | ○ | 更新するフィールド（名前、優先順位、エクスペリエンス、場所、目標など） |

**戻り値：**&#x200B;更新されたアクティビティ オブジェクト。

**プロンプトの例：** 「アクティビティ 12345を更新して、トラフィックの割り当てを70/30に変更します」

+++

+++update_xt_activity

既存のエクスペリエンスのターゲティングアクティビティを更新します。

read-modify-write パターンを使用します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `activity_id` | 整数 | ○ | 更新するXT アクティビティの一意のID |
| `activity` | object | ○ | 更新するフィールド |

**戻り値：**&#x200B;更新されたアクティビティ オブジェクト。

**プロンプトの例：** 「モバイル訪問者に新しいエクスペリエンスを追加するには、XT アクティビティ 12345を更新してください。」

+++

+++update_abt_activity

既存のAutomated Personalization アクティビティを更新します。

read-modify-write パターンを使用します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `activity_id` | 整数 | ○ | 更新するAP アクティビティの一意のID |
| `activity` | object | ○ | 更新するフィールド |

**戻り値：**&#x200B;更新されたアクティビティ オブジェクト。

**プロンプトの例：** 「自動Personalization アクティビティ 12345を更新して、最適化目標を変更してください。」

+++

+++update_activity_schedule

アクティビティの開始日と終了日を更新します。

他の設定を変更することなく、アクティビティのスケジュールを更新します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `activity_id` | 整数 | ○ | アクティビティの一意のID |
| `activity_type` | string | ○ | アクティビティの種類：`ab`、`xt`または`abt` |
| `starts_at` | string | × | 新しい開始日（ISO 8601） |
| `ends_at` | string | × | 新しい終了日（ISO 8601） |

**スケジュール更新の確認を返します：**。

**プロンプトの例：** 「A/B アクティビティ 12345のスケジュールを5月1日から5月31日まで更新します。」

+++

+++update_activity_state

アクティビティの状態を変更します（アクティベート、非アクティベート、または一時停止）。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `activity_id` | 整数 | ○ | アクティビティの一意のID |
| `state` | string | ○ | 新しい状態：`approved` （ライブ/アクティブ）、`deactivated` （非アクティブ）、`paused`、または`saved` （ドラフト） |

**更新されたアクティビティ状態を返します：**。

**プロンプトの例：** 「Activate activity 12345」または「Pause the Homepage Hero Test」

+++

+++update_activity_name

アクティビティの名前を変更します。

完全な設定を変更せずに、名前のみを更新します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `activity_id` | 整数 | ○ | アクティビティの一意のID |
| `name` | string | ○ | 新しいアクティビティ名 |

**戻り値：**&#x200B;更新されたアクティビティ オブジェクト。

**プロンプトの例：** 「アクティビティ 12345の名前を「サマーキャンペーンヒーローテスト」に変更します。」

+++

+++update_activity_priority

アクティビティの優先度を変更します。

複数のアクティビティが同じ場所をターゲットにしている場合は、優先度の高いアクティビティが優先されます。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `activity_id` | 整数 | ○ | アクティビティの一意のID |
| `priority` | 整数 | ○ | 新しい優先度の値（0 ～ 999；高い=高い優先度） |

**戻り値：**&#x200B;更新されたアクティビティ オブジェクト。

**プロンプトの例：** 「アクティビティ 12345の優先度を100に設定します。」

+++

+++add_activity_variant

アクティビティに新しいエクスペリエンス/バリアントを追加します。

オプションの作成、場所へのマッピング、トラフィックのリバランスなど、あらゆる構造調整を処理します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `activity_id` | 整数 | ○ | 変更するアクティビティのID |
| `activity_type` | string | ○ | アクティビティの種類：`ab`、`xt`または`abt` |
| `variant_name` | string | ○ | 新しいエクスペリエンス/バリアントの名前 |
| `offer_id` | 整数 | × | （フォームベース）使用する既存のオファーID |
| `offer_content` | string | × | （フォームベース）新しいインラインオファー用のHTML コンテンツ |
| `traffic_percentage` | 整数 | × | 新しいバリアントのトラフィック % （1 ～ 99）。 省略すると、トラフィックが均等に調整されます |
| `audience_id` | 整数 | × | バリアントのオーディエンス ID （XT アクティビティ） |
| `modifications` | 配列 | × | （VEC） CSS セレクターベースの変更のリスト |

**戻り値：**&#x200B;更新されたアクティビティ オブジェクト。

**プロンプトの例：** 「オファーの67890を使用して、A/B アクティビティ 12345に「Holiday Theme」という新しいバリアントを追加します。」

+++

+++update_traffic_split

バリエーションをまたいでトラフィック配分を更新。

パーセンテージは正確に100に合計する必要があります。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `activity_id` | 整数 | ○ | 変更するアクティビティのID |
| `activity_type` | string | ○ | アクティビティタイプ：`ab`または`abt` （XTはサポートされていません – オーディエンスターゲティング） |
| `splits` | object | ○ | ディクショナリーマッピングエクスペリエンス名をパーセンテージにマッピングします。 すべてのエクスペリエンスを含め、合計を100にする必要があります |

**戻り値：**&#x200B;更新されたアクティビティ オブジェクト。

**プロンプトの例：** 「アクティビティ 12345のトラフィックの分割を70% Controlと30% Variant Aに変更します。」

+++

+++update_variant_offer

特定のバリエーションのオファーを変更する。

フォームベースのアクティビティ（`offer_id`を使用）とVEC アクティビティ（`modifications`を使用）の両方で機能します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `activity_id` | 整数 | ○ | 変更するアクティビティのID |
| `activity_type` | string | ○ | アクティビティの種類：`ab`、`xt`または`abt` |
| `variant_name` | string | ○ | 更新するエクスペリエンス/バリアントの名前 |
| `offer_id` | 整数 | × | （フォームベース）新規オファーID |
| `offer_content` | string | × | （フォームベース）新しいインラインオファー用のHTML コンテンツ |
| `modifications` | 配列 | × | （VEC） CSS セレクターベースの変更の新しいリスト |

**戻り値：**&#x200B;更新されたアクティビティ オブジェクト。

**プロンプトの例：** 「アクティビティ 12345ージの「バリアント A」エクスペリエンスを更新して、オファー99999を使用する」

+++

+++remove_activity_variant

アクティビティからエクスペリエンス/バリアントを削除します。

エクスペリエンスを削除し、孤立したオプションをクリーンアップし、残りのバリエーションをまたいでトラフィックを均等に調整します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `activity_id` | 整数 | ○ | 変更するアクティビティのID |
| `activity_type` | string | ○ | アクティビティの種類：`ab`、`xt`または`abt` |
| `variant_name` | string | ○ | 削除するエクスペリエンス/バリアントの名前 |

**戻り値：**&#x200B;更新されたアクティビティ オブジェクト。

**プロンプトの例：** 「A/B アクティビティ 12345ースから「テスト バリアント」エクスペリエンスを削除する」

+++

## オファーツール {#tools-offers}

+++list_target_offers

[!DNL Target] テナントのすべてのオファーを一覧表示します。

オプションのフィルタリングを使用して、ページ分割されたコンテンツオファーのリストを取得します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `limit` | 整数 | × | 返されるオファーの最大数 |
| `offset` | 整数 | × | ページネーションのためにスキップするオファーの数 |
| `type` | string | × | オファーの種類でフィルター：`content` （HTML）、`json`または`redirect` |
| `name` | string | × | オファー名でフィルター（部分一致） |

**次のJSON オブジェクトを返します：**。`offers` （`id`、`name`、`type`、`content`、`modifiedAt`）および`total`を含むオブジェクトのリスト。

**プロンプトの例：** 「すべてのJSON オファーを一覧表示する」

+++

+++get_target_offer

特定のオファーに関する詳細情報を取得します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `offer_id` | 整数 | ○ | オファーの一意のID |

**返品：**&#x200B;完全なオファーの詳細（`id`、`name`、`type`、`content`、`workspace`、および`modifiedAt`など）。

**プロンプトの例：** 「オファーの詳細を取得67890ます。」

+++

+++create_target_offer

新しいHTML コンテンツオファーを作成します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `name` | string | ○ | オファーの名前 |
| `content` | string | ○ | オファーのHTMLまたはテキストコンテンツ |
| `workspace_id` | string | × | オファーのWorkspace ID |

**返品：**&#x200B;作成されたオファーに割り当てられたIDが含まれています。

**プロンプトの例：** 「プロモーションバナーを使用して、「サマーセールバナー」というHTML オファーを作成します。」

+++

+++create_target_json_offer

構造化データを配信するための新しいJSON オファーを作成します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `name` | string | ○ | オファーの名前 |
| `content` | object | ○ | オファーのJSON コンテンツ |
| `workspace_id` | string | × | オファーのWorkspace ID |

**返品：**&#x200B;作成されたオファーに割り当てられたIDが含まれています。

**プロンプトの例：** 「機能フラグ設定を使用して、「機能フラグ設定」という名前のJSON オファーを作成します。」

+++

+++update_target_offer

既存のオファーを更新します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `offer_id` | 整数 | ○ | 更新するオファーの一意のID |
| `name` | string | × | 更新されたオファー名 |
| `content` | 文字列またはオブジェクト | × | オファーコンテンツの更新 |

**返品：**&#x200B;更新されたオファーオブジェクト。

**プロンプトの例：** 「新しいプロモーションコンテンツを使用してオファー67890を更新する」

+++

## オーディエンスツール {#tools-audiences}

+++list_target_audiences

[!DNL Target] テナント内のすべてのオーディエンスを一覧表示します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `limit` | 整数 | × | 返されるオーディエンスの最大数 |
| `offset` | 整数 | × | ページネーションのためにスキップするオーディエンスの数 |

**次のJSON オブジェクトを返します：**。`audiences` （`id`、`name`、`description`、`origin`、`modifiedAt`）および`total`を含むオブジェクトのリスト。

**プロンプトの例：** 「すべてのオーディエンスを一覧表示する」

+++

+++create_target_audience

ターゲティングルールで新しいオーディエンスを作成します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `name` | string | ○ | オーディエンスの名前 |
| `description` | string | × | オーディエンスの説明 |
| `targetRule` | object | × | ターゲティングルール（地域、ブラウザー、カスタム属性など） |
| `workspace_id` | string | × | オーディエンスのWorkspace ID |

**戻り値：**&#x200B;作成されたオーディエンスとその割り当てられたID。

**プロンプトの例：** 「カリフォルニア州のモバイルユーザーをターゲットとする、「カリフォルニア州からのモバイル訪問者」という名前のオーディエンスを作成します。」

+++

## Mbox ツール {#tools-mboxes}

+++list_target_mboxes

[!DNL Target] テナント内のすべてのmboxを一覧表示します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `limit` | 整数 | × | 返されるmboxの最大数 |
| `offset` | 整数 | × | ページネーションのためにスキップするmboxの数 |
| `name` | string | × | mbox名でフィルター（部分一致） |
| `status` | string | × | ステータスでフィルター |

**次のJSON オブジェクトを返します：**。`mboxes` （`name`、`status`、`lastRequestTime`を含むオブジェクトのリスト）および`total`。

**プロンプトの例：** 「「ホームページ」を含むすべてのmboxを一覧表示する」

+++

+++get_target_mbox

特定のmboxに関する詳細情報を取得します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `mbox_name` | string | ○ | mboxの名前 |

**Mboxを使用して、**、`name`およびアクティビティのリストを含む、`status`個のMboxの詳細を返します。

**プロンプトの例：** 「mbox &#39;homepage-hero&#39;の詳細を取得する」

+++

+++list_target_mbox_profile_attributes

ターゲティングに使用できるすべてのmbox プロファイル属性を一覧表示します。

パラメーターは不要です。

**プロファイル属性オブジェクトのJSON配列**&#x200B;を返します。

**プロンプト例：** 「ターゲティングに使用できるプロファイル属性は何ですか？」

+++

## プロパティツール {#tools-properties}

+++list_target_properties

[!DNL Target] テナントのすべてのプロパティを一覧表示します。

プロパティは、アクティビティを整理し、アクセスを制御します。

パラメーターは不要です。

**戻り値：** `id`、`name`、`description`および`channel`を含むプロパティ オブジェクトのリスト。

**プロンプトの例：** 「すべてのターゲットプロパティを一覧表示する」

+++

## レポートツール {#tools-reporting}

+++get_ab_performance_report

A/B アクティビティのパフォーマンスレポートを取得します。

コンバージョン率、上昇率および信頼性レベルを取得します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `activity_id` | 整数 | ○ | A/B アクティビティの一意のID |
| `report_interval` | string | × | レポートの期間（例：`last7days`、`last30days`、カスタム日付範囲） |

**戻り値：** エクスペリエンスレベルの指標（訪問者、コンバージョン、コンバージョン率）、上昇率の計算、統計的な信頼性レベル、および収益指標（設定されている場合）。

**プロンプトの例：** 「過去30日間のA/B テストのパフォーマンスレポートを表示12345る」

+++

+++get_ab_orders_report

A/B アクティビティの注文/収益レポートを取得します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `activity_id` | 整数 | ○ | A/B アクティビティの一意のID |
| `report_interval` | string | × | レポートの期間 |

**返品数：**&#x200B;注文数、売上高、平均注文額（体験別）。

**プロンプトの例：** 「アクティビティ 12345の注文レポートを取得する」

+++

+++get_xt_performance_report

エクスペリエンスのターゲット設定アクティビティのパフォーマンスレポートを取得します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `activity_id` | 整数 | ○ | XT アクティビティの一意の識別子 |
| `report_interval` | string | × | レポートの期間 |

**エクスペリエンスレベルのパフォーマンス指標**&#x200B;を返します。

**プロンプトの例：** 「エクスペリエンスのターゲット設定アクティビティのパフォーマンスを表示54321ます。」

+++

+++get_xt_orders_report

Experience Targeting アクティビティの注文/収益レポートを取得します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `activity_id` | 整数 | ○ | XT アクティビティの一意の識別子 |
| `report_interval` | string | × | レポートの期間 |

**返品：**&#x200B;体験別の注文指標。

**プロンプトの例：** 「XT アクティビティ 54321の注文データを取得する」

+++

+++get_activity_report_by_name

アクティビティを名前で検索し、そのパフォーマンスレポートを取得します。

アクティビティ名を知っていてもIDが分からない場合に便利です。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `activity_name` | string | ○ | 検索するアクティビティの名前 |
| `report_interval` | string | × | レポートの期間 |

**戻り値：** アクティビティの詳細とパフォーマンス指標。

**プロンプトの例：** 「自分の「ホームページヒーローテスト」アクティビティのパフォーマンスレポートを取得する」

+++

## プレビューツール {#tools-preview}

+++preview_activity

[!DNL Target] アクティビティのブラウザーQA プレビューURLを生成します。

オーディエンスのターゲティングルールを無視して、特定のエクスペリエンスを強制的に表示するクリック可能なプレビューリンクを作成します。 A/B、XTおよびAutomated Personalization アクティビティで機能します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `activity_id` | 整数 | ○ | プレビューする[!DNL Target] アクティビティ ID |
| `experience_index` | 整数 | × | 0 ベースのエクスペリエンス指標： 省略すると、すべてのエクスペリエンスのURLが返されます |
| `url` | string | × | プレビューのページ URL。 フォームベースのアクティビティに必要です。 VEC アクティビティの場合、作成済みの場所が指定されている場合は上書きされます |

**次の値を返します：** アクティビティ情報（名前、タイプ、状態）、各エクスペリエンスのプレビューURL、エクスペリエンス名とインデックス。

**プロンプトの例：** 「アクティビティ 12345のプレビューURLを生成して、ブラウザーで各エクスペリエンスをテストできるようにします。」

+++

## 応答トークンツール {#tools-response-tokens}

+++list_target_response_tokens

[!DNL Target] テナント内のすべての応答トークンを一覧表示します。

設定されたすべての応答トークン（ビルトインとカスタムの両方）を取得します。

パラメーターは不要です。

**応答トークンオブジェクトの** JSON配列を`name`、`type`、`enabled`の状態で返します。

**プロンプトの例：** 「すべての応答トークンを一覧表示する」

+++

+++create_target_response_token

[!DNL Target]回の応答で追加データを収集するための新しいカスタム応答トークンを作成します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `token_name` | string | ○ | 応答トークンの名前 |
| `token_type` | string | ○ | トークンの種類：`SCRIPT`、`ACTIVITY`、`MBOX`、`GEO`または`CRS` |

**戻り値：**&#x200B;作成された応答トークンオブジェクト。

**プロンプトの例：** 「ACTIVITY タイプの&#39;campaign_id&#39;という名前のカスタム応答トークンを作成する」

+++

## リビジョンツール {#tools-revisions}

+++get_target_revisions

リソースタイプの監査ログを取得します。

作成者によるオプションのフィルタリングを使用して、[!DNL Target] リソースに加えられた変更を取得します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `revision_resource_type` | string | ○ | リソースの種類：`activity`、`offer`または`audience` |
| `modified_by` | string | × | 変更を加えたユーザーでフィルタリング |
| `limit` | 整数 | × | 返されるリビジョンの最大数 |
| `offset` | 整数 | × | ページネーションのためにスキップするリビジョン数 |

**タイムスタンプ、ユーザー、変更説明を含むリビジョン履歴**&#x200B;を返します。

**プロンプトの例：** 「アクティビティの変更に関する監査ログを表示する」

+++

+++get_target_entity_revisions

IDで特定のエンティティのすべてのリビジョンを取得します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `revision_resource_type` | string | ○ | リソースの種類：`activity`、`offer`または`audience` |
| `entity_id` | 整数 | ○ | エンティティの一意のID |

**指定されたエンティティのすべてのリビジョンの** JSON配列を返します。

**プロンプトの例：** 「アクティビティ 12345に加えられたすべての変更を表示する」

+++

## テンプレートツール {#tools-templates}

+++list_target_templates

アクティビティやオファーを作成するために利用できるMCP リソースとテンプレートを一覧表示します。

パラメーターは不要です。

**使用可能なテンプレートとリソースを一覧表示する** JSON オブジェクトを返します。

**プロンプト例：** 「アクティビティの作成に使用できるテンプレートは何ですか？」

+++

## ツールの概要 {#tools-summary}

| カテゴリ | カウント | ツール |
|---|---|---|
| アクティビティ | 17 | `list_target_activities`, `get_ab_activity`, `get_xt_activity`, `get_abt_activity`, `create_ab_activity`, `create_xt_activity`, `update_ab_activity`, `update_xt_activity`, `update_abt_activity`, `update_activity_schedule`, `update_activity_state`, `update_activity_name`, `update_activity_priority`, `add_activity_variant`, `update_traffic_split`, `update_variant_offer`, `remove_activity_variant` |
| オファー | 5 | `list_target_offers`、`get_target_offer`、`create_target_offer`、`create_target_json_offer`、`update_target_offer` |
| オーディエンス | 2 | `list_target_audiences`, `create_target_audience` |
| mbox | 3 | `list_target_mboxes`、`get_target_mbox`、`list_target_mbox_profile_attributes` |
| プロパティ | 1 | `list_target_properties` |
| レポート | 5 | `get_ab_performance_report`、`get_ab_orders_report`、`get_xt_performance_report`、`get_xt_orders_report`、`get_activity_report_by_name` |
| プレビュー | 1 | `preview_activity` |
| 応答トークン | 2 | `list_target_response_tokens`, `create_target_response_token` |
| リビジョン | 2 | `get_target_revisions`, `get_target_entity_revisions` |
| テンプレート | 1 | `list_target_templates` |
| **合計** | **39** | |

## 関連リソース {#tools-related}

* [MCP クライアントの操作](target-mcp.md)
* [ [!DNL Adobe Target] MCP サーバーのセルフホスト](target-mcp-self-hosted.md)
* [[!DNL Adobe Target] 管理者API リファレンス ](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}