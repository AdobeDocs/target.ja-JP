---
keywords: エクスペリエンスのターゲット設定;xt;指標;指標の設定;目標の指標;アクティビティ設定;成功指標;コンバージョン;収益;エンゲージメント
description: ' [!DNL Adobe Target] [!UICONTROL Experience Targeting] アクティビティで指標を指定し、訪問が成功したタイミング（[!UICONTROL Conversion]、[!UICONTROL Revenue]、[!UICONTROL Engagement] など）を判断する方法を説明します。'
title: '[!UICONTROL Experience Targeting] アクティビティに目標指標を設定するにはどうすればよいですか？'
feature: Experience Targeting
exl-id: 16249930-8b9c-441c-bd14-5f32332556d2
source-git-commit: d7c1bbbbc8d1dcc45ac09a09f6b3be01f7542384
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 59%

---

# [!UICONTROL Experience Targeting] （XT）アクティビティでの指標の設定

[!DNL Adobe Target] [!UICONTROL Experience Targeting] （XT）アクティビティで指標を使用すると、訪問が成功したタイミングを判断できます。

成功指標について詳しくは、[成功指標](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)を参照してください。

1. アクティビティの目標を指定します。
1. [成功指標](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)を選択します。

   ![成功指標を選択](/help/main/c-activities/t-experience-target/t-xt-create/assets/ab_metrics-new.png)

   [!UICONTROL Select Metrics] のページには、アクティビティに対して選択できる成功指標が一覧表示されます。 成功指標は次のカテゴリに分類されます。

   * [!UICONTROL Conversion]
   * [!UICONTROL Revenue]
   * [!UICONTROL Engagement]

   事前に作成された成功指標を使用するか、カスタム成功指標を作成できます。 成功指標を主要指標としてマークすることもできます。Reports カードおよび Experience Cloud カードは、主要指標が設定されている場合はデフォルトで主要指標を表示します。
1. 指標の設定を指定します。

   使用できる設定は、使用している成功指標によって異なります。

   有効になっている場合は、「[!UICONTROL Estimated Value of the Conversion]」フィールド（[!UICONTROL Page Score] の指標では使用できません）には目標の値が表示されます。 この値を使用することで、[!DNL Target] は売上の推定上昇率を計算できます。このフィールドはオプションですが、このオプションがないと売上高以外の指標に関する売上の増分は計算できません。データタイプは通貨です。このフィールドは、ユーザーが目標を満たすためにとるアクションを指定した後、順次表示されます。詳しくは、「[売上高情報の予測](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)」を参照してください。

   期待するデータを確実に入手するためには、成功指標を正しく設定することが重要です。

   詳しくは [ 、成功指標 ](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) を参照してください。

1. （オプション）さらに指標を追加します。
1. 指標の設定が完了したら、「**[!UICONTROL Continue]**」をクリックします。

指標に名前を付けたり、指標の名前を変更したりする場合、次の文字は使用できません。

| 文字 | 説明 |
|--- |--- |
| `/` | フォワードスラッシュ |
| `?` | 疑問符 |
| `#` | 番号記号 |
| `:` | コロン |
| `=` | イコール |
| `+` | プラス |
| `-` | マイナス |
| `@` | アットマーク |

## トレーニングビデオ：アクティビティ指標（7:43） ![ チュートリアルバッジ ](/help/main/assets/tutorial.png)

このビデオでは、成功指標に関する作業について説明します。

* 「目標」指標の理解
* [!UICONTROL Conversion]、[!UICONTROL Revenue]、[!UICONTROL Engagement] の指標の理解と作成
* クリック追跡指標の構築

>[!VIDEO](https://video.tv.adobe.com/v/17380)
