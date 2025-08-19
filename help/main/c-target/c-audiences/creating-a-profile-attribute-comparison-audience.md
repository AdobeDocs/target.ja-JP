---
keywords: オーディエンス、傾向、profile属性、比較、比較、オーディエンスの作成、オーディエンスの作成
description: 2 つのプロファイル属性を比較するオーディエンスの定義方法を説明します。
title: オーディエンスで使用する 2 つのプロファイル属性を比較できますか？
feature: Audiences
exl-id: 033e90f1-5a05-4fce-a520-68826860a908
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 51%

---

# プロファイル属性比較オーディエンスの作成

[!DNL Adobe Target] のオーディエンスを定義して、[ オーディエンスライブラリ ](/help/main/c-target/c-audiences/audiences.md) または [ アクティビティのみのオーディエンス ](/help/main/c-target/creating-activity-only-audience.md) の 2 つのプロファイル属性を比較します。 より大きい、より小さい、または等しい演算子を使用して、2 つの異なるプロファイル属性の値を動的に比較するオーディエンスを定義します。

>[!NOTE]
>
>この機能は、[[!UICONTROL Visitor Profile]](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E) カテゴリでのみ使用できます。

## 概要 {#section_303CBC78194D49A2A004945D425441E1}

オーディエンスは、誰が [!DNL Target] アクティビティに含まれるか、または除外されるかを決定するルールによって定義されます。オーディエンス定義には複数のルールを含めることができ、各ルールには複数のパラメーターを含めることができます。含めるルールの 1 つが [!UICONTROL Visitor Profile] カテゴリを使用する場合、訪問者プロファイル属性の特定の値に基づいてルールを定義したり、その属性の値を別の訪問者プロファイル属性と比較したりできます。

例えば、ある家具会社で働いていて、2 つの顧客の傾向スコアを [!DNL Target] にアップロードしたとします。

* 次の 90 日間にダイニングルーム用の家具を購入する可能性
* 次の 90 日間にリビング用の家具を購入する可能性

ダイニングルーム用の家具を購入する傾向が、リビング用の家具を購入する傾向よりも高くなるように定義されたオーディエンスを作成できます。[!DNL Target] の後、特定の訪問者のダイニングルームとリビングルームの傾向スコアを動的に比較し、その訪問者がこのオーディエンスに該当するかどうかを判断します。

詳しくは、[データを Target に送信する方法](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=ja){target=_blank}を参照してください。

## プロファイル属性比較オーディエンスの作成 {#section_7A62FD47D5C74C3EBC3417ACDBB85013}

1. **[!UICONTROL Audiences]**／**[!UICONTROL Create Audience]**&#x200B;をクリックします。
1. オーディエンスに名前を付け、オプションで説明を追加します。
1. **[!UICONTROL Visitor Profile]** をオーディエンスビルダーペインにドラッグ&amp;ドロップします。
1. **[!UICONTROL Visitor Profile]** ドロップダウンリストから、属性を選択します。

   ![傾向スコア 1](assets/propensity_score_1.png)

1. 評価基準を選択します。

   ![傾向スコア 2](assets/propensity_score_2.png)

1. 「**[!UICONTROL Choose Comparison Type]**」ドロップダウン・リストから「**[!UICONTROL Attribute]**」を選択します。

   「静的値」比較タイプを使用すると、訪問者プロファイル属性を特定の値と比較できます。

   ![傾向スコア 3](assets/propensity_score_3.png)

   >[!NOTE]
   >
   >デフォルトの訪問者プロファイルカテゴリ（新規訪問者、再訪問者など）のいずれかを使用している場合は、静的な値オプションのみを選択できます。 動的比較オプションは、デフォルトカテゴリーでは使用できません。動的比較オプションを使用できない他の例としては、「セッションの最初のページ」、「他のテストに存在しない」、「セッションの最初のページ以外」、「カテゴリー親和性」があります。

1. 最初の属性と比較する追加属性を選択します。

   ![propensity_score_4 画像 ](assets/propensity_score_4.png)

1. **[!UICONTROL Done]** をクリックします。

## トレーニングビデオ ![ 概要バッジ ](/help/main/assets/overview.png) {#section_3BB8DBF3418F4520B3E274B6F40AF8F3}

この機能を使用できるシナリオと詳細情報については、次のビデオを視聴してください。

>[!VIDEO](https://video.tv.adobe.com/v/328272?captions=jpn)
