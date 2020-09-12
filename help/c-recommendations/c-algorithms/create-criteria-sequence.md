---
keywords: criteria sequence;multiple criteria;algorithms;criteria;recommendations criteria;sequence;limit number of items returned
description: 最大5つの条件のシーケンスを使用して、Adobe TargetRecommendationsアクティビティに表示される項目をより詳細に制御します。
title: 条件のシーケンスの作成
feature: criteria
uuid: 9a5ca86b-fc79-4c24-b86f-e333b0c63088
translation-type: tm+mt
source-git-commit: 81de460e5cd9277adcee4bd6e1e0175b0e350605
workflow-type: tm+mt
source-wordcount: '787'
ht-degree: 36%

---


# ![PREMIUM](/help/assets/premium.png) 条件のシーケンスの作成

最大 5 つの条件のシーケンスを使用して、[!UICONTROL Recommendations] アクティビティで表示される項目をより詳細に制御します。

>[!NOTE]
>
>[!DNL Target Premium] の 2016 年 10 月リリースより前に作成された [!UICONTROL Recommendations] アクティビティでは、条件のシーケンスは使用できません。

条件のシーケンスを作成するには、まずシーケンスに含める条件を作成する必要があります。詳しくは、[条件の作成](/help/c-recommendations/c-algorithms/create-new-algorithm.md)を参照してください。

1 つの条件ではデザインを埋めるのに十分な結果が返されない場合、汎用的なバックアップレコメンデーションを使用する代わりに、条件のシーケンスを使用することで、ターゲットのレコメンデーションを追加で提供できます。通常、条件のシーケンスは、より具体的なターゲティング（より少ない結果が返される可能性がある）からより一般的なターゲティング（通常、より多くの結果が返される）に進みます。

次の例に示すように、条件のシーケンスは、ページタイプによって異なる場合があります。

| ページタイプ | 可能な順序 |
| --- | --- |
| 製品ページ | <ol><li>現在の品目に基づいて、同じブランドから</li><li>現在の品目に基づいて、すべてのブランドから</li><li>コンテンツの類似性に基づいて</li><li>トップセラーに基づいて</li><li>サイト全体で最もよく閲覧された品目に基づいて</li></ol> |
| ホームページ | <ol><li>訪問者の最後の購入に基づいて </li><li>訪問者のお気に入りの品目に基づいて</li><li>訪問者のお気に入りのカテゴリーに基づいて</li><li>トップセラーに基づいて</li><li>サイト全体で最もよく閲覧された品目に基づいて</li></ol> |

## 条件のシーケンスの作成

条件のシーケンスは、「条件のシーケンスを [!UICONTROL 作成] 」画面で作成します。

[!UICONTROL 条件のシーケンスを作成]画面を表示するには、複数の方法があります。一部の画面オプションは、画面の表示方法によって異なります。

* **[!UICONTROL レコメンデーション]**／**[!UICONTROL 条件]**&#x200B;ライブラリ画面で、**[!UICONTROL 条件を作成]**／**[!UICONTROL 条件のシーケンスを作成]**&#x200B;をクリックします。ここで作成した条件は、自動的にすべての [!UICONTROL Recommendations] アクティビティで利用できるようになります。
* [!UICONTROL Recommendations] アクティビティを作成している場合、条件を選択画面で、 **[!UICONTROL 新規作成/条件のシーケンスを]** 作成をクリックします ****。 他の [!UICONTROL Recommendations] アクティビティで使用するために新しい条件のシーケンスを保存するオプションがあります。
* [!UICONTROL Recommendations] アクティビティを編集する場合は、ページの「 [!UICONTROL Recommendationsの場所] 」ボックスをクリックし、「条件を **[!UICONTROL 変更]**」を選択します。 [!UICONTROL 条件を選択]画面で、**[!UICONTROL 新規作成]**／**[!UICONTROL 条件のシーケンスを作成]**&#x200B;をクリックします。他の [!UICONTROL Recommendations] アクティビティで使用するために新しい条件を保存するオプションがあります。

次の手順は、最初の方法を使用して [!UICONTROL 条件のシーケンスを] 作成画面にアクセスしたことを前提としています。 **[!UICONTROL Recommendations]** / **[!UICONTROL 条件]** ライブラリ画面。

1. **[!UICONTROL Recommendations]** / **[!UICONTROL 条件]**&#x200B;をクリックします。

1. 条件 **[!UICONTROL を作成]** /条件のシーケンスを **[!UICONTROL 作成をクリックします]**。

   ![](assets/CreateCriteriaSequence.png)

1. Fill in the information in the [Basic Information](/help/c-recommendations/c-algorithms/create-new-algorithm.md#info) section.

1. 「 **[!UICONTROL 条件のシーケンス]** 」セクションで、「条件 **[!UICONTROL 」をクリックします]**。

   シーケンスの順序は、デザインが入力される順序を定義します。 条件1にデザインを埋めるのに十分なレコメンデーションがない場合、残りのスロットは条件2などで埋められます。

   ![追加条件](/help/c-recommendations/c-algorithms/assets/add-criteria.png)

1. 条件を [!UICONTROL 選択] 画面で条件を選択し、をクリックし ****&#x200B;追加ます。

   「検索」ボックスとフィルタードロップダウンを使用して、目的の条件を見つけることができます。

   ![条件の選択](/help/c-recommendations/c-algorithms/assets/select-criteria.png)

1. （オプション）「返されるアイテム数の **[!UICONTROL 制限]** 」を「オン」の位置に切り替えて、アイテム数を指定します(1 ～ 50)。

   ![返す項目数の制限切り替え](/help/c-recommendations/c-algorithms/assets/limit-number.png)

   「返すアイテム数を [!UICONTROL 制限する」オプションの値を理解するために] 、次の使用例を検討してください。

   * **使用例1**:異なる種類の品目を1つのレコメンデーショントレイに混在させる場合。 例えば、上着（ジャケット）とトップ（シャツ、Tシャツ）を組み合わせて表示するとします。 これを実現するには、デザインの任意のスロットに含めるすべての潜在的なアクティビティタイプを含む製品のコレクションを使用します。 次に、上着のみを含めるように条件を制限する静的フィルタを使用して最初の条件を設定し、上着のみを含めるように条件を制限する静的フィルタを使用して2番目の条件を設定します。 最後に、両方の条件を条件のシーケンスに追加し、最初の条件を2スロットに制限します。

      サイトでは、次のようなレコメンデーショントレイが表示されます。

      ![特集商品のレコメンデーショントレイ](/help/c-recommendations/c-algorithms/assets/featured-products.png)

   * **使用例2**:代替品目と補足品目の両方を組み合わせる必要がある。 1つの条件を設定して、表示済み/表示済みのアルゴリズムを使用し、レコメンデーション品目を現在の品目のカテゴリに制限する動的フィルターを使用します。 2つ目の条件は、閲覧済み/購入済みのアルゴリズムを使用し、現在の品目のカテゴリと一致しないレコメンデーション品目のみを含む動的フィルターを使用するように設定します。 最後に、両方の条件をシーケンスに追加し、最初の条件を2スロットに制限します。

1. シーケンスへの追加の条件の追加を続けます。 1 つのシーケンスに最大 5 つの条件を追加できます。

1. 「 [バックアップコンテンツ」オプションを有効にします](/help/c-recommendations/c-algorithms/create-new-algorithm.md#content)。

1. 「**[!UICONTROL 保存]**」をクリックします。

   条件のシーケンスが条件リストに表示されます。

   レコメンデーションロジックのオプションについて詳しくは、[条件](../../c-recommendations/c-algorithms/algorithms.md)を参照してください。

## トレーニングビデオ：Recommendations の条件の作成（12:33） ![チュートリアルバッジ](/help/assets/tutorial.png)

このビデオには、次の情報が含まれています。

* 条件の作成
* 条件のシーケンスの作成
* カスタム条件のアップロード

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
