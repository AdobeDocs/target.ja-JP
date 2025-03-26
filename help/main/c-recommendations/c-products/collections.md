---
keywords: コレクション;ターゲット設定
description: ' [!DNL Target Recommendations] で製品または項目のコレクションを使用する方法を説明します。'
title: Recommendations アクティビティでコレクションを使用するには
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: e62f501b-3521-4456-9ea1-e4b8a2b478c6
source-git-commit: be9cb6da17f125c127d64ed8f9002987188fdf3d
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 26%

---

# コレクション

コレクションは、レコメンデーションの対象となる製品または項目のセットです。 コレクションを定義するには、そのコレクションの一部となる項目が満たす必要がある条件を指定します。

一般的に、コレクションは、単一の製品コレクションなどの同一または関連する品目のセットです。ただし、どのような品目でも、ビジネス上で適切なカテゴリにグループ化できます。例えば、ある価格帯の製品、ある地域で特に関心が高いと思われる色や品目などです。

コレクションは、製品や論理的な格納場所を整理するために使用できます。例えば、ある地域で使用できる項目があり、別の地域では使用できない項目がある場合、訪問者の地域で使用できない項目を除外するコレクションを作成できます。 また、コレクションを使用すると、季節的な品目やビジネスに適した任意の整理パラメーターによる整理をおこなえます。

レコメンデーション内の各条件に対して生成された [ バックアップのレコメンデーション ](/help/main/c-recommendations/c-algorithms/backup-recs.md) でも、このコレクションを使用するので、コレクション内の項目のみがバックアップのレコメンデーションに含まれます。 コレクションを使用すると、ある位置での表示に適切な商品だけを、確実に表示させることができます。

コレクションは、各条件が実行されるたびに、再構築または更新されます。

品目をコレクションにグループ分けし、各カタログに個別のレコメンデーションを作成できます。

包含条件を使用するとコレクションと同様のことができますが、包含条件はアクティビティを作成する都度設定する必要があります。コレクションを使用すると、一連の項目を 1 回だけ作成し、適切な場合は、もう一度設定しなくてもいつでも使用できます。

[!DNL Recommendations] アクティビティを作成または編集する場合、アクティビティ図の [!UICONTROL Criteria] ラベルの横にコレクション名が表示されます。

>[!NOTE]
>
>* コレクションルールは、条件の実行後に生成されるレコメンデーション項目に適用されます。 これらは、出力内のエンティティ Recommendations （ER）にのみ影響し、キーには影響しません。
>
>* [!UICONTROL Recently Viewed Items] レコメンデーションキーを使用する場合、コレクションは適用されません。

## コレクションの作成 {#task_1256DFF6842141FCAADD9E1428EF7F08}

コレクションを作成して、レコメンデーションに表示する製品またはコンテンツを整理します。

1. **[!UICONTROL Recommendations]**/**[!UICONTROL Collections]** をクリックして、既存のコレクションのリストを表示します。

   [!UICONTROL Collections] ページには、既存のコレクションのリストが表示されます。 新しいコレクションを作成するには、「[!UICONTROL Create Collection]」ボタンをクリックします。 また、目的のコレクションの横にある「その他のアクション」アイコン（![ その他のアクション」アイコン ](/help/main/assets/icons/MoreSmallList.svg)）をクリックしたあと目的のオプションをクリックすると、既存のコレクションを編集、コピー、削除できます。

   [!UICONTROL Collections] リスト表示の各コレクションについて報告された「項目数」は、設定されたデフォルトの Recommendations [ ホストグループ ](/help/main/administrating-target/hosts.md) （環境）内のそのコレクションのルールに一致する製品の数です。 デフォルトのホストグループを変更するには、[ 設定 ](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank} を参照してください。

1. **[!UICONTROL Create Collection]** をクリックします。

1. コレクションの **[!UICONTROL Name]** を入力します。

   また、オプションで **[!UICONTROL Description]** を入力することもできます。

1. （条件付き）コレクションを作成（または更新 ](/help/main/administrating-target/environments.md) する際に、**[!UICONTROL Environment]** フィルターから [ 環境）を選択して、その環境内のコレクションのコンテンツをプレビューします。 デフォルトでは、デフォルトのホストグループの結果が表示されます。

1. コレクションの構築に使用するルールを設定します。

   例えば、リスト内の product ID、category、margin などのパラメーターに関するコレクションを作成できます。

   ルールを追加し、複数のパラメーターを使用して、コレクションを定義することができます。複数のルールを AND 演算子で結合します。 コレクションが適用されるには、指定したすべてのルールに合致する必要があります。

1. **[!UICONTROL Create]** をクリックします。

<!-- ## Create a collection using [!UICONTROL Advanced Search]

You can also create collections using [!UICONTROL Advanced Search] on the [Catalog Search](/help/main/c-recommendations/c-products/catalog-search.md#save-as) page ([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]). 

![Save as dialog](/help/main/c-recommendations/c-products/assets/save-as.png)

After creating a search using "id > contains," for example, you can then click [!UICONTROL Save As] > [!UICONTROL Collection].

>[!IMPORTANT]
>
>The [!UICONTROL Advanced Search] functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. This mismatch might lead to confusion. Ensure that you consider case-sensitivity when you create collections based on results using the [!UICONTROL Advanced Search] functionality. For example, if you perform a search for "Holiday," that initial search lists results containing "Holiday" and "holiday." If you then create a catalog with the intent to return products containing "holiday," only products containing "holiday" are returned. Products containing "Holiday" are not returned. -->

## コレクションの編集、コピー、削除

リスト内の目的のコレクションの横にある ![ その他のアクション アイコン ](/help/main/assets/icons/MoreSmallList.svg)）をクリックし、適切なアイコン（[!UICONTROL Edit]、[!UICONTROL Copy]、[!DNL Delete]）をクリックします。

既存のコレクションをコピーして重複するコレクションを作成し、後で変更できます。 これにより、少ない労力で同様のコレクションを作成できます。

コレクションは、アカウント全体で利用できることに注意してください。 コレクションを削除する前に、このことを考慮してください。 削除したコレクションは復元できません。

## [!DNL Recommendations] アクティビティでのコレクションの使用

1. 上記のいずれかの方法を使用して、コレクションを作成します。

1. 「**[!UICONTROL Activities]**」をクリックして [ 新しい Recommendations を作成 ](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md) アクティビティを作成するか、既存のアクティビティを編集します。

1. 条件とデザインを選択すると、[!UICONTROL Options] のページが表示され、目的のコレクションを選択できます。

1. （条件付き）既存のコレクション設定を変更するには、**[!UICONTROL Experiences]** のページ（3 つのパートから成るガイド付きワークフローのステップ 1）で、レコメンデーションを配置した場所をクリックし、「**[!UICONTROL Change Collection]**」をクリックして目的のコレクションを選択します。
