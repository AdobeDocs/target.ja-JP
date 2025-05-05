---
keywords: コレクション;ターゲット設定
description: ' [!DNL Target Recommendations] で製品または項目のコレクションを使用する方法を説明します。'
title: Recommendations アクティビティでコレクションを使用する方法
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: e62f501b-3521-4456-9ea1-e4b8a2b478c6
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 41%

---

# コレクション

コレクションは、レコメンデーションの対象となる製品または項目のセットです。 コレクションを定義するには、そのコレクションの一部となる項目が満たす必要がある条件を指定します。

一般的に、コレクションは、単一の製品コレクションなどの同一または関連する品目のセットです。ただし、どのような品目でも、ビジネス上で適切なカテゴリにグループ化できます。例えば、ある価格帯の製品、ある地域で特に関心が高いと思われる色や品目などです。

コレクションは、製品や論理的な格納場所を整理するために使用できます。例えば、ある地域で使用できる項目があり、別の地域では使用できない項目がある場合、訪問者の地域で使用できない項目を除外するコレクションを作成できます。 また、コレクションを使用すると、季節的な品目やビジネスに適した任意の整理パラメーターによる整理をおこなえます。

レコメンデーション内の各条件に対して生成される[代替レコメンデーション](/help/main/c-recommendations/c-algorithms/backup-recs.md)でもこのコレクションが使用されるので、コレクション内の品目だけが代替レコメンデーションに含まれます。コレクションを使用すると、ある位置での表示に適切な商品だけを、確実に表示させることができます。

コレクションは、各条件が実行されるたびに、再構築または更新されます。

品目をコレクションにグループ分けし、各カタログに個別のレコメンデーションを作成できます。

包含条件を使用するとコレクションと同様のことができますが、包含条件はアクティビティを作成する都度設定する必要があります。コレクションを使用すると、品目のセットを一度で作成でき、再度設定する必要なく使用したいときに使用できます。

[!DNL Recommendations] アクティビティを作成または編集する場合、アクティビティ図の [!UICONTROL Criteria] ラベルの横にコレクション名が表示されます。

>[!NOTE]
>
>[!UICONTROL Recently Viewed Items] レコメンデーションキーを使用する場合、コレクションは適用されません。

## コレクションの作成 {#task_1256DFF6842141FCAADD9E1428EF7F08}

コレクションを作成して、レコメンデーションに表示する製品またはコンテンツを整理します。

1. **[!UICONTROL Recommendations]**/**[!UICONTROL Collections]** をクリックして、既存のコレクションのリストを表示します。

   ![コレクションリスト](assets/collections_list.png)

   [!UICONTROL Collections] ページには、既存のコレクションのリストが表示されます。 新しいコレクションを作成するには、「[!UICONTROL Create Collection]」ボタンをクリックします。 目的のコレクションにカーソルを合わせて目的のアイコンをクリックして、既存のコレクションを編集、コピーおよび削除することもできます。

   ![ ホバーアイコン：編集、コピー、削除 ](/help/main/c-recommendations/c-products/assets/hover-icons.png)

   [!UICONTROL Collections] のリスト表示で各コレクションに対して報告される「Number of Items」は、設定されたデフォルトのRecommendations [host group](/help/main/administrating-target/hosts.md) （environment）内でそのコレクションのルールに一致する商品の数です。 デフォルトのホストグループを変更するには、[ 設定 ](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html?lang=ja){target=_blank} を参照してください。

1. **[!UICONTROL Create Collection]** をクリックします。

1. （条件付き）コレクションを作成（または更新）する際に、**[!UICONTROL Environment]** フィルターから環境を選択して、その環境内のコレクションのコンテンツをプレビューします。 デフォルトでは、デフォルトのホストグループの結果が表示されます。

   ![コレクションの作成](/help/main/c-recommendations/c-products/assets/CreateCollection.png)

1. コレクションの **[!UICONTROL Name]** を入力します。

   また、オプションで **[!UICONTROL Description]** を入力することもできます。

1. コレクションの構築に使用するルールを設定します。

   例えば、リスト内の product ID、category、margin などのパラメーターに関するコレクションを作成できます。

   ルールを追加し、複数のパラメーターを使用して、コレクションを定義することができます。複数のルールを AND 演算子で結合します。 コレクションが適用されるには、指定したすべてのルールに合致する必要があります。

1. **[!UICONTROL Save]** をクリックします。

## 詳細検索を使用したコレクションの作成

[ カタログ検索 ](/help/main/c-recommendations/c-products/catalog-search.md#save-as) ページ（[!UICONTROL Recommendations]/[!UICONTROL Catalog Search]/[!UICONTROL Advanced Search]）の詳細検索を使用して、コレクションを作成することもできます。

![ 名前を付けて保存ダイアログ ](/help/main/c-recommendations/c-products/assets/save-as.png)

例えば、「id > 次を含む」を使用して検索を作成したら、[!UICONTROL Save As] > [!UICONTROL Collection] をクリックできます。

>[!IMPORTANT]
>
>詳細検索機能では大文字と小文字は区別されません。ただし、配信時に返される商品は、大文字と小文字が区別される検索に基づきます。この違いが混乱を招くこともあります。詳細検索機能による結果を基にしてコレクションを作成する際は、大文字と小文字の区別を考慮してください。例えば、最初に「Holiday」と検索すると、「Holiday」または「holiday」を含む結果が返されます。その後、「holiday」を含む商品を返すことを目的としたカタログを作成すると、「holiday」を含む商品のみが返されます。「Holiday」を含む商品は返されません。

## コレクションの編集、コピー、削除

リスト内の目的のコレクションにポインタを合わせ、適切なアイコン（編集、コピー、削除）をクリックします。

![ コレクションのホバーアイコン ](/help/main/c-recommendations/c-products/assets/hover-collections.png)

既存のコレクションをコピーして重複するコレクションを作成し、後で変更できます。 これにより、少ない労力で同様の除外を作成できます。

コレクションは、アカウント全体で利用できることに注意してください。 コレクションを削除する前に、このことを考慮してください。 削除したコレクションは復元できません。

## Recommendations アクティビティでのコレクションの使用

1. 上記のいずれかの方法を使用して、コレクションを作成します。

1. 「**[!UICONTROL Activities]**」をクリックして [Recommendationsを新規作成 ](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md) アクティビティを作成するか、既存のアクティビティを編集します。

1. 条件とデザインを選択すると、目的のコレクションを選択したときに [!UICONTROL Options] のページが表示されます。

   ![ コレクションオプションを選択 ](/help/main/c-recommendations/c-products/assets/choose-collection.png)

1. （条件付き）既存のコレクション設定を変更するには、**[!UICONTROL Experiences]** のページ（3 つのパートから成るガイド付きワークフローのステップ 2）で、レコメンデーションを配置した場所をクリックし、「**[!UICONTROL Change Collection]**」をクリックして目的のコレクションを選択します。

   ![ コレクションを変更オプション ](/help/main/c-recommendations/c-products/assets/change-collection.png)

## トレーニングビデオ：Recommendationsでコレクションと除外を作成（7:05） ![ チュートリアルバッジ ](/help/main/assets/tutorial.png)

このビデオには、次の情報が含まれています。

* コレクションの作成
* 除外の作成

>[!VIDEO](https://video.tv.adobe.com/v/35311?captions=jpn)
