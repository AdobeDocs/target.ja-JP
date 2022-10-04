---
keywords: 条件のシーケンス；複数の条件；アルゴリズム；条件；レコメンデーション条件；シーケンス；返される項目の制限数；スロットレベル制御；スロット
description: Adobeに表示される項目をより詳細に制御するために、最大 5 つの条件のシーケンスを設定する方法を説明します [!DNL Target] Recommendationsアクティビティ。
title: Recommendationsで条件のシーケンスを作成する方法を教えてください。
feature: Recommendations
exl-id: 5366c86c-7685-478b-a621-9b3f24296ab7
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '835'
ht-degree: 34%

---

# ![PREMIUM](/help/main/assets/premium.png) 条件のシーケンスの作成

最大 5 つの条件のシーケンスを使用して、[!UICONTROL Recommendations] アクティビティで表示される項目をより詳細に制御します。また、返される項目の数を制限することもできます（「スロットレベル制御」と呼ばれる場合もあります）。

>[!NOTE]
>
>[!DNL Target Premium] の 2016 年 10 月リリースより前に作成された [!UICONTROL Recommendations] アクティビティでは、条件のシーケンスは使用できません。

条件のシーケンスを作成するには、まずシーケンスに含める条件を作成する必要があります。詳しくは、[条件の作成](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md)を参照してください。

1 つの条件ではデザインを埋めるのに十分な結果が返されない場合、汎用的なバックアップレコメンデーションを使用する代わりに、条件のシーケンスを使用することで、ターゲットのレコメンデーションを追加で提供できます。通常、条件のシーケンスは、より具体的なターゲティング（より少ない結果が返される可能性があります）から、より一般的なターゲティング（通常はより多くの結果が返される）に進みます。

条件のシーケンスは、次の例に示すように、ページタイプに応じて順番に異なる場合があります。

| ページタイプ | 可能なシーケンスの順序 |
| --- | --- |
| 製品ページ | <ol><li>現在の品目に基づいて、同じブランドから</li><li>現在の品目に基づいて、すべてのブランドから</li><li>コンテンツの類似性に基づいて</li><li>トップセラーに基づいて</li><li>サイト全体で最もよく閲覧された品目に基づいて</li></ol> |
| ホームページ | <ol><li>訪問者の最後の購入に基づいて </li><li>訪問者のお気に入りの品目に基づいて</li><li>訪問者のお気に入りのカテゴリーに基づいて</li><li>トップセラーに基づいて</li><li>サイト全体で最もよく閲覧された品目に基づいて</li></ol> |

## 条件のシーケンスの作成

条件のシーケンスは、 [!UICONTROL 条件のシーケンスを作成] 画面

[!UICONTROL 条件のシーケンスを作成]画面を表示するには、複数の方法があります。一部の画面オプションは、画面の表示方法によって異なります。

* **[!UICONTROL レコメンデーション]**／**[!UICONTROL 条件]**&#x200B;ライブラリ画面で、**[!UICONTROL 条件を作成]**／**[!UICONTROL 条件のシーケンスを作成]**&#x200B;をクリックします。ここで作成した条件は、自動的にすべての [!UICONTROL Recommendations] アクティビティで利用できるようになります。
* を作成する際に、 [!UICONTROL Recommendations] 「 」アクティビティの「条件を選択」画面で、 **[!UICONTROL 新規作成]** > **[!UICONTROL 条件のシーケンスを作成]**. 他の [!UICONTROL Recommendations] アクティビティで使用するために新しい条件のシーケンスを保存するオプションがあります。
* を編集する際に、 [!UICONTROL Recommendations] アクティビティ、 [!UICONTROL Recommendations Location] 」ボックスをクリックし、「 **[!UICONTROL 条件を変更]**. [!UICONTROL 条件を選択]画面で、**[!UICONTROL 新規作成]**／**[!UICONTROL 条件のシーケンスを作成]**&#x200B;をクリックします。他の [!UICONTROL Recommendations] アクティビティで使用するために新しい条件を保存するオプションがあります。

次の手順では、 [!UICONTROL 条件のシーケンスを作成] 画面を次の最初の方法で表示します。の **[!UICONTROL Recommendations]** > **[!UICONTROL 条件]** ライブラリ画面

1. クリック **[!UICONTROL Recommendations]** > **[!UICONTROL 条件]**.

1. クリック **[!UICONTROL 条件の作成]** > **[!UICONTROL 条件のシーケンスを作成]**.

   ![CreateCriteriaSequence 画像](assets/CreateCriteriaSequence.png)

1. 次の項目に情報を入力します。 [基本情報](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info) 」セクションに入力します。

1. 内 **[!UICONTROL 条件のシーケンス]** セクションで、 **[!UICONTROL 条件を追加]**.

   シーケンスの順序は、デザインの塗り潰し順序を定義します。 条件 1 にデザインを埋めるのに十分なレコメンデーションがない場合、残りのスロットは条件 2 などで埋められます。

   ![条件を追加](/help/main/c-recommendations/c-algorithms/assets/add-criteria.png)

1. の [!UICONTROL 条件を選択] 画面を開き、条件を選択して、「 **[!UICONTROL 追加]**.

   「検索」ボックスとフィルタードロップダウンを使用して、必要な条件を検索できます。

   ![条件の選択](/help/main/c-recommendations/c-algorithms/assets/select-criteria.png)

1. （オプション） **[!UICONTROL 返される項目の数を制限]** 「オン」の位置に切り替えて、項目数を指定します (1 ～ 50)。

   ![返される項目数を制限切り替え](/help/main/c-recommendations/c-algorithms/assets/limit-number.png)

   を使用して、 [!UICONTROL 返される項目の数を制限] オプション（「スロットレベル制御」とも呼ばれる）では、次の使用例を考慮します。

   * **使用例 1**:1 つのレコメンデーショントレイに異なる種類の品目を混在させる場合。 例えば、アウター（ジャケット）とトップ（シャツ、T シャツ）の組み合わせを表示したいとします。 これを実現するには、デザインの任意のスロットで必要となるすべての潜在的な製品タイプを含むアクティビティにコレクションを使用します。 次に、上着のみを含むように条件を制限する静的フィルタを使用して最初の条件を設定し、上着のみを含むように条件を制限する静的フィルタを使用して 2 番目の条件を設定します。 最後に、両方の条件を条件シーケンスに追加し、最初の条件を 2 スロットに制限します。

      レコメンデーショントレイは、サイトでは次のように表示されます。

      ![おすすめ製品のレコメンデーショントレイ](/help/main/c-recommendations/c-algorithms/assets/featured-products.png)

   * **使用例 2**:代替品目と補足品目の両方を組み合わせる必要があります。 表示/表示アルゴリズムを使用する 1 つの条件を設定し、レコメンデーション品目を現在の品目のカテゴリに制限する動的フィルターを使用します。 2 つ目の条件を設定して、閲覧済み/購入済みのアルゴリズムを使用し、現在の品目のカテゴリと一致しないレコメンデーション品目のみを含む動的フィルターを使用します。 最後に、両方の条件をシーケンスに追加し、最初の条件を 2 スロットに制限します。

1. 引き続きシーケンスに条件を追加します。 1 つのシーケンスに最大 5 つの条件を追加できます。

1. 有効にする [バックアップコンテンツオプション](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content).

1. 「**[!UICONTROL 保存]**」をクリックします。

   条件のシーケンスが条件リストに表示されます。

   レコメンデーションロジックのオプションについて詳しくは、[条件](/help/main/c-recommendations/c-algorithms/algorithms.md)を参照してください。

## トレーニングビデオ：Recommendations の条件の作成（12:33）![チュートリアルバッジ](/help/main/assets/tutorial.png)

このビデオには、次の情報が含まれています。

* 条件の作成
* 条件のシーケンスの作成
* カスタム条件のアップロード

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
