---
keywords: 条件シーケンス；複数の条件；アルゴリズム；条件；推奨事項の条件；シーケンス；返されるアイテム数の制限；スロットレベル制御；スロット
description: Adobe [!DNL Target] Recommendations アクティビティに表示される項目をより効果的に制御するために、最大5つの条件のシーケンスを設定する方法を説明します。
title: レコメンデーションで基準シーケンスを作成するにはどうすればよいですか？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: 5366c86c-7685-478b-a621-9b3f24296ab7
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '866'
ht-degree: 32%

---

# 条件のシーケンスの作成

最大 5 つの条件のシーケンスを使用して、[!UICONTROL Recommendations] アクティビティで表示される項目をより詳細に制御します。 返されるアイテムの数を制限することもできます（「スロットレベル制御」と呼ばれることもあります）。

>[!NOTE]
>
>条件シーケンスは、[!DNL Target Premium]の2016年10月リリースより前に作成された[!UICONTROL Recommendations] アクティビティでは使用できません。

条件のシーケンスを作成するには、まずシーケンスに含める条件を作成する必要があります。 詳しくは、[条件の作成](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md)を参照してください。

1 つの条件ではデザインを埋めるのに十分な結果が返されない場合、汎用的なバックアップレコメンデーションを使用する代わりに、条件のシーケンスを使用することで、ターゲットのレコメンデーションを追加で提供できます。 通常、基準順序は、より具体的なターゲティング（結果が少ない場合がある）から、より一般的なターゲティング（通常はより多くの結果が返される）へと進みます。

次の例に示すように、条件シーケンスはページの種類によって異なる場合があります。

| ページタイプ | 可能なシーケンス順序 |
| --- | --- |
| 製品ページ | <ol><li>現在の品目に基づいて、同じブランドから</li><li>現在の品目に基づいて、すべてのブランドから</li><li>コンテンツの類似性に基づいて</li><li>トップセラーに基づいて</li><li>サイト全体で最もよく閲覧された品目に基づいて</li></ol> |
| ホームページ | <ol><li>訪問者の最後の購入に基づいて </li><li>訪問者のお気に入りの品目に基づいて</li><li>訪問者のお気に入りのカテゴリーに基づいて</li><li>トップセラーに基づいて</li><li>サイト全体で最もよく閲覧された品目に基づいて</li></ol> |

## 基準シーケンスの作成

条件シーケンスは、[!UICONTROL 条件シーケンスを作成]画面から作成します。

[!UICONTROL 条件のシーケンスを作成]画面を表示するには、複数の方法があります。 一部の画面オプションは、画面の表示方法によって異なります。

* **[!UICONTROL レコメンデーション]**／**[!UICONTROL 条件]**&#x200B;ライブラリ画面で、**[!UICONTROL 条件を作成]**／**[!UICONTROL 条件のシーケンスを作成]**&#x200B;をクリックします。 ここで作成した条件は、自動的にすべての [!UICONTROL Recommendations] アクティビティで利用できるようになります。
* [!UICONTROL Recommendations] アクティビティを作成する場合は、選択条件画面で、**[!UICONTROL 新規作成]** > **[!UICONTROL 条件シーケンスの作成]**&#x200B;をクリックします。 他の [!UICONTROL Recommendations] アクティビティで使用するために新しい条件のシーケンスを保存するオプションがあります。
* [!UICONTROL Recommendations] アクティビティを編集する際に、ページの[!UICONTROL Recommendations Location] ボックスをクリックし、**[!UICONTROL 条件の変更]**&#x200B;を選択します。 [!UICONTROL 条件を選択]画面で、**[!UICONTROL 新規作成]**／**[!UICONTROL 条件のシーケンスを作成]**&#x200B;をクリックします。 他の [!UICONTROL Recommendations] アクティビティで使用するために新しい条件を保存するオプションがあります。

次の手順では、最初の方法を使用して[!UICONTROL 条件シーケンスを作成]画面にアクセスすることを前提としています：**[!UICONTROL Recommendations]** > **[!UICONTROL 条件]** ライブラリ画面。

1. **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**&#x200B;をクリックします。

1. **[!UICONTROL 条件を作成]** > **[!UICONTROL 条件シーケンスを作成]**&#x200B;をクリックします。

   ![CreateCriteriaSequence画像](assets/CreateCriteriaSequence.png)

1. 「[基本情報](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info)」セクションに情報を入力します。

1. **[!UICONTROL 条件シーケンス]** セクションで、**[!UICONTROL 条件を追加]**&#x200B;をクリックします。

   シーケンス順序は、デザインが入力される順序を定義します。 基準1にデザインを埋めるために十分な推奨事項がない場合、残りのスロットに基準2が埋められます。

   ![条件を追加](/help/main/c-recommendations/c-algorithms/assets/add-criteria.png)

1. [!UICONTROL 条件を選択]画面で、条件を選択し、**[!UICONTROL 追加]**&#x200B;をクリックします。

   検索ボックスとフィルタードロップダウンを使用して、目的の条件を見つけることができます。

   ![条件の選択](/help/main/c-recommendations/c-algorithms/assets/select-criteria.png)

1. （オプション）「**[!UICONTROL 返されるアイテムの数を制限]**」トグルを「オン」の位置にスライドさせ、アイテムの数（1 ～ 50個）を指定します。

   ![返されるアイテム数の制限toggle](/help/main/c-recommendations/c-algorithms/assets/limit-number.png)

   「[!UICONTROL 返されるアイテム数の制限]」オプション（「スロットレベル制御」とも呼ばれます）の値を理解するには、次の使用例を考慮してください。

   * **ユースケース 1**:1つのレコメンデーショントレイに、異なる種類のアイテムを混在させたい。 例えば、アウターウェア（ジャケット）とトップス（シャツ、T シャツ）を組み合わせて使用する場合などです。 これを実現するには、デザインの任意のスロットに必要なすべての潜在的な製品タイプを含むアクティビティにコレクションを使用します。 次に、アウターウェアのみを含めるように条件を制限する静的フィルターを使用して最初の条件を設定し、トップスのみを含めるように条件を制限する静的フィルターを使用して2番目の条件を設定します。 最後に、両方の条件を条件シーケンスに追加し、最初の条件を2つのスロットに制限します。

     レコメンデーショントレイは、サイト上では次のようになります。

     ![おすすめ商品レコメンデーショントレイ &#x200B;](/help/main/c-recommendations/c-algorithms/assets/featured-products.png)

   * **ユースケース 2**：代替アイテムと補完的アイテムの両方を組み合わせたい。 1つの条件を設定して、表示/表示アルゴリズムを使用し、推奨される項目を現在の項目のカテゴリに制限する動的フィルターを使用します。 2つ目の条件を設定して、閲覧済み/購入済みアルゴリズムを使用し、現在のアイテムのカテゴリに一致しない推奨アイテムのみを含むダイナミックフィルターを使用します。 最後に、両方の条件をシーケンスに追加し、最初の条件を2つのスロットに制限します。

1. 引き続き、シーケンスに条件を追加します。 1 つのシーケンスに最大 5 つの条件を追加できます。

1. [&#x200B; コンテンツのバックアップ オプション &#x200B;](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content)を有効にします。

1. 「**[!UICONTROL 保存]**」をクリックします。

   条件のシーケンスが条件リストに表示されます。

   レコメンデーションロジックのオプションについて詳しくは、[条件](/help/main/c-recommendations/c-algorithms/algorithms.md)を参照してください。

## トレーニングビデオ：Recommendationsで条件を作成する（12:33） ![&#x200B; チュートリアルバッジ &#x200B;](/help/main/assets/tutorial.png)

このビデオには、次の情報が含まれています。

* 条件の作成
* 条件のシーケンスの作成
* カスタム条件のアップロード

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
