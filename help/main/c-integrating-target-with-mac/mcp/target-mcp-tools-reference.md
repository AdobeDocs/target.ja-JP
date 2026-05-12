---
solution: Target
product: target
title: Adobe Target MCP サーバーツールリファレンス
description: Adobe Target MCP サーバーが公開する21個の読み取り専用ツールすべてのパラメーター参照を完了します。
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta" type="Informative"
role: Developer, User
level: Intermediate, Experienced
source-git-commit: 216b1103f501a3fcf955523d4bcc8254a8ea418d
workflow-type: tm+mt
source-wordcount: '1698'
ht-degree: 11%

---

# [!DNL Adobe Target] MCP サーバーツール リファレンス {#target-mcp-tools-reference}

>[!AVAILABILITY]
>
>[!DNL Adobe Target] MCP サーバーは、**パブリック Beta**&#x200B;のすべてのユーザーが利用できます。 現在、**Claude Web**、**Claude Desktop**、**Claude Code**、**Cursor**、および&#x200B;**ChatGPT**&#x200B;でサポートされています。

このページは、[!DNL Adobe Target] MCP サーバーによって公開されたすべての読み取り専用ツールの完全なリファレンスです。 各ツールには、説明、パラメーターの詳細、戻り値、自然言語プロンプトの例が表示されます。 セットアップ手順とユースケースについては、[基本を学ぶ](target-mcp-get-started.md)および[&#x200B; ユースケースとチュートリアル &#x200B;](target-mcp-use-cases.md)を参照してください。

>[!IMPORTANT]
>
>Model Context Protocol （MCP）は新しいオープンソースの標準であり、セキュリティや信頼性に関するリスクが生じる可能性があります。 Adobe MCP サーバーの統合と関連ドキュメントは、いかなる保証も受けることなく、「現状のまま」提供されます。
>
>MCP クライアントまたはサーバーをAdobe製品に接続することは、お客様が選択した設定であり、お客様はMCP統合のセキュリティと適合性を評価する責任があります。 Adobeは、設定ミス、MCPの誤用、サードパーティ実装の脆弱性、またはMCP対応ワークフローを通じて実行された意図しないアクションから生じる問題については責任を負いません。
>
>リスクを軽減するために、Adobeでは、本番稼働前にサンドボックス環境で統合をテストし、MCPで開始されるすべてのアクションと応答を慎重にレビューおよび検証してから、確認または依存することを推奨しています。

## 前提条件 {#tools-prerequisites}

[!DNL Adobe Target]の役割によって、使用可能なツールが決まります。

* **オブザーバー**&#x200B;以上：すべての読み取りツールへのアクセス
* **編集者**&#x200B;の役割：読み取りと書き込み（作成）ツールへのアクセス
* **承認者**&#x200B;の役割：ツールの読み取り、書き込み、アクティベート/非アクティベートへのアクセス

完全なセットアップ手順については、[基本を学ぶ](target-mcp-get-started.md)を参照してください。

## アクティビティツール {#tools-activities}

+++アクティビティのリスト

**ツール：** `list_target_activities`

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

+++A/B アクティビティの取得

**ツール：** `get_ab_activity`

A/B アクティビティの詳細。

エクスペリエンス、場所、指標、ターゲティングルールなど、特定のA/B テストの完全な設定を取得します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `activity_id` | 整数 | ○ | A/B アクティビティの一意のID |

**戻り値：** メタデータ（名前、状態、優先度、日付）、エクスペリエンス、場所とオファー、目標と指標、ターゲティングルールなど、アクティビティの詳細を表示します。

**プロンプトの例：** 「A/B アクティビティの詳細を取得12345る」

+++

+++エクスペリエンスのターゲティングアクティビティを取得

**ツール：** `get_xt_activity`

エクスペリエンスのターゲット設定（XT）アクティビティに関する詳細情報を取得します。

オーディエンスエクスペリエンスのマッピング、場所、指標など、特定のXT アクティビティの完全な設定を取得します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `activity_id` | 整数 | ○ | XT アクティビティの一意の識別子 |

**返品数：** メタデータ、オーディエンスマッピングでのエクスペリエンス、場所とオファー、目標と指標を含む完全なアクティビティの詳細。

**プロンプトの例：** 「エクスペリエンスのターゲット設定アクティビティの詳細を取得12345ます。」

+++

+++Automated Personalization アクティビティを取得

**ツール：** `get_abt_activity`

Automated Personalization（AP）アクティビティの詳細を確認します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `activity_id` | 整数 | ○ | AP アクティビティの一意のID |

**戻り値：** メタデータ、エクスペリエンス、場所、アルゴリズム設定を含むアクティビティの詳細を表示します。

**プロンプトの例：** 「自動Personalization アクティビティ 12345の詳細を取得する」

+++

<!--
+++Create an A/B activity

**Tool:** `create_ab_activity`

Create a new A/B test activity.

Creates a new A/B test with the specified configuration including experiences, offers, and targeting.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | string | Yes | Name of the activity |
| `state` | string | No | Initial state: `approved`, `deactivated`, or `saved` (default: `saved`) |
| `priority` | integer | No | Activity priority (0–999, default: 0) |
| `starts_at` | string | No | Activity start date (ISO 8601) |
| `ends_at` | string | No | Activity end date (ISO 8601) |
| `experiences` | array | Yes | List of experience configurations |
| `locations` | array | Yes | List of location/mbox configurations |
| `goals` | object | No | Primary and secondary goal metrics |
| `audiences` | array | No | Target audience configurations |
| `workspace_id` | string | No | Workspace ID for the activity |

**Returns:** The created activity object with its assigned ID.

**Example prompt:** "Create an A/B test called 'Homepage Hero Test' with two experiences testing different hero images on the homepage-hero mbox."

+++
-->

<!--
+++Create an Experience Targeting activity

**Tool:** `create_xt_activity`

Create a new Experience Targeting (XT) activity.

Creates an XT activity that delivers different experiences to different audiences based on targeting rules.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | string | Yes | Name of the activity |
| `state` | string | No | Initial state: `approved`, `deactivated`, or `saved` (default: `saved`) |
| `priority` | integer | No | Activity priority (0–999, default: 0) |
| `starts_at` | string | No | Activity start date (ISO 8601) |
| `ends_at` | string | No | Activity end date (ISO 8601) |
| `experiences` | array | Yes | List of experience configurations with audience mappings |
| `locations` | array | Yes | List of location/mbox configurations |
| `goals` | object | No | Primary and secondary goal metrics |
| `workspace_id` | string | No | Workspace ID for the activity |

**Returns:** The created activity object with its assigned ID.

**Example prompt:** "Create an Experience Targeting activity called 'Geo Personalization' that shows different content to visitors from different regions."

+++
-->

<!--
+++Update an A/B activity

**Tool:** `update_ab_activity`

Update an existing A/B activity.

Uses a read-modify-write pattern: fetches the current state, merges your changes, validates, and sends the update.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the activity to update |
| `activity` | object | Yes | Fields to update (name, priority, experiences, locations, goals, etc.) |

**Returns:** The updated activity object.

**Example prompt:** "Update activity 12345 to change the traffic allocation to 70/30."

+++
-->

<!--
+++Update an Experience Targeting activity

**Tool:** `update_xt_activity`

Update an existing Experience Targeting activity.

Uses a read-modify-write pattern.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the XT activity to update |
| `activity` | object | Yes | Fields to update |

**Returns:** The updated activity object.

**Example prompt:** "Update XT activity 12345 to add a new experience for mobile visitors."

+++
-->

<!--
+++Update an Automated Personalization activity

**Tool:** `update_abt_activity`

Update an existing Automated Personalization activity.

Uses a read-modify-write pattern.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the AP activity to update |
| `activity` | object | Yes | Fields to update |

**Returns:** The updated activity object.

**Example prompt:** "Update Auto-Personalization activity 12345 to change the optimization goal."

+++
-->

<!--
+++Update activity schedule

**Tool:** `update_activity_schedule`

Update activity start and end dates.

Updates the schedule for an activity without modifying other settings.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the activity |
| `activity_type` | string | Yes | Type of activity: `ab`, `xt`, or `abt` |
| `starts_at` | string | No | New start date (ISO 8601) |
| `ends_at` | string | No | New end date (ISO 8601) |

**Returns:** Confirmation of the schedule update.

**Example prompt:** "Update the schedule for A/B activity 12345 to run from May 1st to May 31st."

+++
-->

<!--
+++Change activity state

**Tool:** `update_activity_state`

Change activity state (activate, deactivate, or pause).

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the activity |
| `state` | string | Yes | New state: `approved` (live/active), `deactivated` (inactive), `paused`, or `saved` (draft) |

**Returns:** The updated activity state.

**Example prompt:** "Activate activity 12345" or "Pause the Homepage Hero Test."

+++
-->

<!--
+++Rename an activity

**Tool:** `update_activity_name`

Rename an activity.

Updates only the name without modifying the full configuration.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the activity |
| `name` | string | Yes | New activity name |

**Returns:** The updated activity object.

**Example prompt:** "Rename activity 12345 to 'Summer Campaign Hero Test'."

+++
-->

<!--
+++Change activity priority

**Tool:** `update_activity_priority`

Change activity priority.

Higher-priority activities take precedence when multiple activities target the same location.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the activity |
| `priority` | integer | Yes | New priority value (0–999; higher = higher priority) |

**Returns:** The updated activity object.

**Example prompt:** "Set the priority of activity 12345 to 100."

+++
-->

<!--
+++Add a variant to an activity

**Tool:** `add_activity_variant`

Add a new experience/variant to an activity.

Handles all structural coordination including creating options, mapping to locations, and rebalancing traffic.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The ID of the activity to modify |
| `activity_type` | string | Yes | Activity type: `ab`, `xt`, or `abt` |
| `variant_name` | string | Yes | Name for the new experience/variant |
| `offer_id` | integer | No | (Form-based) Existing offer ID to use |
| `offer_content` | string | No | (Form-based) HTML content for a new inline offer |
| `traffic_percentage` | integer | No | Traffic % for the new variant (1–99). If omitted, traffic is rebalanced evenly |
| `audience_id` | integer | No | Audience ID for the variant (XT activities) |
| `modifications` | array | No | (VEC) List of CSS selector-based modifications |

**Returns:** The updated activity object.

**Example prompt:** "Add a new variant called 'Holiday Theme' to A/B activity 12345 using offer 67890."

+++
-->

<!--
+++Update traffic split

**Tool:** `update_traffic_split`

Update traffic allocation across variants.

The percentages must sum to exactly 100.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The ID of the activity to modify |
| `activity_type` | string | Yes | Activity type: `ab` or `abt` (XT not supported — audience-targeted) |
| `splits` | object | Yes | Dictionary mapping experience name to percentage. Must include all experiences and sum to 100 |

**Returns:** The updated activity object.

**Example prompt:** "Change the traffic split for activity 12345 to 70% Control and 30% Variant A."

+++
-->

<!--
+++Change a variant's offer

**Tool:** `update_variant_offer`

Change the offer for a specific variant.

Works for both form-based activities (using `offer_id`) and VEC activities (using `modifications`).

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The ID of the activity to modify |
| `activity_type` | string | Yes | Activity type: `ab`, `xt`, or `abt` |
| `variant_name` | string | Yes | Name of the experience/variant to update |
| `offer_id` | integer | No | (Form-based) New offer ID |
| `offer_content` | string | No | (Form-based) HTML content for a new inline offer |
| `modifications` | array | No | (VEC) New list of CSS selector-based modifications |

**Returns:** The updated activity object.

**Example prompt:** "Update the 'Variant A' experience in activity 12345 to use offer 99999."

+++
-->

<!--
+++Remove a variant from an activity

**Tool:** `remove_activity_variant`

Remove an experience/variant from an activity.

Removes the experience, cleans up orphaned options, and rebalances traffic evenly across remaining variants.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The ID of the activity to modify |
| `activity_type` | string | Yes | Activity type: `ab`, `xt`, or `abt` |
| `variant_name` | string | Yes | Name of the experience/variant to remove |

**Returns:** The updated activity object.

**Example prompt:** "Remove the 'Test Variant' experience from A/B activity 12345."

+++
-->

## オファーツール {#tools-offers}

+++オファーのリスト

**ツール：** `list_target_offers`

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

+++オファーを取得

**ツール：** `get_target_offer`

特定のオファーに関する詳細情報を取得します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `offer_id` | 整数 | ○ | オファーの一意のID |

**返品：**&#x200B;完全なオファーの詳細（`id`、`name`、`type`、`content`、`workspace`、および`modifiedAt`など）。

**プロンプトの例：** 「オファーの詳細を取得67890ます。」

+++

<!--
+++Create an HTML offer

**Tool:** `create_target_offer`

Create a new HTML content offer.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | string | Yes | Name of the offer |
| `content` | string | Yes | HTML or text content for the offer |
| `workspace_id` | string | No | Workspace ID for the offer |

**Returns:** The created offer with its assigned ID.

**Example prompt:** "Create an HTML offer called 'Summer Sale Banner' with a promotional banner."

+++

+++Create a JSON offer

**Tool:** `create_target_json_offer`

Create a new JSON offer for delivering structured data.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | string | Yes | Name of the offer |
| `content` | object | Yes | JSON content for the offer |
| `workspace_id` | string | No | Workspace ID for the offer |

**Returns:** The created offer with its assigned ID.

**Example prompt:** "Create a JSON offer called 'Feature Flags Config' with feature toggle settings."

+++

+++Update an offer

**Tool:** `update_target_offer`

Update an existing offer.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `offer_id` | integer | Yes | The unique identifier of the offer to update |
| `name` | string | No | Updated offer name |
| `content` | string or object | No | Updated offer content |

**Returns:** The updated offer object.

**Example prompt:** "Update offer 67890 with new promotional content."

+++
-->

## オーディエンスツール {#tools-audiences}

+++オーディエンスのリスト

**ツール：** `list_target_audiences`

[!DNL Target] テナント内のすべてのオーディエンスを一覧表示します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `limit` | 整数 | × | 返されるオーディエンスの最大数 |
| `offset` | 整数 | × | ページネーションのためにスキップするオーディエンスの数 |

**次のJSON オブジェクトを返します：**。`audiences` （`id`、`name`、`description`、`origin`、`modifiedAt`）および`total`を含むオブジェクトのリスト。

**プロンプトの例：** 「すべてのオーディエンスを一覧表示する」

+++

<!--
+++Create an audience

**Tool:** `create_target_audience`

Create a new audience with targeting rules.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | string | Yes | Name of the audience |
| `description` | string | No | Description of the audience |
| `targetRule` | object | No | Targeting rules (geo, browser, custom attributes, etc.) |
| `workspace_id` | string | No | Workspace ID for the audience |

**Returns:** The created audience with its assigned ID.

**Example prompt:** "Create an audience called 'Mobile Visitors from California' targeting mobile users in CA."

+++
-->

## Mbox ツール {#tools-mboxes}

+++リスト mbox

**ツール：** `list_target_mboxes`

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

+++mboxを入手

**ツール：** `get_target_mbox`

特定のmboxに関する詳細情報を取得します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `mbox_name` | string | ○ | mboxの名前 |

**Mboxを使用して、`name`、`status`およびアクティビティのリストを含む、**&#x200B;個のMboxの詳細を返します。

**プロンプトの例：** 「mbox &#39;homepage-hero&#39;の詳細を取得する」

+++

+++mbox プロファイル属性のリスト

**ツール：** `list_target_mbox_profile_attributes`

ターゲティングに使用できるすべてのmbox プロファイル属性を一覧表示します。

パラメーターは不要です。

**プロファイル属性オブジェクトのJSON配列**&#x200B;を返します。

**プロンプト例：** 「ターゲティングに使用できるプロファイル属性は何ですか？」

+++

## プロパティツール {#tools-properties}

+++リストプロパティ

**ツール：** `list_target_properties`

[!DNL Target] テナントのすべてのプロパティを一覧表示します。

プロパティは、アクティビティを整理し、アクセスを制御します。

パラメーターは不要です。

**戻り値：** `id`、`name`、`description`および`channel`を含むプロパティ オブジェクトのリスト。

**プロンプトの例：** 「すべてのターゲットプロパティを一覧表示する」

+++

## レポートツール {#tools-reporting}

+++A/B パフォーマンスレポートを読む

**ツール：** `get_ab_performance_report`

A/B アクティビティのパフォーマンスレポートを取得します。

コンバージョン率、上昇率および信頼性レベルを取得します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `activity_id` | 整数 | ○ | A/B アクティビティの一意のID |
| `report_interval` | string | × | レポートの期間（例：`last7days`、`last30days`、カスタム日付範囲） |

**戻り値：** エクスペリエンスレベルの指標（訪問者、コンバージョン、コンバージョン率）、上昇率の計算、統計的な信頼性レベル、および収益指標（設定されている場合）。

**プロンプトの例：** 「過去30日間のA/B テストのパフォーマンスレポートを表示12345る」

+++

+++A/B注文レポートの取得

**ツール：** `get_ab_orders_report`

A/B アクティビティの注文/収益レポートを取得します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `activity_id` | 整数 | ○ | A/B アクティビティの一意のID |
| `report_interval` | string | × | レポートの期間 |

**返品数：**&#x200B;注文数、売上高、平均注文額（体験別）。

**プロンプトの例：** 「アクティビティ 12345の注文レポートを取得する」

+++

+++エクスペリエンスのターゲット設定に関するパフォーマンスレポートを読む

**ツール：** `get_xt_performance_report`

エクスペリエンスのターゲット設定アクティビティのパフォーマンスレポートを取得します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `activity_id` | 整数 | ○ | XT アクティビティの一意の識別子 |
| `report_interval` | string | × | レポートの期間 |

**エクスペリエンスレベルのパフォーマンス指標**&#x200B;を返します。

**プロンプトの例：** 「エクスペリエンスのターゲット設定アクティビティのパフォーマンスを表示54321ます。」

+++

+++エクスペリエンスのターゲット設定の注文レポートを取得

**ツール：** `get_xt_orders_report`

Experience Targeting アクティビティの注文/収益レポートを取得します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `activity_id` | 整数 | ○ | XT アクティビティの一意の識別子 |
| `report_interval` | string | × | レポートの期間 |

**返品：**&#x200B;体験別の注文指標。

**プロンプトの例：** 「XT アクティビティ 54321の注文データを取得する」

+++

+++アクティビティ名によるパフォーマンスレポートの取得

**ツール：** `get_activity_report_by_name`

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

+++アクティビティのプレビュー

**ツール：** `preview_activity`

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

+++応答トークンのリスト

**ツール：** `list_target_response_tokens`

[!DNL Target] テナント内のすべての応答トークンを一覧表示します。

設定されたすべての応答トークン（ビルトインとカスタムの両方）を取得します。

パラメーターは不要です。

**応答トークンオブジェクトの** JSON配列を`name`、`type`、`enabled`の状態で返します。

**プロンプトの例：** 「すべての応答トークンを一覧表示する」

+++

<!--
+++Create a response token

**Tool:** `create_target_response_token`

Create a new custom response token for collecting additional data in [!DNL Target] responses.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `token_name` | string | Yes | Name of the response token |
| `token_type` | string | Yes | Type of token: `SCRIPT`, `ACTIVITY`, `MBOX`, `GEO`, or `CRS` |

**Returns:** The created response token object.

**Example prompt:** "Create a custom response token called 'campaign_id' of type ACTIVITY."

+++
-->

## リビジョンツール {#tools-revisions}

+++監査ログの取得

**ツール：** `get_target_revisions`

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

+++特定のエンティティのリビジョンを取得

**ツール：** `get_target_entity_revisions`

IDで特定のエンティティのすべてのリビジョンを取得します。

| パラメーター | タイプ | 必須 | 説明 |
|---|---|---|---|
| `revision_resource_type` | string | ○ | リソースの種類：`activity`、`offer`または`audience` |
| `entity_id` | 整数 | ○ | エンティティの一意のID |

**指定されたエンティティのすべてのリビジョンの** JSON配列を返します。

**プロンプトの例：** 「アクティビティ 12345に加えられたすべての変更を表示する」

+++

## テンプレートツール {#tools-templates}

+++使用可能なテンプレートのリスト

**ツール：** `list_target_templates`

アクティビティやオファーを作成するために利用できるMCP リソースとテンプレートを一覧表示します。

パラメーターは不要です。

**使用可能なテンプレートとリソースを一覧表示する** JSON オブジェクトを返します。

**プロンプト例：** 「アクティビティの作成に使用できるテンプレートは何ですか？」

+++

## ツールの概要 {#tools-summary}

| カテゴリ | カウント | ツール |
|---|---|---|
| アクティビティ | 4 | `list_target_activities`, `get_ab_activity`, `get_xt_activity`, `get_abt_activity` |
| オファー | 2 | `list_target_offers`, `get_target_offer` |
| オーディエンス | 1 | `list_target_audiences` |
| mbox | 3 | `list_target_mboxes`, `get_target_mbox`, `list_target_mbox_profile_attributes` |
| プロパティ | 1 | `list_target_properties` |
| レポート | 5 | `get_ab_performance_report`, `get_ab_orders_report`, `get_xt_performance_report`, `get_xt_orders_report`, `get_activity_report_by_name` |
| プレビュー | 1 | `preview_activity` |
| 応答トークン | 1 | `list_target_response_tokens` |
| リビジョン | 2 | `get_target_revisions`, `get_target_entity_revisions` |
| テンプレート | 1 | `list_target_templates` |
| **合計** | **21** | |

## 関連リソース {#tools-related}

* [MCP クライアントの操作](target-mcp.md)
* [[!DNL Adobe Target]管理者API リファレンス](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
