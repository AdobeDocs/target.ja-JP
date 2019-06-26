---
description: 多変量分析テストの指標を使用して、訪問が成功かどうかを判断します。
keywords: 多変量分析;mvt;指標;指標の設定;目標指標;アクティビティ設定;成功指標;コンバージョン;売上高;エンゲージメント
seo-description: 多変量分析テストの指標を使用して、訪問が成功かどうかを判断します。
seo-title: 指標の設定
solution: Target,standard
title: 指標の設定
uuid: 0fb297ba-f1c3-4139-ac37-7fa0bf2ac308
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# 指標の設定{#set-metrics}

多変量分析テストの指標を使用して、訪問が成功かどうかを判断します。

成功指標について詳しくは、[成功指標](../../../c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)を参照してください。

1. アクティビティの目標を指定します。
1. [成功指標](../../../c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)を選択します。

   ![指標リストの設定](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt_metrics-list.png)

   [!UICONTROL 成功指標]ページには、アクティビティ用に選択できる成功指標の一覧が表示されます。成功指標は次のカテゴリに分類されます。

   * コンバージョン
   * 売上高
   * エンゲージメント
   あらかじめ用意されている成功指標を使用することも、カスタム成功指標を作成することもできます。成功指標を主要指標としてマークすることもできます。Reports カードおよび Experience Cloud カードは、主要指標が設定されている場合はデフォルトで主要指標を表示します。
1. 指標の設定を指定します。

   使用可能な設定は、使用する成功指標によって異なります。

   [!UICONTROL 「コンバージョンの予測値」]フィールドを有効にすると（ページスコア指標では使用できません）、目標の値が提供されます。この値を使用することで、Target は売上の推定上昇率を計算できます。このフィールドはオプションですが、このオプションがないと売上高以外の指標に関する売上の増分は計算できません。データタイプは通貨です。このフィールドは、ユーザーが目標を満たすためにとるアクションを指定した後、順次表示されます。詳しくは、「[売上高情報の予測](../../../administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md#concept_32F875D8F91349CE86AF391F65BEAEEE)」を参照してください。

   期待するデータを確実に入手するためには、成功指標を正しく設定することが重要です。

   For more information, see [Success Metrics](../../../c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)
1. （オプション）さらに指標を追加します。
1. 指標の設定が終了したら、「**[!UICONTROL 続行]**」をクリックします。
指標に名前を付けたり、名前を変更したりする場合、以下の文字は使用できないことに注意してください。

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

## トレーニングビデオ：アクティビティ指標（7:43）

このビデオでは、成功指標に関する作業について説明します。

* 「目標」指標の理解
* コンバージョン、収益、エンゲージメントの指標の理解と構築
* クリック追跡指標の構築

>[!VIDEO](https://video.tv.adobe.com/v/17380?captions=jpn)
