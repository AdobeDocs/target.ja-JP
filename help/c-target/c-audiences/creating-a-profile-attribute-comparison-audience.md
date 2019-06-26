---
description: オーディエンスを定義して、Targetオーディエンスライブラリまたはアクティビティのみのオーディエンスの2つのプロファイル属性を比較します。より大きい、より小さい、または等しい演算子を使用して、2 つの異なるプロファイル属性の値を動的に比較するオーディエンスを定義します。
keywords: オーディエンス、傾向、profile属性、比較、比較、オーディエンスの作成、オーディエンスの作成
seo-description: オーディエンスを定義して、Targetオーディエンスライブラリまたはアクティビティのみのオーディエンスの2つのプロファイル属性を比較します。より大きい、より小さい、または等しい演算子を使用して、2 つの異なるプロファイル属性の値を動的に比較するオーディエンスを定義します。
seo-title: プロファイル属性比較オーディエンスの作成Adobe Target
solution: 'Target '
title: プロファイル属性比較オーディエンスの作成
topic: Advanced,Standard,Classic
uuid: 17c1f2e0-4c1e-4b7a-8398-9ec147253a5f
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# プロファイル属性比較オーディエンスの作成{#create-a-profile-attribute-comparison-audience}

Define an audience to compare two profile attributes for your [Audience library](/help/c-target/c-audiences/audiences.md) or in an [activity-only audience](/help/c-target/creating-activity-only-audience.md). より大きい、より小さい、または等しい演算子を使用して、2 つの異なるプロファイル属性の値を動的に比較するオーディエンスを定義します。

>[!NOTE]
>
>この機能は [、訪問者プロファイル](../../c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E) カテゴリでのみ使用できます。

## 概要 {#section_303CBC78194D49A2A004945D425441E1}

オーディエンスは、誰が Target アクティビティに含まれるか、または除外されるかを決定するルールによって定義されます。オーディエンス定義には複数のルールを含めることができ、各ルールには複数のパラメーターを含めることができます。含めるルールのいずれかが訪問者プロファイルカテゴリーを使用する場合、訪問者プロファイル属性の特定の値に基づいてルールを定義するか、またはその属性の値を別の訪問者プロファイル属性と比較できます。

例えば、家具会社に勤務しており、次の 2 つの顧客傾向スコアを Target にアップロードしたとします。

* 次の 90 日間にダイニングルーム用の家具を購入する可能性
* 次の 90 日間にリビング用の家具を購入する可能性

ダイニングルーム用の家具を購入する傾向が、リビング用の家具を購入する傾向よりも高くなるように定義されたオーディエンスを作成できます。Target は、特定の訪問者のダイニングルームとリビングの傾向スコアを動的に比較して、その訪問者が前述のオーディエンスに該当するかどうかを判断します。

詳しくは、[データを Target に送信する方法](../../c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17)を参照してください。

## プロファイル属性比較オーディエンスの作成 {#section_7A62FD47D5C74C3EBC3417ACDBB85013}

1. **[!UICONTROL オーディエンス]**／オーディエンスを作成 **[!UICONTROL ]**／ルールを追加 **[!UICONTROL ]**／**[!UICONTROL 訪問者プロファイル]** をクリックします。
1. 「**[!UICONTROL 訪問者プロファイル]**」ドロップダウンリストから、属性を選択します。

   ![傾向スコア1](assets/propensity_score_1.png)

1. 評価基準を選択します。

   ![傾向スコア2](assets/propensity_score_2.png)

1. 「**[!UICONTROL 比較書式を選択]**」ドロップダウンリストから、「**[!UICONTROL 属性]**」を選択します。

   「static value」の比較タイプを使用すると、訪問者プロファイル属性を特定の値と比較できます。

   ![傾向スコア3](assets/propensity_score_3.png)

   >[!NOTE]
   >
   >ステップ1でデフォルトの訪問者プロファイルカテゴリのいずれかを使用している場合（例えば、新規訪問者または再訪問者）、静的値オプションのみを選択できます。動的比較オプションは、デフォルトカテゴリーでは使用できません。動的比較オプションを使用できない他の例としては、「セッションの最初のページ」、「他のテストに存在しない」、「セッションの最初のページ以外」、「カテゴリー親和性」があります。

1. 最初の属性と比較する追加属性を選択します。

   ![](assets/propensity_score_4.png)

## トレーニングビデオ {#section_3BB8DBF3418F4520B3E274B6F40AF8F3}

この機能を使用できるシナリオと詳細情報については、次のビデオを視聴してください。

>[!VIDEO](https://video.tv.adobe.com/v/23218/?captions=jpn)