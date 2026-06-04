---
keywords: コレクション;ターゲティング
description: ' [!DNL Target Recommendations]の製品またはアイテムのコレクションを使用する方法を説明します。'
title: レコメンデーションアクティビティでコレクションを使用するにはどうすればよいですか？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: e62f501b-3521-4456-9ea1-e4b8a2b478c6
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '897'
ht-degree: 44%

---

# コレクション

コレクションは、レコメンデーションに使用できる商品または品目のセットです。 コレクションは、そのコレクションに含まれるアイテムが満たす必要がある条件を指定することによって定義されます。

一般的に、コレクションは、単一の製品コレクションなどの同一または関連する品目のセットです。 ただし、特定の価格帯や色の商品、特定の地域で関心を示す可能性の高い商品など、ビジネスにとって意味のあるカテゴリーに分類することは可能です。

コレクションは、製品や論理的な格納場所を整理するために使用できます。 例えば、ある地域で利用可能なアイテムが別の地域では利用できないアイテムがある場合、訪問者の地域で利用できないアイテムを除外するコレクションを作成できます。 また、コレクションを使用すると、季節的な品目やビジネスに適した任意の整理パラメーターによる整理をおこなえます。

レコメンデーション内の各条件に対して生成される[代替レコメンデーション](/help/main/c-recommendations/c-algorithms/backup-recs.md)でもこのコレクションが使用されるので、コレクション内の品目だけが代替レコメンデーションに含まれます。 コレクションを使用すると、ある位置での表示に適切な商品だけを、確実に表示させることができます。

コレクションは、各条件が実行されるたびに、再構築または更新されます。

品目をコレクションにグループ分けし、各カタログに個別のレコメンデーションを作成できます。

包含条件を使用するとコレクションと同様のことができますが、包含条件はアクティビティを作成する都度設定する必要があります。 コレクションを使用すると、品目のセットを一度で作成でき、再度設定する必要なく使用したいときに使用できます。

[!DNL Recommendations] アクティビティを作成または編集する際に、アクティビティ ダイアグラムの[!UICONTROL 条件] ラベルの横にコレクション名が表示されます。

>[!NOTE]
>
>[!UICONTROL 最近閲覧したアイテム ]のレコメンデーションキーを使用する場合、コレクションは適用されません。

## コレクションの作成 {#task_1256DFF6842141FCAADD9E1428EF7F08}

レコメンデーションに表示する商品やコンテンツを整理するためのコレクションを作成します。

1. **[!UICONTROL Recommendations]** > **[!UICONTROL コレクション]**&#x200B;をクリックして、既存のコレクションのリストを表示します。

   ![コレクションリスト](assets/collections_list.png)

   [!UICONTROL  コレクション ] ページには、既存のコレクションのリストが表示されます。 「[!UICONTROL  コレクションを作成]」ボタンをクリックして、新しいコレクションを作成します。 また、目的のコレクションにカーソルを合わせて目的のアイコンをクリックすると、既存のコレクションを編集、コピー、削除することもできます。

   ![ アイコンにカーソルを合わせる：編集、コピー、削除](/help/main/c-recommendations/c-products/assets/hover-icons.png)

   [!UICONTROL  コレクション ] リストビューの各コレクションについて報告された「アイテム数」は、設定されたデフォルトのRecommendations [ ホストグループ ](/help/main/administrating-target/hosts.md) （環境）内の、そのコレクションのルールに一致する製品の数です。 デフォルトのホストグループを変更するには、[設定](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html?lang=ja){target=_blank}を参照してください。

1. 「**[!UICONTROL コレクションを作成]**」をクリックします。

1. （条件付き）コレクションを作成（または更新）中に&#x200B;**[!UICONTROL 環境]** フィルターから環境を選択して、その環境内のコレクションの内容をプレビューします。 デフォルトでは、デフォルトのホストグループの結果が表示されます。

   ![コレクションの作成](/help/main/c-recommendations/c-products/assets/CreateCollection.png)

1. コレクションの&#x200B;**[!UICONTROL 名前]**&#x200B;を入力します。

   オプションで&#x200B;**[!UICONTROL 説明]**&#x200B;を入力することもできます。

1. コレクションの構築に使用するルールを設定します。

   例えば、リスト内の product ID、category、margin などのパラメーターに関するコレクションを作成できます。

   ルールを追加し、複数のパラメーターを使用して、コレクションを定義することができます。 複数のルールをAND演算子で結合します。 コレクションが適用されるには、指定したすべてのルールに合致する必要があります。

1. 「**[!UICONTROL 保存]**」をクリックします。

## 詳細検索を使用したコレクションの作成

また、[ カタログ検索](/help/main/c-recommendations/c-products/catalog-search.md#save-as) ページ （[!UICONTROL Recommendations] > [!UICONTROL  カタログ検索] > [!UICONTROL 高度な検索]）で高度な検索を使用してコレクションを作成することもできます。

![別名で保存ダイアログ ](/help/main/c-recommendations/c-products/assets/save-as.png)

例えば、「id >次を含む」を使用して検索を作成した後、[!UICONTROL 別名で保存] > [!UICONTROL  コレクション ]をクリックできます。

>[!IMPORTANT]
>
>詳細検索機能では大文字と小文字は区別されません。ただし、配信時に返される商品は、大文字と小文字が区別される検索に基づきます。 この違いが混乱を招くこともあります。 詳細検索機能による結果を基にしてコレクションを作成する際は、大文字と小文字の区別を考慮してください。 例えば、最初に「Holiday」と検索すると、「Holiday」または「holiday」を含む結果が返されます。 その後、「holiday」を含む商品を返すことを目的としたカタログを作成すると、「holiday」を含む商品のみが返されます。 「Holiday」を含む商品は返されません。

## コレクションの編集、コピー、削除

リスト内の目的のコレクションにカーソルを合わせ、編集、コピー、削除の適切なアイコンをクリックします。

コレクションの![ アイコンにカーソルを合わせる](/help/main/c-recommendations/c-products/assets/hover-collections.png)

既存のコレクションをコピーして重複したコレクションを作成し、それを変更できます。 これにより、より少ない労力で同様の除外を作成できます。

コレクションはアカウント全体で利用できます。 コレクションを削除する前に、この点を考慮してください。 削除したコレクションは復元できません。

## Recommendations アクティビティでのコレクションの使用

1. 上記のいずれかの方法を使用して、コレクションを作成します。

1. **[!UICONTROL アクティビティ]**&#x200B;と[をクリックして、新しいRecommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md) アクティビティを作成するか、既存のアクティビティを編集します。

1. 条件とデザインを選択すると、目的のコレクションを選択すると、[!UICONTROL  オプション ] ページが表示されます。

   ![ コレクションオプションを選択](/help/main/c-recommendations/c-products/assets/choose-collection.png)

1. （条件付き）既存のコレクション設定を変更するには、**[!UICONTROL エクスペリエンス]** ページ（3部構成のガイド付きワークフローのステップ 2）で、レコメンデーションを配置した場所をクリックし、**[!UICONTROL コレクションを変更]**&#x200B;をクリックしてから、目的のコレクションを選択します。

   ![ コレクションの変更オプション ](/help/main/c-recommendations/c-products/assets/change-collection.png)

## トレーニングビデオ：レコメンデーションでコレクションと除外を作成する（7:05） ![ チュートリアルバッジ ](/help/main/assets/tutorial.png)

このビデオには、次の情報が含まれています。

* コレクションの作成
* 除外の作成

>[!VIDEO](https://video.tv.adobe.com/v/27689)
