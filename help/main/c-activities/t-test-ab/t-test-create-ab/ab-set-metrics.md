---
keywords: A/B;アクティビティ指標;指標;指標の設定;目標の指標;アクティビティ設定;成功指標;コンバージョン;収益;エンゲージメント
description: 指標を指定するAdobe [!DNL Target] コンバージョン、売上高、エンゲージメントなど、訪問が成功かどうかを判断する A/B アクティビティ。
title: A/B アクティビティで目標指標を設定する方法を教えてください。
feature: A/B Tests
exl-id: 9e9e8787-c0cd-4aab-bd2d-0e9591e0a07d
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 85%

---

# 指標の設定

指標を [!DNL Adobe Target] 訪問が成功したタイミングを判断する A/B アクティビティ。

成功指標について詳しくは、[成功指標](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)を参照してください。

1. アクティビティの目標を指定します。
1. [成功指標](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)を選択します。

   ![成功指標を選択](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_metrics-new.png)

   [!UICONTROL 成功指標]ページには、アクティビティ用に選択できる成功指標の一覧が表示されます。成功指標は次のカテゴリに分類されます。

   * コンバージョン
   * 売上高
   * エンゲージメント

   あらかじめ用意されている成功指標を使用することも、カスタム成功指標を作成することもできます。成功指標を主要指標としてマークすることもできます。Reports カードおよび Experience Cloud カードは、主要指標が設定されている場合はデフォルトで主要指標を表示します。
1. 指標の設定を指定します。

   使用可能な設定は、使用する成功指標によって異なります。

   [!UICONTROL 「コンバージョンの予測値」]フィールドを有効にすると（ページスコア指標では使用できません）、目標の値が提供されます。この値を使用することで、Target は売上の推定上昇率を計算できます。このフィールドはオプションですが、このオプションがないと売上高以外の指標に関する売上の増分は計算できません。データタイプは通貨です。このフィールドは、ユーザーが目標を満たすためにとるアクションを指定した後、順次表示されます。詳しくは、「[売上高情報の予測](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)」を参照してください。

   期待するデータを確実に入手するためには、成功指標を正しく設定することが重要です。

   詳しくは [ 、成功指標 ](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) を参照してください。
1. （オプション）さらに指標を追加します。
1. 指標の設定が終了したら、「**[!UICONTROL 続行]**」をクリックします。

指標に名前を付けたり、名前を変更したりする場合、以下の文字は使用できないことに注意してください。

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

## トレーニングビデオ：アクティビティ指標（7:43）![チュートリアルバッジ](/help/main/assets/tutorial.png)

このビデオでは、成功指標に関する作業について説明します。

* 「目標」指標の理解
* コンバージョン、売上高、エンゲージメントの各指標の理解と作成
* クリック追跡指標の構築

>[!VIDEO](https://video.tv.adobe.com/v/17380)