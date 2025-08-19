---
keywords: 条件シーケンス；複数の条件；アルゴリズム；条件；recommendations 条件；シーケンス；返される項目数の制限；スロットレベルコントロール；スロット
description: 最大 5 つの条件のシーケンスを設定して、Adobe [!DNL Target] Recommendations アクティビティに表示される項目をより詳細に制御する方法を説明します。
title: Recommendations で条件のシーケンスを作成するには
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: 5366c86c-7685-478b-a621-9b3f24296ab7
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '786'
ht-degree: 25%

---

# 条件のシーケンスの作成

最大 5 つの条件のシーケンスを使用して、[!UICONTROL Recommendations] アクティビティに表示される項目をより詳細に制御します。 返される項目の数を制限することもできます（「スロットレベル制御」とも呼ばれます）。

>[!NOTE]
>
>条件シーケンスは、[!UICONTROL Recommendations] の 2016 年 10 月リリースより前に作成された [!DNL Target Premium] アクティビティでは使用できません。

条件のシーケンスを作成するには、まずシーケンスに含める条件を作成する必要があります。詳しくは、[ 条件の作成 ](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md) を参照してください。

1 つの条件ではデザインを埋めるのに十分な結果が返されない場合、汎用的なバックアップレコメンデーションを使用する代わりに、条件のシーケンスを使用することで、ターゲットのレコメンデーションを追加で提供できます。通常、条件のシーケンスは、より具体的なターゲティング（結果が少ない可能性があります）から、より一般的なターゲティング（通常はより多くの結果が返されます）に進みます。

条件のシーケンスは、次の例に示すように、ページタイプによって順番が異なる場合があります。

| ページタイプ | 可能なシーケンス順序 |
| --- | --- |
| 製品ページ | <ol><li>現在の品目に基づいて、同じブランドから</li><li>現在の品目に基づいて、すべてのブランドから</li><li>コンテンツの類似性に基づいて</li><li>トップセラーに基づいて</li><li>サイト全体で最もよく閲覧された品目に基づいて</li></ol> |
| ホームページ | <ol><li>訪問者の最後の購入に基づいて </li><li>訪問者のお気に入りの品目に基づいて</li><li>訪問者のお気に入りのカテゴリーに基づいて</li><li>トップセラーに基づいて</li><li>サイト全体で最もよく閲覧された品目に基づいて</li></ol> |

## 条件シーケンスの作成

[!UICONTROL Create Criteria Sequence] 画面から条件のシーケンスを作成します。

[!UICONTROL Create Criteria Sequence] 画面に到達する方法は複数あります。 一部の画面オプションは、画面の表示方法によって異なります。

* **[!UICONTROL Recommendations]** / **[!UICONTROL Criteria]** ライブラリ画面で、**[!UICONTROL Create Criteria]** / **[!UICONTROL Create Criteria Sequence]** をクリックします。 ここで作成した条件は、自動的にすべての [!UICONTROL Recommendations] アクティビティで利用できるようになります。
* [!UICONTROL Recommendations] アクティビティを作成する場合は、「条件を選択」画面で **[!UICONTROL Create New]**/**[!UICONTROL Create Criteria Sequence]** をクリックします。 他の [!UICONTROL Recommendations] アクティビティで使用する新しい条件シーケンスを保存するオプションがあります。
* [!UICONTROL Recommendations] アクティビティを編集する場合は、ページの [!UICONTROL Recommendations Location] ボックスをクリックし、「**[!UICONTROL Change Criteria]**」を選択します。 [!UICONTROL Select Criteria] 画面で、**[!UICONTROL Create New]**/**[!UICONTROL Create Criteria Sequence]** をクリックします。 他の [!UICONTROL Recommendations] アクティビティで使用するために新しい条件を保存するオプションがあります。

以下の手順では、最初のメソッド（[!UICONTROL Create Criteria Sequence] / **[!UICONTROL Recommendations]** ライブラリ画面）を使用して **[!UICONTROL Criteria]** ール画面にアクセスすることを想定しています。

1. **[!UICONTROL Recommendations]**／**[!UICONTROL Criteria]**&#x200B;をクリックします。

1. **[!UICONTROL Create Criteria]**／**[!UICONTROL Create Criteria Sequence]**&#x200B;をクリックします。

   ![CreateCriteriaSequence 画像 ](assets/CreateCriteriaSequence.png)

1. 「基本情報 [ セクションに情報を入力し ](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info) す。

1. 「**[!UICONTROL Criteria Sequence]**」セクションで、「**[!UICONTROL Add Criteria]**」をクリックします。

   シーケンスの順序は、デザインが入力される順序を定義します。 条件 1 にデザインを満たすだけのレコメンデーションがない場合は、残りのスロットが条件 2 で満たされます。

   ![ 条件の追加 ](/help/main/c-recommendations/c-algorithms/assets/add-criteria.png)

1. [!UICONTROL Select Criteria] 画面で条件を選択し、「**[!UICONTROL Add]**」をクリックします。

   「検索」ボックスとフィルタードロップダウンを使用して、目的の条件を見つけることができます。

   ![条件の選択](/help/main/c-recommendations/c-algorithms/assets/select-criteria.png)

1. （オプション） **[!UICONTROL Limit the number of items returned]** 切り替えスイッチを「オン」の位置にスライドさせ、項目数（1～50）を指定します。

   ![ 返される項目の数を制限に切り替え ](/help/main/c-recommendations/c-algorithms/assets/limit-number.png)

   [!UICONTROL Limit the number of items returned] オプション（「スロットレベル制御」とも呼ばれます）の値を理解しやすくするために、次のユースケースを考慮します。

   * **ユースケース 1**:1 つのレコメンデーショントレイに様々な種類のアイテムを混在させる。 例えば、アウターウェア（ジャケット）とトップス（シャツ、T シャツ）を混在させて表示するとします。 これを実現するには、デザインの任意のスロットに必要なすべての潜在的な製品タイプを含むアクティビティのコレクションを使用します。 次に、アウターウェアのみを含めるように条件を制限する静的フィルターで最初の条件を設定し、トップスのみを含めるように条件を制限する静的フィルターで 2 番目の条件を設定します。 最後に、両方の条件を条件シーケンスに追加し、最初の条件を 2 スロットに制限します。

     Recommendations トレイは、サイトでは次のようになります。

     ![ おすすめ製品レコメンデーショントレイ ](/help/main/c-recommendations/c-algorithms/assets/featured-products.png)

   * **ユースケース 2**：代替項目と補完項目の両方を組み合わせたい場合。 表示/閲覧アルゴリズムを使用する条件を 1 つ設定し、推奨される項目を現在の項目のカテゴリに制限する動的フィルターを使用します。 2 番目の条件を設定して、閲覧/購入アルゴリズムを使用し、現在の項目のカテゴリに一致しない推奨項目のみを含む動的フィルターを使用します。 最後に、シーケンスに両方の条件を追加し、最初の条件を 2 スロットに制限します。

1. シーケンスに条件を追加し続けます。 1 つのシーケンスに最大 5 つの条件を追加できます。

1. [ コンテンツのバックアップオプション ](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content) を有効にします。

1. **[!UICONTROL Save]** をクリックします。

   条件のシーケンスが条件リストに表示されます。

   レコメンデーションロジックのオプションについて詳しくは、[条件](/help/main/c-recommendations/c-algorithms/algorithms.md)を参照してください。

## トレーニングビデオ：Recommendations で条件を作成（12:33） ![ チュートリアルバッジ ](/help/main/assets/tutorial.png)

このビデオには、次の情報が含まれています。

* 条件の作成
* 条件のシーケンスの作成
* カスタム条件のアップロード

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
