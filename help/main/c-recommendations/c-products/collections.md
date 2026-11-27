---
keywords: コレクション;ターゲティング
description: '[!DNL Target Recommendations]の製品またはアイテムのコレクションを使用する方法を説明します。'
title: レコメンデーションアクティビティでコレクションを使用するにはどうすればよいですか？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: e62f501b-3521-4456-9ea1-e4b8a2b478c6
TQID: 'https://experienceleague.adobe.com/kdjl2cpjaRWYZRqHFqARHvbTaTuu0iAH7ZWbD2Lrs7o'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 11%
---
# コレクション {#collections}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、[!DNL Adobe Target Recommendations]のアイテムのコレクションを作成、管理、使用する方法について説明します。

>[!ENDSHADEBOX]

コレクションは、レコメンデーションに使用できる商品または品目のセットです。 コレクションは、アイテムがそのコレクションに含まれるために満たす必要がある条件によって定義されます。 類似商品や関連商品、特定の価格帯や色の商品、特定の地理的地域で関心を示す可能性の高い商品など、ビジネスにとって意味のある方法で分類することができます。

コレクションで商品を論理バケットに整理します。 例えば、ある地域で利用可能なアイテムが存在するが、別の地域で利用可能でないアイテムがある場合、コレクションは訪問者の地域で利用できないアイテムを除外できます。 コレクションは、季節商品や、ビジネスに適用されるその他の組織的パラメーターを整理することもできます。 アイテムはカタログに分類し、各コレクションに対して個別のレコメンデーションを作成できます。

次の点は、コレクションが[!DNL Recommendations]の残りの部分とどのように相互作用するかを示しています。

* 各条件に対して生成された[&#x200B; バックアップ レコメンデーション &#x200B;](/help/main/c-recommendations/c-algorithms/backup-recs.md)もコレクションを使用するため、コレクション内のアイテムのみがバックアップ レコメンデーションに含まれます。 その結果、場所にとって意味のある製品のみが表示されます。
* コレクションは、各条件が実行されるたびに、再構築または更新されます。
* コレクションのルールは、条件の実行後に生成されたレコメンデーション項目に適用されます。 これらは、キーではなく、出力内のエンティティ推奨（ER）のみに影響します。
* **[!UICONTROL 最近閲覧したアイテム]**&#x200B;のレコメンデーションキーを使用する場合、コレクションは適用されません。
* 包含基準は、同様の結果を生成できますが、アクティビティが作成されるたびに設定する必要があります。 コレクションは1回作成され、再度設定しなくても再利用できます。
* [!DNL Recommendations] アクティビティを作成または編集すると、アクティビティ ダイアグラムの&#x200B;**[!UICONTROL 条件]** ラベルの横にコレクション名が表示されます。

## コレクションの作成 {#task_1256DFF6842141FCAADD9E1428EF7F08}

コレクションはアカウント全体で利用できるため、一度作成したコレクションは、任意の[!DNL Recommendations] アクティビティで選択できます。 ルールはコレクションで定義されるので、各アクティビティに対して再び設定する必要はありません。

1. **[!UICONTROL Recommendations]** > **[!UICONTROL コレクション]**&#x200B;をクリックして、既存のコレクションのリストを表示します。

   既存のコレクションを編集、コピー、または削除するには、コレクションの横にあるその他のアクション アイコン（![その他のアクション アイコン &#x200B;](/help/main/assets/icons/MoreSmallList.svg)）をクリックし、目的のオプションをクリックします。

   >[!NOTE]
   >
   >**[!UICONTROL コレクション]** リストビューの各コレクションについて報告された「アイテム数」は、設定されたデフォルトのRecommendations [&#x200B; ホストグループ &#x200B;](/help/main/administrating-target/hosts.md) （環境）内の、そのコレクションのルールに一致する製品の数です。 デフォルトのホストグループを変更するには、[設定](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html?lang=ja){target=_blank}を参照してください。

1. 「**[!UICONTROL コレクションを作成]**」をクリックします。

   コレクションを作成ボタンを含む![&#x200B; コレクションページ &#x200B;](../assets/collection_1.png)

1. コレクションの&#x200B;**[!UICONTROL 名前]**&#x200B;を入力します。 オプションの&#x200B;**[!UICONTROL 説明]**&#x200B;も入力できます。

1. （条件付き） **[!UICONTROL 環境]** フィルターから[環境](/help/main/administrating-target/environments.md)を選択して、その環境内のコレクションの内容をプレビューします。 デフォルトでは、デフォルトのホストグループの結果が表示されます。

1. コレクションの構築に使用するルールを設定します。

   コレクションは、製品ID、カテゴリ、マージン、またはリスト内の他のパラメーターを中心に構築できます。 複数のパラメーターを使用してコレクションを定義するルールを追加します。 複数のルールはAND演算子で結合されるため、コレクションを適用するには、指定したすべてのルールを一致させる必要があります。

1. 「**[!UICONTROL 作成]**」をクリックします。

1. コレクションを作成したら、その他のアクション アイコン（![その他のアクション アイコン &#x200B;](/help/main/assets/icons/MoreSmallList.svg)）をクリックし、適切なオプション（**[!UICONTROL 編集]**、**[!UICONTROL コピー]**、または&#x200B;**[!UICONTROL 削除]**）を選択します。

   ![その他のアクション メニューを開いたコレクション リストで、編集、コピー、削除を表示](../assets/collection_2.png)

<!--
## Create a collection using [!UICONTROL Advanced Search]

You can also create collections using [!UICONTROL Advanced Search] on the [Catalog Search](/help/main/c-recommendations/c-products/catalog-search.md#save-as) page ([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]). 

![Save as dialog](/help/main/c-recommendations/c-products/assets/save-as.png)

After creating a search using "id > contains," for example, you can then click [!UICONTROL Save As] > [!UICONTROL Collection].

>[!IMPORTANT]
>
>The [!UICONTROL Advanced Search] functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. This mismatch might lead to confusion. Ensure that you consider case-sensitivity when you create collections based on results using the [!UICONTROL Advanced Search] functionality. For example, if you perform a search for "Holiday," that initial search lists results containing "Holiday" and "holiday." If you then create a catalog with the intent to return products containing "holiday," only products containing "holiday" are returned. Products containing "Holiday" are not returned.
-->

## アクティビティでのコレクションの使用 {#use-collection}

コレクションは、[!DNL Recommendations] アクティビティの各エクスペリエンスに対して選択されます。 コレクションは、そのエクスペリエンスのレコメンデーションに表示できるアイテムを決定します。

1. [&#x200B; コレクションを作成](#task_1256DFF6842141FCAADD9E1428EF7F08)。

   ![&#x200B; コレクションの詳細とルールのセクションを含むコレクション画面を作成](../assets/collection_3.png)

1. **[!UICONTROL アクティビティ]**&#x200B;と[をクリックして、新しいRecommendations アクティビティ &#x200B;](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md)を作成するか、既存のアクティビティを編集します。

   ![&#x200B; アクティビティを作成メニューでレコメンデーションを選択した全アクティビティページ &#x200B;](../assets/collection_4.png)

1. 条件とデザインを選択したら、**[!UICONTROL オプション]** ページで目的のコレクションを選択します。

1. （条件付き）既存のアクティビティのコレクションを変更するには、**[!UICONTROL エクスペリエンス]** ページのレコメンデーションの場所をクリックし、**[!UICONTROL コレクションの変更]**&#x200B;をクリックしてから、目的のコレクションを選択します。
