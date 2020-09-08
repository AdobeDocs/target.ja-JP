---
keywords: criteria sequence;multiple criteria;algorithms;criteria;recommendations criteria;sequence;
description: 最大5つの条件のシーケンスを使用して、Adobe TargetRecommendationsアクティビティに表示される項目をより詳細に制御します。
title: 条件のシーケンスの作成
feature: criteria
uuid: 9a5ca86b-fc79-4c24-b86f-e333b0c63088
translation-type: tm+mt
source-git-commit: b85237ba7526701dee76810af1b719be00fb4fc3
workflow-type: tm+mt
source-wordcount: '840'
ht-degree: 57%

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

## 条件のシーケンスを作成画面にアクセスする

[!UICONTROL 条件のシーケンスを作成]画面を表示するには、複数の方法があります。一部の画面オプションは、画面の表示方法によって異なります。

* **[!UICONTROL レコメンデーション]**／**[!UICONTROL 条件]**&#x200B;ライブラリ画面で、**[!UICONTROL 条件を作成]**／**[!UICONTROL 条件のシーケンスを作成]**&#x200B;をクリックします。ここで作成した条件は、自動的にすべての [!UICONTROL Recommendations] アクティビティで利用できるようになります。
* [!UICONTROL Recommendations] アクティビティを作成している場合、条件を選択画面で、 **[!UICONTROL 新規作成/条件のシーケンスを]** 作成をクリックします ****。 他の [!UICONTROL Recommendations] アクティビティで使用するために新しい条件のシーケンスを保存するオプションがあります。
* [!UICONTROL Recommendations] アクティビティを編集する場合は、ページの「 [!UICONTROL Recommendationsの場所] 」ボックスをクリックし、「条件を **[!UICONTROL 変更]**」を選択します。 [!UICONTROL 条件を選択]画面で、**[!UICONTROL 新規作成]**／**[!UICONTROL 条件のシーケンスを作成]**&#x200B;をクリックします。他の [!UICONTROL Recommendations] アクティビティで使用するために新しい条件を保存するオプションがあります。

次の手順は、最初の方法を使用して [!UICONTROL 条件のシーケンスを] 作成画面にアクセスしたことを前提としています。 **[!UICONTROL Recommendations]** / **[!UICONTROL 条件]** ライブラリ画面。

1. **[!UICONTROL Recommendations]** / **[!UICONTROL 条件]**&#x200B;をクリックします。

1. 条件 **[!UICONTROL を作成]** /条件のシーケンスを **[!UICONTROL 作成をクリックします]**。

   ![](assets/CreateCriteriaSequence.png)

## 「情報」セクションに入力します。

1. シーケンスの&#x200B;**[!UICONTROL 名前]**&#x200B;を入力します。

   これは、条件のシーケンスの説明に使用される「内部」名です。サイトの訪問者にこの名前は表示されません。

   ![「条件のシーケンスの情報を作成」セクション](/help/c-recommendations/c-algorithms/assets/criteria-sequence-info.png)

1. シーケンス内の複数の条件を使用して **[!UICONTROL Recommendations]** デザインを埋める場合は、公開される[!UICONTROL 一般表示タイトル]を入力します。このタイトルはページに表示されます。

   例えば、複数の[!UICONTROL レコメンデーション]キーに基づく品目がデザインに含まれている場合は、「これを見たお客様はこちらも...」を「お勧め」に置き換えることができます。

1. 条件のシーケンスの簡単な&#x200B;**[!UICONTROL 説明]**&#x200B;を入力します。

   説明は条件のシーケンスの特定に役立ちます。このシーケンスの目的に関する情報を含めることもできます。

1. 「**[!UICONTROL 業種]**」を選択します。

   Your default [industry vertical](/help/c-recommendations/c-algorithms/algorithms.md#section_936BCFCF234C49A2BEC1C38AAC2D71AF) appears automatically.

1. **[!UICONTROL ページタイプ]**&#x200B;を選択します。

   複数のページタイプを選択できます。

   業種とページタイプを共に使用して、保存した条件のシーケンスを分類し、他の [!UICONTROL Recommendations] アクティビティで簡単に再利用できるようにします。

## 条件のシーケンスの作成

シーケンスの順序は、デザインが入力される順序を定義します。 条件1にデザインを埋めるのに十分なレコメンデーションがない場合、残りのスロットは条件2などで埋められます。

1. 「 **[!UICONTROL 条件のシーケンス]** 」セクションで、「条件 **[!UICONTROL 」をクリックします]**。

   ![追加条件](/help/c-recommendations/c-algorithms/assets/add-criteria.png)

1. On the [!UICONTROL Select Criteria] screen, select a criteria.

   ![条件の選択](/help/c-recommendations/c-algorithms/assets/select-criteria.png)

1. 「**[!UICONTROL 追加]**」をクリックします。

1. シーケンスへの条件の追加を続けます。 1 つのシーケンスに最大 5 つの条件を追加できます。

## バックアップコンテンツの指定

デザインテンプレートに挿入するのに十分なレコメンデーションがない場合に返すコンテンツを選択します。

条件のシーケンスを作成すると、シーケンスを構成する個々の条件のバックアップレコメンデーションおよびデザインの部分レンダリング設定は無視されます。バックアップレコメンデーションとデザインの部分レンダリングを使用するには、それらをシーケンスに対して有効にする必要があります。適切なものに切り替えて選択します。バックアップレコメンデーションを許可すると、バックアップレコメンデーションにインクルージョンルールを適用するかどうかを選択することもできます。

![バックアップコンテンツの設定](/help/c-recommendations/c-algorithms/assets/backup-content-settings.png)

1. （オプション）「 **[!UICONTROL Partial Design Rendering]** 」トグルを「on」位置にスライドします。

   塗りつぶされるスロットはできるだけ多くありますが、デザインテンプレートに残りのスロット用の空白スペースが含まれる場合があります。

1. （オプション）「 **[!UICONTROL バックアップRecommendations]** 」を「オン」の位置に切り替えます。

   デザインの残りの空のスロットに、サイト全体から最も多く閲覧された製品をランダムに選択して入力します。

   詳しくは、「代替レコメンデーションの [使用](/help/c-recommendations/c-algorithms/backup-recs.md)」を参照してください。

1. （条件付き）前の手順で「 **[!UICONTROL Recommendationsのバックアップ]** 」を選択した場合は、「代替レコメンデーションにインクルージョンルールを **[!UICONTROL 適用する]**」を選択できます。

   For more information see [Use dynamic and static inclusion rules](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md).

1. 「**[!UICONTROL 保存]**」をクリックします。

   条件のシーケンスが条件リストに表示されます。

   ![](assets/CriteriaSequenceCard.png)

   レコメンデーションロジックのオプションについて詳しくは、[条件](../../c-recommendations/c-algorithms/algorithms.md#concept_4BD01DC437F543C0A13621C93A302750)を参照してください。

## トレーニングビデオ：Recommendations の条件の作成（12:33） ![チュートリアルバッジ](/help/assets/tutorial.png)

このビデオには、次の情報が含まれています。

* 条件の作成
* 条件のシーケンスの作成
* カスタム条件のアップロード

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
