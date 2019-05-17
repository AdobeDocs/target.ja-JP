---
description: Recommendations アクティビティで使用する条件を選択します。
keywords: レコメンデーション;レコメンデーションアクティビティ;条件
seo-description: Recommendations アクティビティで使用する条件を選択します。
seo-title: 条件の選択
solution: 'Target '
title: 条件の選択
title-outputclass: premium
topic: Premium
uuid: 1a1e13e0-7fbd-4f86-80da-cd4e96748d30
badge: premium
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# ![PREMIUM](/help/assets/premium.png) 条件を選択{#select-criteria}

Recommendations アクティビティで使用する条件を選択します。

複数の条件を追加することで複数のレコメンデーションタイプを相互にテストすることができます。

複数の条件を選択すると、トラフィックは選択した条件間で等しく分割されます。例えば、2 つの条件が選択されており、アクティビティ参加者の 20％にデフォルトコンテンツを表示するようにアクティビティがデザインされている場合、各条件によって制御されるレコメンデーションがアクティビティ参加者の 40％に表示されます。各条件の割合を変更するオプションはありません。

* 既存の条件を検索（例えば、多くの条件カードが表示されている場合）するには、必要な条件が表示されるまで検索フィールドに入力し、条件を選択して「**[!UICONTROL 完了]**」をクリックします。

   [!DNL Recommendations] によって提供される条件もあります。カスタムの条件を作成することも可能です。

* 新しい条件を作成するには、「**[!UICONTROL 新規作成]**」をクリックして新しい条件についての情報を入力します。新しい条件の作成について詳しくは、[新しい条件を作成](../../c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE)を参照してください。

1. [新規レコメンデーションを作成](../../c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)するか、設定したい条件を持つレコメンデーションを探し、「**[!UICONTROL 編集]**」をクリックします。
1. 業種とページタイプを選択します。

* **業種：**業種は、[!DNL Recommendations] 条件の分類に使用されます。デフォルトの業種を変更するには、「**[!UICONTROL 設定]**」をクリックし、目的のデフォルト**業種]設定を選択します。[!UICONTROL **
* **ページタイプ：**ページタイプによって、レコメンデーションが分類しやすくなります。それぞれのページタイプで選択できるビルトイン条件もあります。
* **互換性：**選択されたページが必要なデータを渡す条件のみが表示されます。すべてのページですべての条件が正しく実行されるわけではありません。現在の品目／現在のカテゴリのレコメンデーションと互換性を持たせるために、ページや mbox には `entity.id` か [!DNL entity.categoryId] を渡す必要があります。通常は、互換性のある条件のみを表示するようにします。ただし、アクティビティで互換性のない条件を有効にしたい場合は、「**[!UICONTROL 互換性あり]」チェックボックスのチェックを外します。**このオプションは、[!DNL Target][!UICONTROL  の環境設定]で有効と無効を切り替えることができます。

1. 「**[!UICONTROL 追加]**」をクリックします。
