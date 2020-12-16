---
keywords: promotions;front promotions;back promotions;promotions type
description: プロモーション項目を追加して、Adobe Target Recommendations デザインでの配置を制御します。静的なプロモーションおよび動的なプロモーションを追加できます。
title: Adobe Target Recommendations デザインにプロモーションを追加します。
feature: recs creation
translation-type: tm+mt
source-git-commit: e07a457339509d1019cdd241ef3adfbb17ffafaa
workflow-type: tm+mt
source-wordcount: '679'
ht-degree: 60%

---


# ![PREMIUM](/help/assets/premium.png) プロモーションの追加

プロモーション項目を追加して、Recommendations デザインでの配置を制御します。静的なプロモーションおよび動的なプロモーションを追加できます。

>[!IMPORTANT]
>
>静的および動的な除外ルールは、マーケティングに役立つ便利な機能です。詳細な情報、例、および使用例については、[動的および静的インクルージョンルールの使用](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F)を参照してください。

[!DNL Recommendations] アクティビティを作成するときは、[!DNL Recommendations] デザインにプロモーション項目を含めることができます。プロモーションは、デザインの使用可能なスロットを使用し、条件の結果およびバックアップレコメンデーションよりも優先されます。例えば、デザインに 6 つのスロットがあり、そのうち 2 つをプロモーションに使用した場合、条件に基づいてレコメンデーションされる項目に 4 つのスロットを使用できます。

プロモーションは、アクティビティの条件で推奨された項目に対して重複排除されるので、特定の項目が 1 つのレコメンデーショントレイに 2 回表示されることはありません。

特定の項目をプロモーションしたり、動的に項目をプロモーションしたり、属性に基づいて項目をプロモーションすることができます。また、コレクションをプロモーションすることもできます。

![](assets/add_promotion_toggles.png)

>[!NOTE]
>
>プロモーションを使用すると、CSV の構造と出力が変更されます。この変更により、電子メールなど、CSV に関連する外部プロセスが影響を受ける可能性があります。

1. **[!UICONTROL オプション]**&#x200B;ページで、「**[!UICONTROL プロモーション - 前]**」または「**[!UICONTROL プロモーション - 後]**」をクリックします。

   以下の図に、「[!UICONTROL プロモーション - 前]」が「オン」の状態を示します。

   ![「プロモーション - 前」オプションを追加](/help/c-recommendations/t-create-recs-activity/assets/add_promotion_front.png)

   条件の結果の前と&#x200B;**&#x200B;後のどちらにもプロモーションを挿入できます。
1. プロモーション項目に使用するデザインスロットの数を設定します。

   [!DNL Recommendations] デザインによりますが、最大で 20 個のスロットを使用できます。使用した各スロットは、条件に基づいて返されたレコメンデーションには使用できません。

1. プロモーション項目の開始日と終了日を設定します。

   開始日を設定しない場合、プロモーションはすぐに開始されます。終了日を設定しない場合、プロモーションは無期限に実行されます。

1. 「**[!UICONTROL プロモーションタイプ]**」を選択します。

   * 「**[!UICONTROL 項目のリスト]**」を選択し、プロモーションする特定の項目の `entity.id` 値をコンマで区切って入力します。

   * 「**[!UICONTROL 属性別にプロモート]**」を選択し、プロモーションする項目の属性を定義するルールを追加します。

      「属性別にプロモート」を選択すると、動的な一致を作成できます。詳しくは、[動的および静的インクルージョンルールの使用](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F)を参照してください。

   * 「**[!UICONTROL コレクションをプロモート]**」を選択し、プロモーションする項目のコレクションを選択します。

      プロモーションに使用する新しいコレクションを作成できます。詳しくは、[コレクションの作成](/help/c-recommendations/c-products/collections.md#task_1256DFF6842141FCAADD9E1428EF7F08)を参照してください。
   「プ **[!UICONTROL ロモーションタイプ]** 」に「品目 **[!UICONTROL リスト]**」を選択した場合は、必要に応じて「品目順序の **[!UICONTROL ランダム化]** 」チェックボックスをオンにします。

   項目 [!UICONTROL リストのデフォルトの並べ替え順は] 、ターゲットのUIまたはAPIで入力した順序に基づきます。

   If your list includes more items than the number of slots you set for promotions, the [!UICONTROL Randomize Item Order] option randomizes the promoted items that are displayed in your design. Choosing this option results in [!DNL Target] randomly selecting the items enabled for promotions in the template from the entire promotion set on each hit.

   エンティティに属性がない場合（製品を販売しない場合など）は、 `entity.value``entity.value` 属性に数値（発行日など）を渡すことができます。 この場合、最新の投稿日に基づいて、プロモーションされた項目を降順でプロモーションできます。 属性は `entity.value` 重複型です。文字列は受け付けません。

   「属性 [!UICONTROL 別に] プロモート」または「コレクションをプロモート」オプションを選択した場合、順序をランダム化するオプションは使用できません  。

   「属性別に [!UICONTROL プロモート」または「コレクションをプロモート」] (Promote by Attribute [!UICONTROL )オプションを使用して特定の項目をプロモートする場合、項目が表示されるデフォルトの順序は、]`entity.value` 属性に基づき、数値の降順です。

   次の表に、これらのオプションの違いを示します。

   | プロモーションタイプ | デフォルトの並べ替え | バックアップの並べ替え | 動的フィルタリングオプション |
   | --- | --- | --- | --- |
   | 項目のリスト | ターゲットUI/APIに入力された注文 | ランダム（UI/APIで選択された場合） | × |
   | 属性別にプロモート | entity.value（降順） | リクエストごとにランダム化（entity.value属性が存在しない場合） | × |
   | コレクションの更新 | entity.value（降順） | リクエストごとにランダム化（entity.value属性が存在しない場合） | × |

1. Click **[!UICONTROL Save.]**.

プロモーションはアクティビティのすべてのエクスペリエンスに適用されます。
