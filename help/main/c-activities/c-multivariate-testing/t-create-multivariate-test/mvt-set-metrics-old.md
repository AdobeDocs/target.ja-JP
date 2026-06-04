---
keywords: 多変量分析;mvt;指標;指標の設定;目標指標;アクティビティ設定;成功指標;コンバージョン;売上高;エンゲージメント
description: '[!UICONTROL  コンバージョン ]、[!UICONTROL 収益]、[!UICONTROL  エンゲージメント ]など、訪問が成功したかどうかを判断するために、 [!DNL Adobe Target] [!UICONTROL 多変量テスト ] アクティビティで指標を指定する方法について説明します。'
title: '[!UICONTROL 多変量テスト ] （MVT）アクティビティで目標の指標を設定するにはどうすればよいですか？'
feature: Multivariate Tests
exl-id: 8530b3f1-5daa-4a03-a482-93b10eb23208
source-git-commit: 8f9c0ea65197fd639d463628e54db79db993c2da
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 60%

---

# [!UICONTROL 多変量テスト ] アクティビティの指標を設定

[!DNL Adobe Target] [!UICONTROL 多変量テスト ]で指標を使用して、訪問が成功したかどうかを判断します。

成功指標について詳しくは、[成功指標](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)を参照してください。

1. アクティビティの目標を指定します。
1. [成功指標](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)を選択します。

   ![指標リストを設定](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt_metrics-list.png)

   [!UICONTROL 指標の選択] ページには、アクティビティに選択できる成功指標が一覧表示されます。 成功指標は次のカテゴリに分類されます。

   * [!UICONTROL コンバージョン]
   * [!UICONTROL 売上高]
   * [!UICONTROL エンゲージメント]

   あらかじめ用意されている成功指標を使用することも、カスタム成功指標を作成することもできます。 成功指標を主要指標としてマークすることもできます。 Reports カードおよび Experience Cloud カードは、主要指標が設定されている場合はデフォルトで主要指標を表示します。

1. 指標の設定を指定します。

   使用可能な設定は、使用している成功指標によって異なります。

   有効にした場合、「[!UICONTROL  コンバージョンの見積もり値]」フィールド（[!UICONTROL  ページスコア ]指標では使用できません）は、目標の値を提供します。 この値を使用することで、[!DNL Target] は売上の推定上昇率を計算できます。 このフィールドはオプションですが、このオプションがないと売上高以外の指標に関する売上の増分は計算できません。 データタイプは通貨です。 このフィールドは、ユーザーが目標を満たすためにとるアクションを指定した後、順次表示されます。 詳しくは、「[売上高情報の予測](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)」を参照してください。

   期待するデータを確実に入手するためには、成功指標を正しく設定することが重要です。

   詳しくは、[成功指標](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)を参照してください。

1. （オプション）さらに指標を追加します。
1. 指標の設定が完了したら、**[!UICONTROL 続行]**&#x200B;をクリックします。

指標に名前を付けたり、名前を変更したりする場合、次の文字は使用できません。

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
* [!UICONTROL  コンバージョン ]、[!UICONTROL 収益]、[!UICONTROL  エンゲージメント ]の指標を理解して構築する
* クリック追跡指標の構築

>[!VIDEO](https://video.tv.adobe.com/v/17380)
