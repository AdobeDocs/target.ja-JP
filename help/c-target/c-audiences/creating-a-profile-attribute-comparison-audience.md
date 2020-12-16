---
keywords: audience;propensity;profile attribute;compare;comparison;create audience;creating audience
description: Target オーディエンスライブラリに対して、またはアクティビティのみのオーディエンスにおいて、2 つのプロファイル属性を比較するオーディエンスを定義します。より大きい、より小さい、または等しい演算子を使用して、2 つの異なるプロファイル属性の値を動的に比較するオーディエンスを定義します。
title: プロファイル属性比較オーディエンスの作成（Adobe Target）
feature: audiences
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 99%

---


# プロファイル属性比較オーディエンスの作成{#create-a-profile-attribute-comparison-audience}

[オーディエンスライブラリ](/help/c-target/c-audiences/audiences.md)に対して、または[アクティビティのみのオーディエンス](/help/c-target/creating-activity-only-audience.md)において、2 つのプロファイル属性を比較するオーディエンスを定義します。より大きい、より小さい、または等しい演算子を使用して、2 つの異なるプロファイル属性の値を動的に比較するオーディエンスを定義します。

>[!NOTE]
>
>この機能は [、訪問者プロファイル](/help/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E) カテゴリでのみ使用できます。

## 概要 {#section_303CBC78194D49A2A004945D425441E1}

オーディエンスは、誰が Target アクティビティに含まれるか、または除外されるかを決定するルールによって定義されます。オーディエンス定義には複数のルールを含めることができ、各ルールには複数のパラメーターを含めることができます。含めるルールのいずれかが訪問者プロファイルカテゴリーを使用する場合、訪問者プロファイル属性の特定の値に基づいてルールを定義するか、またはその属性の値を別の訪問者プロファイル属性と比較できます。

例えば、家具会社に勤務しており、次の 2 つの顧客傾向スコアを Target にアップロードしたとします。

* 次の 90 日間にダイニングルーム用の家具を購入する可能性
* 次の 90 日間にリビング用の家具を購入する可能性

ダイニングルーム用の家具を購入する傾向が、リビング用の家具を購入する傾向よりも高くなるように定義されたオーディエンスを作成できます。Target は、特定の訪問者のダイニングルームとリビングの傾向スコアを動的に比較して、その訪問者が前述のオーディエンスに該当するかどうかを判断します。

詳しくは、[データを Target に送信する方法](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17)を参照してください。

## プロファイル属性比較オーディエンスの作成 {#section_7A62FD47D5C74C3EBC3417ACDBB85013}

1. **[!UICONTROL Audiences]**／**[!UICONTROL Create Audience]**／**[!UICONTROL Add Rule]**／**[!UICONTROL Visitor Profile]** の順にクリックします。
1. **[!UICONTROL 訪問者プロファイル]**&#x200B;ドロップダウンリストから、属性を選択します。

   ![傾向スコア 1](assets/propensity_score_1.png)

1. 評価基準を選択します。

   ![傾向スコア 2](assets/propensity_score_2.png)

1. **[!UICONTROL 比較書式を選択]**&#x200B;ドロップダウンリストから、「**[!UICONTROL 属性]**」を選択します。

   「static value」の比較タイプを使用すると、訪問者プロファイル属性を特定の値と比較できます。

   ![傾向スコア 3](assets/propensity_score_3.png)

   >[!NOTE]
   >
   >ステップ1でデフォルトの訪問者プロファイルカテゴリのいずれかを使用している場合（例えば、新規訪問者または再訪問者）、静的値オプションのみを選択できます。動的比較オプションは、デフォルトカテゴリーでは使用できません。動的比較オプションを使用できない他の例としては、「セッションの最初のページ」、「他のテストに存在しない」、「セッションの最初のページ以外」、「カテゴリー親和性」があります。

1. 最初の属性と比較する追加属性を選択します。

   ![](assets/propensity_score_4.png)

## トレーニングビデオ![概要バッジ](/help/assets/overview.png) {#section_3BB8DBF3418F4520B3E274B6F40AF8F3}

この機能を使用できるシナリオと詳細情報については、次のビデオを視聴してください。

>[!VIDEO](https://video.tv.adobe.com/v/23218/)