---
keywords: A/B;アクティビティ指標;指標;指標の設定;目標の指標;アクティビティ設定;成功指標;コンバージョン;収益;エンゲージメント
description: 訪問が成功したタイミング（ [!DNL Adobe Target] 、[!UICONTROL Conversion]、[!UICONTROL Revenue] など）を判断するための [!UICONTROL Engagement]A/B アクティビティの指標を指定する方法を説明します。
title: A/B アクティビティで目標指標を設定するにはどうすればよいですか？
feature: A/B Tests
exl-id: 9e9e8787-c0cd-4aab-bd2d-0e9591e0a07d
source-git-commit: eb7e892a85fa3952ffc22172085d421756d0dfb5
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 62%

---

# 指標の設定

[!DNL Adobe Target] A/B アクティビティの指標を使用すると、訪問が成功したタイミングを判断できます。

成功指標について詳しくは、[成功指標](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)を参照してください。

1. **[!UICONTROL Reporting Settings]** のページの「**[!UICONTROL Goals & Settings]**」セクションで、[ 成功指標 ](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) を選択します

   ![成功指標を選択](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_metrics-new.png)

   「[!UICONTROL Select Metrics]」オプションには、アクティビティに対して選択できる成功指標が一覧表示されます。 成功指標は次のカテゴリに分類されます。

   * [!UICONTROL Conversion]
   * [!UICONTROL Revenue]
   * [!UICONTROL Engagement]

   あらかじめ用意されている成功指標を使用することも、カスタム成功指標を作成することもできます。成功指標を主要指標としてマークすることもできます。Reports カードおよび Experience Cloud カードは、主要指標が設定されている場合はデフォルトで主要指標を表示します。

1. 指標の設定を指定します。

   使用可能な設定は、使用する成功指標によって異なります。

   有効になっている場合は、「[!UICONTROL Estimated Value of the Conversion]」フィールド（[!UICONTROL Page Score] 指標では使用できません）には目標の値が表示されます。 この値を使用することで、[!DNL Target] は売上の推定上昇率を計算できます。このフィールドはオプションですが、このオプションがないと売上高以外の指標に関する売上の増分は計算できません。データタイプは通貨です。このフィールドは、ユーザーが目標を満たすためにとるアクションを指定した後、順次表示されます。詳しくは、「[売上高情報の予測](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)」を参照してください。

   成功指標の正しい設定は、期待するデータを確実に取得するために重要です。

   詳しくは [ 、成功指標 ](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) を参照してください。

1. （オプション）さらに指標を追加します。

指標に名前を付けたり、指標の名前を変更したりする場合、次の文字は使用できません。

| 文字 | 説明 |
|--- |--- |
| / | フォワードスラッシュ |
| ? | 疑問符 |
| # | 番号記号 |
| : | コロン |
| = | イコール |
| + | プラス |
| - | マイナス |
| @ | アットマーク |

## トレーニングビデオ：アクティビティ指標（7:43） ![ チュートリアルバッジ ](/help/main/assets/tutorial.png)

このビデオでは、成功指標に関する作業について説明します。

* 「目標」指標の理解
* コンバージョン、売上高、エンゲージメントの各指標の理解と作成
* クリック追跡指標の構築

>[!VIDEO](https://video.tv.adobe.com/v/17380)
