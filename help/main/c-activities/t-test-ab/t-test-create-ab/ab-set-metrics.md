---
keywords: A/B;アクティビティ指標;指標;指標の設定;目標の指標;アクティビティ設定;成功指標;コンバージョン;収益;エンゲージメント
description: A/B アクティビティで指標を設定して、[!UICONTROL Conversion]、[!UICONTROL Revenue]、[!UICONTROL Engagement]などの訪問の成功を判断する方法について説明します。
title: A/B アクティビティで目標指標を設定するにはどうすればよいですか？
feature: A/B Tests
exl-id: 9e9e8787-c0cd-4aab-bd2d-0e9591e0a07d
TQID: https://experienceleague.adobe.com/WE27AidwrwYLn-ZlnpxKNfOG2jT07iPYztdrovRl0Qk
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 286
ht-degree: 61%

---

# 指標の設定

[!DNL Adobe Target]のA/B アクティビティで指標を使用して、訪問が成功したタイミングを判断します。

成功指標について詳しくは、[成功指標](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)を参照してください。

1. **[!UICONTROL Goals & Settings]** ページの&#x200B;**[!UICONTROL Reporting Settings]** セクションで、[成功指標](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)を選択します。

   [!UICONTROL Select Metrics] オプションには、アクティビティに選択できる成功指標が一覧表示されます。 成功指標は次のカテゴリに分類されます。

   * [!UICONTROL Conversion]
   * [!UICONTROL Revenue]
   * [!UICONTROL Engagement]

   あらかじめ用意されている成功指標を使用することも、カスタム成功指標を作成することもできます。 成功指標を主要指標としてマークすることもできます。 Reports カードおよび Experience Cloud カードは、主要指標が設定されている場合はデフォルトで主要指標を表示します。

1. 指標の設定を指定します。

   使用可能な設定は、使用する成功指標によって異なります。

   有効にした場合、[!UICONTROL Estimated Value of the Conversion] フィールド（[!UICONTROL Page Score]指標では使用できません）は、目標の値を提供します。 この値を使用することで、[!DNL Target] は売上の推定上昇率を計算できます。 このフィールドはオプションですが、このオプションがないと売上高以外の指標に関する売上の増分は計算できません。 データタイプは通貨です。 このフィールドは、ユーザーが目標を満たすためにとるアクションを指定した後、順次表示されます。 詳しくは、「[売上高情報の予測](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)」を参照してください。

   成功指標の適切な設定は、期待するデータを確実に取得するために不可欠です。

   詳しくは [ 、成功指標 ](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) を参照してください。

1. （オプション）さらに指標を追加します。

指標に名前を付けたり、名前を変更したりする場合、次の文字は使用できません。

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
