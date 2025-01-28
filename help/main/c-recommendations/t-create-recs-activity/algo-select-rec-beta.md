---
keywords: recommendations;recommendations アクティビティ；条件；アルゴリズム
description: Adobe [!DNL Target] Recommendations アクティビティで使用する条件（推奨する製品やコンテンツを決定するルール）を選択する方法を説明します。
title: Recommendations アクティビティの条件を選択するには
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
hide: true
hidefromtoc: true
source-git-commit: b7c7e8d85f7f39024ed5e57177e5c9f628460e9c
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 57%

---

# 条件の選択

[!DNL Adobe Target Recommendations] アクティビティで使用する [ 条件 ](/help/main/c-recommendations/c-algorithms/algorithms.md) を選択します。 条件とは、事前に定義されている訪問者の行動に基づいて、どの商品をレコメンデーションするかを決定するルールです。

複数の条件を追加することで複数のレコメンデーションタイプを相互にテストすることができます。

複数の条件を選択すると、トラフィックは選択した条件間で等しく分割されます。例えば、2 つの条件が選択されており、アクティビティ参加者の 20％にデフォルトコンテンツを表示するようにアクティビティがデザインされている場合、各条件によって制御されるレコメンデーションがアクティビティ参加者の 40％に表示されます。各条件の割合を変更するオプションはありません。

* 既存の条件（条件カードが多数表示される場合など）を検索するには、目的の条件が表示されるまで検索フィールドに入力し、条件を選択して「検 **[!UICONTROL Done]**」をクリックします。

  [!DNL Recommendations] によって提供される条件もあります。カスタムの条件を作成することも可能です。

* 新しい条件を作成するには、**[!UICONTROL Create Criteria]**/**[!UICONTROL Create Criteria]** をクリックし、新しい条件の情報を入力します。 新しい条件の作成について詳しくは、[新しい条件を作成](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE)を参照してください。

**条件を選択するには：**

1. [ 新しいレコメンデーションの作成 ](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F) 中に、**[!UICONTROL Select Criteria]** ダイアログボックスで 1 つ以上の条件を見つけて選択します。

   [!UICONTROL Industry Type] フィルター、[!UICONTROL Page Type] フィルター、および [!UICONTROL Compatible] チェックボックスを使用して、条件のリストをフィルタリングできます。 これらのオプションは、目的の条件を探すのに役立ちます。

   * **業種：**&#x200B;業種は、[!DNL Recommendations] 条件の分類に使用されます。デフォルトの業種を変更するには、**[!UICONTROL Recommendations]**/**[!UICONTROL Settings]** をクリックし、目的のデフォルトの **[!UICONTROL Industry Vertical]** 設定を選択します。
   * **ページタイプ：**&#x200B;ページタイプによって、レコメンデーションが分類しやすくなります。それぞれのページタイプで選択できるビルトイン条件もあります。
   * **互換性：**&#x200B;選択されたページが必要なデータを渡す条件のみが表示されます。すべてのページですべての条件が正しく実行されるわけではありません。現在の品目／現在のカテゴリのレコメンデーションと互換性を持たせるために、ページや mbox には `entity.id` か `entity.categoryId` を渡す必要があります。通常は、互換性のある条件のみを表示するようにします。ただし、互換性のない条件をアクティビティで使用できるようにする場合は、「**[!UICONTROL Compatible]**」チェックボックスをオフにします。 このオプションは、設定（**[!UICONTROL Recommendations]**/**[!UICONTROL Settings]**）で無効または有効にすることができます。

1. 「**[!UICONTROL Next]**」をクリックして [ 「デザインを選択 ](/help/main/c-recommendations/c-design-overview/design-overview.md)」ダイアログボックスを表示します。
