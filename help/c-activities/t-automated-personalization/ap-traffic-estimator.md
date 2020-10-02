---
keywords: traffic estimator;automated personalization;ap
description: トラフィック見積もりでは、Adobe Targetアクティビティが成功するのに十分なトラフィックがあるかどうかを知らせるフィードバックを提供します。
title: 成功のために必要なトラフィックの見積もり
feature: ap
topic: Standard
uuid: 9961ebaa-8761-431d-9605-852025ca580f
translation-type: tm+mt
source-git-commit: df9cb5c4a3cd44917ee9136300e4ad68f922d3c9
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 22%

---


# ![PREMIUM](/help/assets/premium.png) 成功のために必要なトラフィックの見積もり{#estimate-the-traffic-required-for-success}

[!UICONTROL トラフィック見積もりには] 、 [!DNL Adobe Target] アクティビティが成功するのに十分なトラフィックがあるかどうかを知らせるフィードバックが表示されます。

[!UICONTROL Automated Personalization] アクティビティでは複数のオファーの組み合わせを使用するので、有意義な結果を得るために必要なトラフィック量を知ることが重要です。 The [!UICONTROL Traffic Estimator] uses statistics about your page and the number of experiences being tested to estimate the amount of traffic and the test duration needed to make the activity successful.

The [!UICONTROL Traffic Estimator] determines if there is enough traffic to generate personalized models, by comparing the estimated page impressions and typical conversion rate for the pages. アクティビティの成功のためには、パーソナライズされたコンテンツがアクティビティ期間の 50％以内または 14 日以内（どちらか短い方）に準備されるようなサンプルサイズにするのが理想的です。これにより、パーソナライズされたコンテンツの取得と、配信するコンテンツの学習に十分な時間を確保できます。

Remember that [!DNL Target] randomly serves experiences until the personalization algorithms are built. The checkmark icon beside each offer shows when the model for that offer is ready and [!DNL Target] is able to begin delivering personalized content. モデルが準備完了になった後にのみ指標の上昇が期待されるので、視覚的な表示によって、適切に予想を立てることができます。Use the [!UICONTROL Traffic Estimator] in the [!UICONTROL Visual Experience Composer] (VEC) to get a guideline of when the models will be ready.

## トラフィック見積もりの使用

1. From the [!UICONTROL Visual Experience Composer], click **[!UICONTROL Traffic]**.

   ![トラフィックアイコン](/help/c-activities/t-automated-personalization/assets/icon-traffic.png)

   The [!UICONTROL Traffic Estimator] opens. You can click **[!UICONTROL Traffic]** again to hide the [!UICONTROL Traffic Estimator].

   ![](assets/ap_est.png)

1. 標準コンバージョン率（このアクティビティで期待できるコンバージョン率）、アクティビティの 1 日あたりの推定インプレッション数、テスト期間を確認できます。

   * **オファー数**:除外後にアクティビティの一部として作成されるエクスペリエンスの数に基づいて自動的に計算されます。
   * **一般的なコンバージョン率**:コンバージョン率は、見積もりまたは分析システムの過去のデータに基づいて、割合で表されます。
   * **1日あたりの予想訪問数**:ターゲット条件に基づいて、アクティビティを表示できる訪問者からの1日あたりの訪問回数です。 この数値は、分析データに基づいて決定することができます。この数値は実訪問者数ではなく、訪問数であることにご注意ください。
   * **テスト期間**：アクティビティを実行する日数です。

   The [!UICONTROL Traffic Estimato]r uses these statistics to determine what adjustments are needed to run a successful test.

   Near the top of the [!UICONTROL Traffic Estimator], the values you entered are calculated and the results are shown.

   ![](assets/ap_est_no.png)

   数値を変更すると、見積もりも変更されます。For example, if you are testing a large number of combinations and your conversion rate and impressions are too low, the [!UICONTROL Traffic Estimator] shows how long the test will need to run to be successful. Or, if your traffic is low, the [!UICONTROL Traffic Estimator] might suggest a lower number of offer combinations so you can run the test the desired number of days.

   十分なトラフィックがない場合は、次のいずれかまたはすべてをおこなうことができます。

   * Consider using an [Auto-Target](/help/c-activities/auto-target-to-optimize.md) activity instead of [!UICONTROL Automated Personalization] to create experiences with several offer changes in one experience variation.
   * [!UICONTROL Automated Personalization] アクティビティ内のオファーの組み合わせの数を減らします。
   * アクティビティの実行期間を長くします。

   Adjust the numbers until the [!UICONTROL Traffic Estimator] says you have sufficient traffic, then design your test accordingly.

   ![](assets/ap_est_yes.png)

   If the traffic is sufficient, the [!UICONTROL Traffic] icon shows a green check. トラフィックが不十分な場合は、赤の警告ラベルが表示されます。

## トラフィック見積もりに関するよくある質問(FAQ)

ト [!UICONTROL ラフィック見積もりを使用する際は、次のFAQについて考慮してください]。

### APアクティビティに十分なトラフィックがある場合に、パーソナライズされたモデルが [!DNL Target] 作成されないのはなぜですか。

状況によっては、パーソナライズされたモデルを作成するのに十分なトラフィック量がある場合がありますが、そのトラフィックは、パーソナライズされたモデルとランダム [!DNL Target] の間に意味のある違いがないことを通知する場合があります。 モデルは組み込み [!DNL Target] テストされていますが、モデルはランダムよりも大幅に優れていないので、配置されません。

モデルがランダム以上に良くならない原因として考えられるのは、オファーが互いに大きく異なっていないことです。 その場合は、メッセージングが類似している場合にオファーをより視覚的に異なるものにするか、メッセージング自体を変更してみることができます。
