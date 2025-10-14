---
keyword: traffic estimate;traffic estimator;estimate;traffic;confidence;statistical power;lift;bonferroni;conversion rate;visitors per day;duration
description: ' [!DNL Adobe Target] [!UICONTROL Multivariate Test] アクティビティが成功するのに十分なトラフィックがあるかどうかを知ることができるトラフィック見積もりを使用する方法を説明します。'
title: '[!UICONTROL Multivariate Test] （MVT）アクティビティに必要なトラフィックはどれくらいですか？'
feature: Multivariate Tests
exl-id: 2b32f4a7-b9b4-40bf-a17b-88225bc88787
source-git-commit: 8f9c0ea65197fd639d463628e54db79db993c2da
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 21%

---

# [!UICONTROL Multivariate Test] アクティビティを成功させるために必要なトラフィックの見積もり

多変量分析テストでは複数のエクスペリエンスを比較するので、有意な結果を得るためにはどの程度のトラフィックが必要かを把握しておくことが重要です。この [!UICONTROL Traffic Estimator] では、ページとテストしているエクスペリエンスの数に関する統計を使用して、テストを成功させるために必要なトラフィックの量とテスト時間を見積もります。

この [!UICONTROL Traffic Estimator] では、以下を確実に行うために必要なサンプルサイズを予測します。

* 95% の信頼性。 この統計は、実際の上昇率がない場合に偽陽性とレポートされる可能性が 5% （100% – 信頼性レベル）であることを意味します。
* 80% の統計的検出力。 この統計は、テストが 25% 以上の真の上昇率を検出する確率が 80% であることを意味します。
* 25% 最小で確実に検出可能な上昇率。 [!DNL Target] は、真の上昇率が 25% 以上と 80% の確率を検出するために必要なトラフィック量を計算します。

このテストでは、ボンフェローニ補正を使用して、多重比較の補正をおこないます。この方法は保守的な方法として知られていますが、確実に検出可能な最低上昇率を比較的大きく設定することで、バランスをとることができます。

また、[!UICONTROL Traffic Estimator] は、成功するように設計したテストに十分なトラフィックがあるかどうかを知らせるフィードバックも提供します。

1. [!UICONTROL Experiences] アクティビティの [!UICONTROL Visual Experience Composer] の [!UICONTROL Multivariate] ページで、**[!UICONTROL Traffic]** ページの左上隅にある ![&#x200B; アイコン &#x200B;](/help/main/assets/icons/Gauge2.svg) トラフィック見積もりアイコン [!UICONTROL Experiences]）をクリックします。

   [!UICONTROL Traffic Estimator] が開きます。

   ![&#x200B; トラフィック見積もりユーザーインターフェイス &#x200B;](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt-est.png)

   アイコンをもう一度クリックすると、ア [!UICONTROL Traffic Estimator] ットを非表示にできます。

   [!UICONTROL Traffic Estimator] の上部付近で、入力した値が計算され、結果が表示されます。

1. （条件付き）一般的なコンバージョン率、1 日あたりの推定訪問者数およびテスト期間を指定します。

   * **[!UICONTROL Number of Content Combinations]**：除外の後にアクティビティの一部として作成されるエクスペリエンスの数に基づいて自動的に計算されます。
   * **[!UICONTROL Typical Conversion Rate]**：コンバージョン率は、Analytics システムからの推定または過去のデータに基づいてパーセンテージで表されます。
   * **[!UICONTROL Estimated Visitors Per Day]**：ターゲティング条件に基づいて、このページを表示する可能性が高い訪問者の数です。 この数値は、分析データに基づいて決定することができます。
   * **[!UICONTROL Test Duration]**：アクティビティを実行する日数。

   [!UICONTROL Traffic Estimator] では、これらの統計を使用して、テストを正常に実行するために必要な調整を決定します。

   数値を変更すると、見積もりも変更されます。例えば、多くのエクスペリエンスをテストし、コンバージョン率とインプレッション数が低すぎる場合、テストを成功させるためには、どの程度の期間 [!UICONTROL Traffic Estimator] テストを実行する必要があるかを示します。 または、トラフィックが少ない場合は、[!UICONTROL Traffic Estimator] が提案するエクスペリエンスの数が少なくなるので、目的の日数でテストを実行できます。

   十分なトラフィックがない場合は、次のいずれかまたは両方をおこなうことができます。

   * オファーの組み合わせの数、および場所の数を減らします。
   * テスト期間を長くします。

   [!UICONTROL Traffic Estimator] が十分なトラフィックがあることを示すまで数値を調整し、それに応じてテストを設計します。
