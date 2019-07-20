---
description: Recommendations アクティビティで使用する条件を選択します。
keywords: レコメンデーション;レコメンデーションアクティビティ;条件
seo-description: Adobe Target Recommendationsアクティビティで使用する条件を選択します。
seo-title: 条件の選択
solution: 'Target '
title: 条件の選択
title-outputclass: premium
topic: Premium
uuid: 1a1e13e0-7fbd-4f86-80da-cd4e96748d30
badge: premium
translation-type: tm+mt
source-git-commit: e8e6dcadf307209abcc712798b714af0a5be2e7e

---


# ![PREMIUM](/help/assets/premium.png) 条件を選択{#select-criteria}

Select the [criteria](/help/c-recommendations/c-algorithms/algorithms.md) to use in your Recommendations activity. 条件とは、事前に定義されている訪問者の行動に基づいて、どの商品をレコメンデーションするかを決定するルールです。

複数の条件を追加することで複数のレコメンデーションタイプを相互にテストすることができます。

複数の条件を選択すると、トラフィックは選択した条件間で等しく分割されます。例えば、2 つの条件が選択されており、アクティビティ参加者の 20％にデフォルトコンテンツを表示するようにアクティビティがデザインされている場合、各条件によって制御されるレコメンデーションがアクティビティ参加者の 40％に表示されます。各条件の割合を変更するオプションはありません。

* 既存の条件を検索（例えば、多くの条件カードが表示されている場合）するには、必要な条件が表示されるまで検索フィールドに入力し、条件を選択して「**[!UICONTROL 完了]**」をクリックします。

   [!DNL Recommendations] によって提供される条件もあります。カスタムの条件を作成することも可能です。

* To create a new criteria, click **[!UICONTROL Create Criteria]**, then fill in the information for the new criteria. 新しい条件の作成について詳しくは、[新しい条件を作成](../../c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE)を参照してください。

**条件を選択するには:**

1. While [creating a new recommendation](../../c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F), in the **[!UICONTROL Criteria]** dialog box, locate and select one or more criteria.

   ![条件の選択ダイアログボックス](/help/c-recommendations/t-create-recs-activity/assets/filters.png)

   [!UICONTROL 「業種»?フィルター、?«ページタイプ?»フィルターおよび?«互換性]これらのオプションは、目的の条件を見つけるのに役立ちます。

   * **業種：**&#x200B;業種は、[!DNL Recommendations] 条件の分類に使用されます。デフォルトの業種を変更するには、「**[!UICONTROL 設定]**」をクリックし、目的のデフォルト&#x200B;**業種]設定を選択します。[!UICONTROL **
   * **ページタイプ：**&#x200B;ページタイプによって、レコメンデーションが分類しやすくなります。それぞれのページタイプで選択できるビルトイン条件もあります。
   * **互換性：**&#x200B;選択されたページが必要なデータを渡す条件のみが表示されます。すべてのページですべての条件が正しく実行されるわけではありません。現在の品目／現在のカテゴリのレコメンデーションと互換性を持たせるために、ページや mbox には `entity.id` か `entity.categoryId` を渡す必要があります。通常は、互換性のある条件のみを表示するようにします。ただし、アクティビティで互換性のない条件を有効にしたい場合は、「**[!UICONTROL 互換性あり]」チェックボックスのチェックを外します。**&#x200B;このオプションは、[!DNL Target][!UICONTROL  の環境設定]で有効と無効を切り替えることができます。

1. **[!UICONTROL 「次へ」]** をクリックして、デザイン [を選択](/help/c-recommendations/c-design-overview/design-overview.md) ダイアログボックスを表示します。
