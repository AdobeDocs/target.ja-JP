---
keywords: コレクション;ターゲット設定
description: コレクションのAdobe [!DNL Target] Recommendations。 コレクションは、レコメンデーションに使用できる商品または品目のセットです。
title: Recommendationsアクティビティでコレクションを使用する方法を教えてください。
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: e62f501b-3521-4456-9ea1-e4b8a2b478c6
source-git-commit: 2a25fdb42ce4470f9126b7e0e7f6fd9e60c350e5
workflow-type: tm+mt
source-wordcount: '884'
ht-degree: 60%

---

# コレクション

コレクションは、レコメンデーションに使用できる商品または品目のセットです。コレクションは、そのコレクションの一部となる項目で満たす必要がある条件を指定することで定義されます。

一般的に、コレクションは、単一の製品コレクションなどの同一または関連する品目のセットです。ただし、どの品目も、ビジネスに適したカテゴリにグループ化できます。例えば、特定の価格帯の製品や色の製品、特定の地域で興味を引く可能性の高い品目などです。

コレクションは、製品や論理的な格納場所を整理するために使用できます。例えば、ある品目が別の地域ではなく他の地域で使用可能な場合、訪問者の地域で使用できない品目を除外するコレクションを作成できます。 また、コレクションを使用すると、季節的な品目やビジネスに適した任意の整理パラメーターによる整理をおこなえます。

レコメンデーション内の各条件に対して生成される[代替レコメンデーション](/help/main/c-recommendations/c-algorithms/backup-recs.md)でもこのコレクションが使用されるので、コレクション内の品目だけが代替レコメンデーションに含まれます。コレクションを使用すると、ある位置での表示に適切な商品だけを、確実に表示させることができます。

コレクションは、各条件が実行されるたびに、再構築または更新されます。

品目をコレクションにグループ分けし、各カタログに個別のレコメンデーションを作成できます。

包含条件を使用するとコレクションと同様のことができますが、包含条件はアクティビティを作成する都度設定する必要があります。コレクションを使用すると、品目のセットを一度で作成でき、再度設定する必要なく使用したいときに使用できます。

[!DNL Recommendations] アクティビティを作成または編集しているときに、アクティビティ図の「[!UICONTROL 条件]」ラベルの横にコレクション名が表示されます。

>[!NOTE]
>
>[!UICONTROL 最近表示された項目]レコメンデーションキーを使用する際に、コレクションは適用されません。

## コレクションの作成 {#task_1256DFF6842141FCAADD9E1428EF7F08}

レコメンデーションに表示したい製品やコンテンツを整理するために、コレクションを作成します。

1. **[!UICONTROL Recommendations]**／**[!UICONTROL コレクション]**&#x200B;をクリックして、既存のコレクションのリストを表示します。

   ![コレクションリスト](assets/collections_list.png)

   この [!UICONTROL コレクション] ページには、既存のコレクションのリストが表示されます。 新しいコレクションを作成するには、 [!UICONTROL コレクションを作成] 」ボタンをクリックします。 コレクションを選択し、目的のアイコンをクリックして、既存のコレクションを編集、コピーおよび削除することもできます。

   ![ホバーアイコン：編集、コピー、削除](/help/main/c-recommendations/c-products/assets/hover-icons.png)

   [!UICONTROL コレクション]リストビューで各コレクションについて報告される「項目数」は、現在設定されているデフォルトの Recommendations[ ホストグループ](/help/main/administrating-target/hosts.md)（環境）内でそのコレクションのルールに一致する製品の数です。デフォルトのホストグループを変更するには、[設定](https://experienceleague.corp.adobe.com/docs/target-dev/developer/recommendations.html?lang=ja)を参照してください。{target=_blank}

1. 「**[!UICONTROL コレクションを作成]**」をクリックします。

1. （条件付き）コレクションの作成（または更新）時に、環境を&#x200B;**[!UICONTROL 環境]**&#x200B;フィルターから選択して、その環境のコレクションのコンテンツをプレビューします。デフォルトでは、デフォルトのホストグループの結果が表示されます。

   ![コレクションの作成](/help/main/c-recommendations/c-products/assets/CreateCollection.png)

1. コレクションの&#x200B;**[!UICONTROL 名前]**&#x200B;を入力します。

   オプションで&#x200B;**[!UICONTROL 説明]**&#x200B;を入力することもできます。

1. コレクションの構築に使用するルールを設定します。

   例えば、リスト内の product ID、category、margin などのパラメーターに関するコレクションを作成できます。

   ルールを追加し、複数のパラメーターを使用して、コレクションを定義することができます。複数のルールは、AND 演算子で結合されます。 コレクションが適用されるには、指定したすべてのルールに合致する必要があります。

1. 「**[!UICONTROL 保存]**」をクリックします。

## 詳細検索を使用したコレクションの作成

また、[カタログ検索](/help/main/c-recommendations/c-products/catalog-search.md#save-as)ページ（[!UICONTROL レコメンデーション]／[!UICONTROL カタログ検索]／[!UICONTROL 詳細検索]）の詳細検索を使用してコレクションを作成することもできます。

![名前を付けて保存ダイアログ](/help/main/c-recommendations/c-products/assets/save-as.png)

「ID／次を含む」などを使用した検索を作成したら、[!UICONTROL 名前を付けて保存]／[!UICONTROL コレクション]をクリックします。

>[!IMPORTANT]
>
>詳細検索機能では大文字と小文字は区別されません。ただし、配信時に返される商品は、大文字と小文字が区別される検索に基づきます。この違いが混乱を招くこともあります。詳細検索機能による結果を基にしてコレクションを作成する際は、大文字と小文字の区別を考慮してください。例えば、最初に「Holiday」と検索すると、「Holiday」または「holiday」を含む結果が返されます。その後、「holiday」を含む商品を返すことを目的としたカタログを作成すると、「holiday」を含む商品のみが返されます。「Holiday」を含む商品は返されません。

## コレクションの編集、コピー、削除

リスト内の目的のコレクションの上にマウスポインターを置いて、適切なアイコンをクリックします。編集、コピー、削除を行います。

![コレクションのアイコンにマウスポインターを置く](/help/main/c-recommendations/c-products/assets/hover-collections.png)

既存のコレクションをコピーして重複するコレクションを作成し、それを変更できます。 これにより、手間をかけずに同様の除外を作成できます。

コレクションはアカウント全体で使用できることに注意してください。 コレクションを削除する前に、必ずこの点を考慮してください。 削除したコレクションは復元できません。

## Recommendationsアクティビティでのコレクションの使用

1. 上記のいずれかの方法を使用してコレクションを作成します。

1. クリック **[!UICONTROL アクティビティ]** および [新しいRecommendationsを作成](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md) アクティビティを作成するか、既存のアクティビティを編集します。

1. 条件とデザインを選択すると、 [!UICONTROL オプション] ページが表示されます。

   ![コレクションオプションを選択](/help/main/c-recommendations/c-products/assets/choose-collection.png)

1. （条件付き）既存のコレクション設定を変更するには、 **[!UICONTROL エクスペリエンス]** （3 ステップのガイドによるワークフローの手順 2）を参照し、レコメンデーションを配置した場所をクリックし、 **[!UICONTROL コレクションを変更]**&#x200B;を選択し、目的のコレクションを選択します。

   ![コレクションを変更オプション](/help/main/c-recommendations/c-products/assets/change-collection.png)

## トレーニングビデオ：Recommendationsでのコレクションと除外の作成(7:05) ![チュートリアルバッジ](/help/main/assets/tutorial.png)

このビデオには、次の情報が含まれています。

* コレクションの作成
* 除外の作成

>[!VIDEO](https://video.tv.adobe.com/v/27689)
