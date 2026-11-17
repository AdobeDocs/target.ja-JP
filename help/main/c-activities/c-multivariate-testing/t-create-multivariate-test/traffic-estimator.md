---
keywords: Traffic Estimator;Traffic Estimator;Estimator;Traffic;Confidence；統計的パワー；リフト；bonferroni；コンバージョン率；1日あたりの訪問者；期間
description: '[!DNL Adobe Target] [!UICONTROL 多変量テスト &#x200B;] アクティビティを成功させるために十分なトラフィックがあるかどうかを知らせるトラフィック見積もり機能の使用方法について説明します。'
title: '[!UICONTROL 多変量テスト &#x200B;] （MVT）アクティビティに必要なトラフィックの量'
feature: Multivariate Tests
exl-id: 2b32f4a7-b9b4-40bf-a17b-88225bc88787
TQID: 'https://experienceleague.adobe.com/XHBXV7Jtvp87ve4NTd-016E2dFkHTbPu-8-nY8GE-VM'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: b934e7cf-c07f-5a64-924b-3c9da8413e3d
    internal-label: Multivariate Tests
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 0ae6991a6a86854bd64a632070a1fcbe544cc606
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 8%
---
# 成功した[!UICONTROL 多変量テスト &#x200B;] アクティビティに必要なトラフィックの見積もり {#traffic-estimator}

>[!BEGINSHADEBOX]

**このページで：** **[!UICONTROL Traffic Estimator]**&#x200B;を使用して、**[!UICONTROL 多変量テスト]** アクティビティが成功するのに十分なトラフィックを持っているかどうかを確認する方法を説明します。

>[!ENDSHADEBOX]

多変量テストは複数のエクスペリエンスを比較するため、有意義な結果を得るためにどれだけのトラフィックが必要かを把握することが重要です。 **[!UICONTROL トラフィック見積もり]**&#x200B;では、ページとテスト中のエクスペリエンスの数に関する統計を使用して、テストを成功させるために必要なトラフィック量とテスト期間を見積もります。 また、成功するために設計したテストに十分なトラフィックがあるかどうかを確認するためのフィードバックも提供されます。

**[!UICONTROL Traffic Estimator]**&#x200B;は、以下を確実にするために必要なサンプルサイズを予測します。

* **95%の信頼性。** この統計は、実際の上昇率がない場合に偽陽性を報告する可能性が5% （100% – 信頼性レベル）であることを意味します。
* **80%の統計的検出力。** この統計は、テストが25%以上の真のリフトを検出する80%の確率を持っていることを意味します。
* **25%以上の信頼性検出可能な上昇率。** [!DNL Target]は、80%の可能性で25%以上の真のリフトを検出するために必要なトラフィック量を計算します。

このテストでは、ボンフェローニ補正を使用して、多重比較の補正をおこないます。 この方法は保守的な方法として知られていますが、確実に検出可能な最低上昇率を比較的大きく設定することで、バランスをとることができます。

## Traffic Estimatorの使用 {#use-traffic-estimator}

**[!UICONTROL 多変量テスト]**&#x200B;をデザインする際、**[!UICONTROL トラフィック見積もり]**&#x200B;を使用すると、テストするエクスペリエンスの数に対して、ページへのトラフィックが十分かどうかを確認できます。 テストを開始する前にこのチェックを実行すると、意味のある結果を生成するのに十分な訪問者に到達できないテストを回避できます。また、トラフィックが十分でない場合の組み合わせ数またはテストの期間を調整する方法を示します。

1. **[!UICONTROL 多変量]** アクティビティの&#x200B;**[!UICONTROL Visual Experience Composer]**&#x200B;の&#x200B;**[!UICONTROL エクスペリエンス]** ページで、ページの左上隅にある&#x200B;**[!UICONTROL トラフィック]** アイコン （![&#x200B; トラフィック見積もりアイコン &#x200B;](/help/main/assets/icons/Gauge2.svg)）をクリックします。

   **[!UICONTROL Traffic Estimator]**&#x200B;が開きます。 非表示にするには、もう一度アイコンをクリックします。

   ![Traffic Estimator ユーザーインターフェイス &#x200B;](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt-est.png)

   **[!UICONTROL Traffic Estimator]**&#x200B;の上部付近で、入力した値が計算され、結果が表示されます。

1. （オプション）一般的なコンバージョン率、1日あたりの推定訪問者数、テスト期間を指定します。

   **[!UICONTROL Traffic Estimator]**&#x200B;は、これらの統計を使用して、テストを成功させるために必要な調整を決定します。

   | 指標 | 説明 |
   | --- | --- |
   | **[!UICONTROL コンテンツの組み合わせ数]** | この指標は、除外後、アクティビティの一部として作成されたエクスペリエンスの数に基づいて自動的に計算されます。 |
   | **[!UICONTROL 一般的なコンバージョン率]** | この指標は、見積もりや分析システムからの過去のデータにもとづいて、パーセントで表されます。 |
   | **[!UICONTROL 1日あたりの推定訪問者数]** | ターゲティング基準をもとに、このページを閲覧する可能性の高い訪問者の数を指します。 この数値は分析データにもとづく可能性があります。 |
   | **[!UICONTROL テスト期間]** | アクティビティを実行する日数。 |

1. 結果の検証： 数値を変更すると、見積もりも変更されます。

   例えば、多数のエクスペリエンスをテストしており、コンバージョン率とインプレッション率が低すぎる場合、**[!UICONTROL トラフィック見積もり]**&#x200B;には、テストを成功させるために実行する必要がある期間が表示されます。 または、トラフィックが少ない場合は、**[!UICONTROL Traffic Estimator]**&#x200B;でエクスペリエンスの数が少ないことが示され、必要な日数のテストを実行できます。

1. 十分なトラフィックがない場合は、次のいずれかまたは両方を実行します。

   * オファーの組み合わせの数、および場所の数を減らします。
   * テスト期間を長くします。

1. **[!UICONTROL Traffic Estimator]**&#x200B;で十分なトラフィックがあることが示されるまで数値を調整し、それに応じてテストを設計します。
