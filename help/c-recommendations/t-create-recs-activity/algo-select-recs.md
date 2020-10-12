---
keywords: recommendations;recommendations activity;criteria;algorithm
description: Adobe Target Recommendations アクティビティで使用する条件を選択します。
title: 条件の選択
feature: recs creation
uuid: 1a1e13e0-7fbd-4f86-80da-cd4e96748d30
translation-type: tm+mt
source-git-commit: 8ae2bf479a9b53693f830515aee55573987bb05b
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 82%

---


# ![PREMIUM](/help/assets/premium.png) 条件を選択{#select-criteria}

 アクティビティで使用する[条件](/help/c-recommendations/c-algorithms/algorithms.md)を選択します。[!DNL Adobe Target Recommendations]条件とは、事前に定義されている訪問者の行動に基づいて、どの商品をレコメンデーションするかを決定するルールです。

複数の条件を追加することで複数のレコメンデーションタイプを相互にテストすることができます。

複数の条件を選択すると、トラフィックは選択した条件間で等しく分割されます。例えば、2 つの条件が選択されており、アクティビティ参加者の 20％にデフォルトコンテンツを表示するようにアクティビティがデザインされている場合、各条件によって制御されるレコメンデーションがアクティビティ参加者の 40％に表示されます。各条件の割合を変更するオプションはありません。

* 既存の条件を検索（例えば、多くの条件カードが表示されている場合）するには、必要な条件が表示されるまで検索フィールドに入力し、条件を選択して「**[!UICONTROL 完了]**」をクリックします。

   [!DNL Recommendations] によって提供される条件もあります。カスタムの条件を作成することも可能です。

* To create a new criteria, click **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**, then fill in the information for the new criteria. 新しい条件の作成について詳しくは、[新しい条件を作成](../../c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE)を参照してください。

**条件を選択するには：**

1. While [creating a new recommendation](../../c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F), in the **[!UICONTROL Select Criteria]** dialog box, locate and select one or more criteria.

   ![条件を選択ダイアログボックス](/help/c-recommendations/t-create-recs-activity/assets/filters.png)

   [!UICONTROL 業種] フィルター、[!UICONTROL ページタイプ]フィルターおよび「[!UICONTROL 互換性]」チェックボックスを使用して、条件のリストをフィルターできます。これらのオプションは、目的の条件を探すのに役立ちます。

   * **業種：**&#x200B;業種は、[!DNL Recommendations] 条件の分類に使用されます。To change your default industry vertical, click **[!UICONTROL Recommendations]** > **[!UICONTROL Settings]** and select your desired default **[!UICONTROL Industry Vertical]** setting.
   * **ページタイプ：**&#x200B;ページタイプによって、レコメンデーションが分類しやすくなります。それぞれのページタイプで選択できるビルトイン条件もあります。
   * **互換性：**&#x200B;選択されたページが必要なデータを渡す条件のみが表示されます。すべてのページですべての条件が正しく実行されるわけではありません。現在の品目／現在のカテゴリのレコメンデーションと互換性を持たせるために、ページや mbox には `entity.id` か `entity.categoryId` を渡す必要があります。通常は、互換性のある条件のみを表示するようにします。ただし、アクティビティで互換性のない条件を有効にしたい場合は、「**[!UICONTROL 互換性あり]**」チェックボックスのチェックを外します。This option can be disabled or enabled in your settings: **[!UICONTROL Recommendations]** > **[!UICONTROL Settings]**.

1. 「**[!UICONTROL 次へ]**」をクリックして、[デザインを選択](/help/c-recommendations/c-design-overview/design-overview.md)ダイアログボックスを表示します。
