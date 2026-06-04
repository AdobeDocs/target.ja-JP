---
keyword: traffic estimate;traffic estimator;estimate;traffic;confidence;statistical power;lift;bonferroni;conversion rate;visitors per day;duration
description: 「 [!DNL Adobe Target] [!UICONTROL 多変量テスト ]」アクティビティを成功させるために十分なトラフィックがあるかどうかを確認できるトラフィック見積もり機能の使用方法について説明します。
title: '[!UICONTROL 多変量テスト ] （MVT）アクティビティに必要なトラフィックの量'
feature: Multivariate Tests
exl-id: 2b32f4a7-b9b4-40bf-a17b-88225bc88787
TQID: https://experienceleague.adobe.com/XHBXV7Jtvp87ve4NTd-016E2dFkHTbPu-8-nY8GE-VM
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 530
ht-degree: 19%

---

# 成功した[!UICONTROL 多変量テスト ] アクティビティに必要なトラフィックの見積もり

多変量分析テストでは複数のエクスペリエンスを比較するので、有意な結果を得るためにはどの程度のトラフィックが必要かを把握しておくことが重要です。 [!UICONTROL  トラフィック見積もり]では、ページとテスト中のエクスペリエンスの数に関する統計を使用して、テストを成功させるために必要なトラフィック量とテスト期間を見積もります。

[!UICONTROL Traffic Estimator]は、以下を確実にするために必要なサンプルサイズを予測します。

* 95%の信頼性。 この統計は、実際の上昇率がない場合に偽陽性を報告する可能性が5% （100% – 信頼性レベル）であることを意味します。
* 統計的に80%のパワー。 この統計は、テストが25%以上の真のリフトを検出する80%の確率を持っていることを意味します。
* 25%の最低の信頼できる検出可能な上昇。 [!DNL Target]は、80%の可能性で25%以上の真のリフトを検出するために必要なトラフィック量を計算します。

このテストでは、ボンフェローニ補正を使用して、多重比較の補正をおこないます。 この方法は保守的な方法として知られていますが、確実に検出可能な最低上昇率を比較的大きく設定することで、バランスをとることができます。

また、[!UICONTROL  トラフィック見積もり]は、成功するために設計したテストに十分なトラフィックがあるかどうかを確認するためのフィードバックも提供します。

1. [!UICONTROL 多変量] アクティビティの[!UICONTROL Visual Experience Composer]の[!UICONTROL  エクスペリエンス ] ページから、[!UICONTROL  エクスペリエンス ] ページの左上隅にある&#x200B;**[!UICONTROL トラフィック]** アイコン（![ トラフィック見積もりアイコン ](/help/main/assets/icons/Gauge2.svg)）をクリックします。

   [!UICONTROL Traffic Estimator]が開きます。

   ![Traffic Estimator ユーザーインターフェイス ](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt-est.png)

   もう一度アイコンをクリックして、[!UICONTROL Traffic Estimator]を非表示にすることができます。

   [!UICONTROL Traffic Estimator]の上部付近で、入力した値が計算され、結果が表示されます。

1. （条件付き）一般的なコンバージョン率、1日あたりの推定訪問者数、テスト期間を提供します。

   * **[!UICONTROL コンテンツの組み合わせ数]**：除外後にアクティビティの一部として作成されたエクスペリエンスの数に基づいて自動的に計算されます。
   * **[!UICONTROL 一般的なコンバージョン率]**: コンバージョン率は、見積もりまたは分析システムからの過去のデータに基づいて、パーセントで表されます。
   * **[!UICONTROL 1日当たりの推定訪問者数]**：これは、ターゲティング条件に基づいてこのページを表示する可能性の高い訪問者の数です。 この数値は、分析データに基づいて決定することができます。
   * **[!UICONTROL テスト期間]**: アクティビティを実行する日数。

   [!UICONTROL Traffic Estimator]は、これらの統計を使用して、テストを成功させるために必要な調整を決定します。

   数値を変更すると、見積もりも変更されます。 例えば、多数のエクスペリエンスをテストしており、コンバージョン率とインプレッション率が低すぎる場合、[!UICONTROL  トラフィック見積もり]には、テストを成功させるために実行する必要がある期間が表示されます。 または、トラフィックが少ない場合は、[!UICONTROL Traffic Estimator]でエクスペリエンスの数が少ないことが示され、必要な日数でテストを実行できます。

   十分なトラフィックがない場合は、次のいずれかまたは両方をおこなうことができます。

   * オファーの組み合わせの数、および場所の数を減らします。
   * テスト期間を長くします。

   [!UICONTROL Traffic Estimator]で十分なトラフィックがあることが示されるまで数値を調整し、それに応じてテストを設計します。
