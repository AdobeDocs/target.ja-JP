---
keywords: 条件シーケンス；複数の条件；アルゴリズム；条件；推奨事項の条件；シーケンス；返されるアイテム数の制限；スロットレベル制御；スロット
description: Recommendations アクティビティに表示される項目をより詳細に制御するために、最大5つの条件のシーケンスを設定する方法について説明します。
title: レコメンデーションで基準シーケンスを作成するにはどうすればよいですか？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: 5366c86c-7685-478b-a621-9b3f24296ab7
TQID: https://experienceleague.adobe.com/dxO5cKxesTxgzZyfcvydQUlSq4TAgFN0ztT5VIe1WKU
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 763
ht-degree: 21%

---

# 条件のシーケンスの作成

最大5つの条件のシーケンスを使用して、[!DNL Adobe Target] [!UICONTROL Recommendations] アクティビティに表示される項目をより詳細に制御します。 また、返されるアイテムの数を制限することもできます（「スロットレベル制御」と呼ばれることもあります）。

>[!NOTE]
>
>条件シーケンスは、[!DNL Target Premium]の2016年10月リリースより前に作成された[!UICONTROL Recommendations] アクティビティでは使用できません。

条件のシーケンスを作成するには、まずシーケンスに含める条件を作成する必要があります。 詳しくは、[条件の作成](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md)を参照してください。

1 つの条件ではデザインを埋めるのに十分な結果が返されない場合、汎用的なバックアップレコメンデーションを使用する代わりに、条件のシーケンスを使用することで、ターゲットのレコメンデーションを追加で提供できます。 通常、基準シーケンスは、より具体的なターゲティング（結果が少ない場合がある）から、より一般的なターゲティング（通常はより多くの結果が返される）に移行します。

次の例に示すように、条件シーケンスはページの種類によって異なる場合があります。

| ページタイプ | 可能なシーケンス順序 |
| --- | --- |
| 製品ページ | <ol><li>現在のアイテムに基づいて、同じブランドから</li><li>現在の品目に基づいて、すべてのブランドから</li><li>コンテンツの類似性に基づいて</li><li>トップセラーに基づいて</li><li>サイト全体で最もよく閲覧された品目に基づいて</li></ol> |
| ホームページ | <ol><li>訪問者の最後の購入に基づいて </li><li>訪問者のお気に入りの品目に基づいて</li><li>訪問者のお気に入りのカテゴリーに基づいて</li><li>トップセラーに基づいて</li><li>サイト全体で最もよく閲覧された品目に基づいて</li></ol> |

## 基準シーケンスの作成

[!UICONTROL Create Criteria Sequence]画面から条件シーケンスを作成します。

[!UICONTROL Create Criteria Sequence]画面に到達する方法は複数あります。 一部の画面オプションは、画面の表示方法によって異なります。

* **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]** ライブラリ画面で、**[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria Sequence]**&#x200B;をクリックします。 ここで作成した条件は、自動的にすべての [!UICONTROL Recommendations] アクティビティで利用できるようになります。
* [!UICONTROL Recommendations] アクティビティを作成する場合は、[!UICONTROL Select Criteria]画面で、**[!UICONTROL Create New]** > **[!UICONTROL Create Criteria Sequence]**&#x200B;をクリックします。 他の[!UICONTROL Recommendations] アクティビティで使用するために、新しい条件シーケンスを保存するオプションがあります。
* [!UICONTROL Recommendations] アクティビティを編集する場合は、ページの[!UICONTROL Recommendations Location] ボックスをクリックし、**[!UICONTROL Change Criteria]**&#x200B;を選択します。 [!UICONTROL Select Criteria]画面で、**[!UICONTROL Create New]** > **[!UICONTROL Create Criteria Sequence]**&#x200B;をクリックします。 他の[!UICONTROL Recommendations] アクティビティで使用するために、新しい条件を保存するオプションがあります。

次の手順では、最初の方法（**[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]** ライブラリ画面）を使用して、[!UICONTROL Create Criteria Sequence]画面にアクセスすることを前提としています。

1. **[!UICONTROL Recommendations]**／**[!UICONTROL Criteria]**&#x200B;をクリックします。

1. **[!UICONTROL Create Criteria]**／**[!UICONTROL Create Criteria Sequence]**&#x200B;をクリックします。

1. 「[基本情報](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info)」セクションに情報を入力します。

1. **[!UICONTROL Criteria Sequence]** セクションで、プラス（+）記号をクリックして、1つ以上の基準シーケンスを追加します。

   シーケンス順序は、デザインが入力される順序を定義します。 条件1にデザインを埋めるために十分な推奨事項がない場合は、残りのスロットに条件2などが埋められます。

1. [!UICONTROL Select Criteria]画面で条件を選択し、**[!UICONTROL Save]**&#x200B;をクリックします。

   [!UICONTROL Search] ボックスとフィルターオプションを使用して、目的の条件を見つけることができます。

1. （オプション） **[!UICONTROL Limit the number of items returned]** トグルを「オン」の位置にスライドさせ、項目数（1 ～ 50個）を指定します。

   [!UICONTROL Limit the number of items returned] オプションの値（「スロットレベル制御」とも呼ばれます）を理解するには、次の使用例を考慮してください。

   * **ユースケース 1**:1つのレコメンデーショントレイに、異なる種類のアイテムを混在させたい。 例えば、アウターウェア（ジャケット）とトップス（シャツ、T シャツ）を組み合わせて使用する場合などです。 これを実現するには、デザインの任意のスロットに必要なすべての潜在的な製品タイプを含むアクティビティにコレクションを使用します。 次に、アウターウェアのみを含めるように条件を制限する静的フィルターを使用して最初の条件を設定し、トップスのみを含めるように条件を制限する静的フィルターを使用して2番目の条件を設定します。 最後に、両方の条件を条件シーケンスに追加し、最初の条件を2つのスロットに制限します。

     レコメンデーショントレイは、サイト上では次のようになります。

     ![おすすめ商品レコメンデーショントレイ ](/help/main/c-recommendations/c-algorithms/assets/featured-products.png)

   * **ユースケース 2**：代替アイテムと補完的アイテムの両方を組み合わせたい。 1つの条件を設定して、表示/表示アルゴリズムを使用し、推奨される項目を現在の項目のカテゴリに制限する動的フィルターを使用します。 2つ目の条件を設定して、閲覧済み/購入済みアルゴリズムを使用し、現在のアイテムのカテゴリに一致しない推奨アイテムのみを含むダイナミックフィルターを使用します。 最後に、両方の条件をシーケンスに追加し、最初の条件を2つのスロットに制限します。

1. 引き続き、シーケンスに条件を追加します。 1 つのシーケンスに最大 5 つの条件を追加できます。

1. [ コンテンツのバックアップ オプション ](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content)を有効にします。

1. **[!UICONTROL Create]** をクリックします。

   条件シーケンスが[!UICONTROL Criteria] リストに表示されます。

   レコメンデーションロジックのオプションについて詳しくは、[条件](/help/main/c-recommendations/c-algorithms/algorithms.md)を参照してください。
