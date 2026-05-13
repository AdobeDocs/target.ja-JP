---
keywords: コレクション;ターゲティング
description: ' [!DNL Target Recommendations]の製品またはアイテムのコレクションを使用する方法を説明します。'
title: レコメンデーションアクティビティでコレクションを使用するにはどうすればよいですか？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: e62f501b-3521-4456-9ea1-e4b8a2b478c6
TQID: https://experienceleague.adobe.com/kdjl2cpjaRWYZRqHFqARHvbTaTuu0iAH7ZWbD2Lrs7o
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 16fb7a1902ea76cab56a93fa141a32a3c6bc4467
workflow-type: tm+mt
source-wordcount: 732
ht-degree: 31%

---

# コレクション

コレクションは、レコメンデーションに使用できる商品または品目のセットです。 コレクションは、そのコレクションに含まれるアイテムが満たす必要がある条件を指定することによって定義されます。

一般的に、コレクションは、単一の製品コレクションなどの同一または関連する品目のセットです。 ただし、特定の価格帯や色の商品、特定の地域で関心を示す可能性の高い商品など、ビジネスにとって意味のあるカテゴリーに分類することは可能です。

コレクションは、製品や論理的な格納場所を整理するために使用できます。 例えば、ある地域で利用可能なアイテムが別の地域では利用できないアイテムがある場合、訪問者の地域で利用できないアイテムを除外するコレクションを作成できます。 また、コレクションを使用すると、季節的な品目やビジネスに適した任意の整理パラメーターによる整理をおこなえます。

レコメンデーション内の各条件に対して生成された[&#x200B; バックアップ レコメンデーション &#x200B;](/help/main/c-recommendations/c-algorithms/backup-recs.md)もこのコレクションを使用するため、コレクション内のアイテムのみがバックアップ レコメンデーションに含まれます。 コレクションを使用すると、ある位置での表示に適切な商品だけを、確実に表示させることができます。

コレクションは、各条件が実行されるたびに、再構築または更新されます。

品目をコレクションにグループ分けし、各カタログに個別のレコメンデーションを作成できます。

包含条件を使用するとコレクションと同様のことができますが、包含条件はアクティビティを作成する都度設定する必要があります。 コレクションを利用すれば、一度に複数のアイテムを作成し、再び設定することなく、適切なときにいつでも使用できます。

[!DNL Recommendations] アクティビティを作成または編集する際に、アクティビティ ダイアグラムの[!UICONTROL Criteria] ラベルの横にコレクション名が表示されます。

>[!NOTE]
>
>* コレクションのルールは、条件の実行後に生成されたレコメンデーション項目に適用されます。 これらは、キーではなく、出力内のエンティティ推奨（ER）のみに影響します。
>
>* [!UICONTROL Recently Viewed Items] レコメンデーションキーを使用する場合、コレクションは適用されません。

## コレクションの作成 {#task_1256DFF6842141FCAADD9E1428EF7F08}

レコメンデーションに表示する商品やコンテンツを整理するためのコレクションを作成します。

1. **[!UICONTROL Recommendations]** > **[!UICONTROL Collections]**&#x200B;をクリックして、既存のコレクションのリストを表示します。

   [!UICONTROL Collections] ページには、既存のコレクションのリストが表示されます。 [!UICONTROL Create Collection] ボタンをクリックして、新しいコレクションを作成します。 また、目的のコレクションの横にあるその他のアクション アイコン（![その他のアクション アイコン &#x200B;](/help/main/assets/icons/MoreSmallList.svg)）をクリックし、目的のオプションをクリックして、既存のコレクションを編集、コピー、削除することもできます。

   [!UICONTROL Collections] リストビューの各コレクションについて報告された「アイテム数」は、設定されたデフォルトのRecommendations [&#x200B; ホストグループ &#x200B;](/help/main/administrating-target/hosts.md) （環境）内の、そのコレクションのルールに一致する製品の数です。 デフォルトのホストグループを変更するには、[設定](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html?lang=ja){target=_blank}を参照してください。

1. **[!UICONTROL Create Collection]** をクリックします。

1. コレクションの&#x200B;**[!UICONTROL Name]**&#x200B;を入力します。

   オプションの&#x200B;**[!UICONTROL Description]**&#x200B;を入力することもできます。

1. （条件付き）コレクションを作成（または更新）中に&#x200B;**[!UICONTROL Environment]** フィルターから[環境](/help/main/administrating-target/environments.md)を選択すると、その環境のコレクションの内容がプレビューされます。 デフォルトでは、デフォルトのホストグループの結果が表示されます。

1. コレクションの構築に使用するルールを設定します。

   例えば、リスト内の product ID、category、margin などのパラメーターに関するコレクションを作成できます。

   ルールを追加し、複数のパラメーターを使用して、コレクションを定義することができます。 複数のルールをAND演算子で結合します。 コレクションが適用されるには、指定したすべてのルールに合致する必要があります。

1. **[!UICONTROL Create]** をクリックします。

<!--
## Create a collection using [!UICONTROL Advanced Search]

You can also create collections using [!UICONTROL Advanced Search] on the [Catalog Search](/help/main/c-recommendations/c-products/catalog-search.md#save-as) page ([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]). 

![Save as dialog](/help/main/c-recommendations/c-products/assets/save-as.png)

After creating a search using "id > contains," for example, you can then click [!UICONTROL Save As] > [!UICONTROL Collection].

>[!IMPORTANT]
>
>The [!UICONTROL Advanced Search] functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. This mismatch might lead to confusion. Ensure that you consider case-sensitivity when you create collections based on results using the [!UICONTROL Advanced Search] functionality. For example, if you perform a search for "Holiday," that initial search lists results containing "Holiday" and "holiday." If you then create a catalog with the intent to return products containing "holiday," only products containing "holiday" are returned. Products containing "Holiday" are not returned.
-->

## コレクションの編集、コピー、削除

リスト内の目的のコレクションの横にある（![その他のアクション アイコン &#x200B;](/help/main/assets/icons/MoreSmallList.svg)）をクリックし、適切なアイコン（[!UICONTROL Edit]、[!UICONTROL Copy]、または[!DNL Delete]）をクリックします。

既存のコレクションをコピーして重複したコレクションを作成し、それを変更できます。 これにより、より少ない労力で同様のコレクションを作成できます。

コレクションはアカウント全体で利用できます。 コレクションを削除する前に、この点を考慮してください。 削除したコレクションは復元できません。

## [!DNL Recommendations] アクティビティでのコレクションの使用

1. 上記のいずれかの方法を使用して、コレクションを作成します。

1. **[!UICONTROL Activities]**&#x200B;と[をクリックして、新しいRecommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md) アクティビティを作成するか、既存のアクティビティを編集します。

1. 条件とデザインを選択すると、[!UICONTROL Options] ページが表示され、目的のコレクションを選択できます。

1. （条件付き）既存のコレクション設定を変更するには、**[!UICONTROL Experiences]** ページ（3つの部分のガイド付きワークフローの手順1）で、レコメンデーションを配置した場所をクリックし、**[!UICONTROL Change Collection]**&#x200B;をクリックしてから、目的のコレクションを選択します。
