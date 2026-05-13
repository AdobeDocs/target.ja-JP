---
keywords: Traffic Estimator;Automated Personalization;ap；トラフィックの推定
description: '[!UICONTROL Traffic Estimator]を使用して、[!UICONTROL Automated Personalization] アクティビティが成功するのに十分なトラフィックがあるかどうかを評価します。'
title: '[!UICONTROL Automated Personalization] アクティビティを成功させるために必要なトラフィックの量'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Automated Personalization
exl-id: 11f9e239-700b-45cd-bf77-39f7f8967a2e
TQID: https://experienceleague.adobe.com/rLjNgDlAWK-r9Zv7083vo-PdWTPy3aHGS4fXEGeTdnY
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 730
ht-degree: 12%

---

# 成功のために必要なトラフィックの見積もり

[!DNL Adobe Target] [!UICONTROL Traffic Estimator]は、[!UICONTROL Automated Personalization] （AP）アクティビティを成功させるのに十分なトラフィックがあるかどうかを確認するためのフィードバックを提供します。

[!UICONTROL Automated Personalization]のアクティビティでは複数のオファーの組み合わせを使用するため、有意義な結果を提供するために必要なトラフィック量を把握することが重要です。 [!UICONTROL Traffic Estimator]は、ページとテスト中のエクスペリエンスの数に関する統計を使用して、アクティビティを成功させるために必要なトラフィック量とテスト期間を推定します。

[!UICONTROL Traffic Estimator]は、推定されるページのインプレッション数とページの一般的なコンバージョン率を比較することで、パーソナライズされたモデルを生成するのに十分なトラフィックがあるかどうかを判断します。 アクティビティの成功のためには、パーソナライズされたコンテンツがアクティビティ期間の 50％以内または 14 日以内（どちらか短い方）に準備されるようなサンプルサイズにするのが理想的です。 このプロセスにより、パーソナライズされたコンテンツを入手し、どのようなコンテンツを配信すべきかを学ぶのに十分な時間を確保できます。

パーソナライゼーションアルゴリズムが構築されるまで、[!DNL Target]はランダムにエクスペリエンスを提供します。 各オファーの横にあるチェックマークアイコンは、そのオファーのモデルの準備が完了し、[!DNL Target]がパーソナライズされたコンテンツの配信を開始できるタイミングを示します。 上昇率はモデルの準備が整った後にのみ予想されるため、視覚的な表示により適切な期待を設定できます。 [!UICONTROL Visual Experience Composer] （VEC）の[!UICONTROL Traffic Estimator]を使用して、モデルの準備が整ったときのガイドラインを取得します。

## Traffic Estimatorの使用

1. [!UICONTROL Automated Personalization] アクティビティの[!UICONTROL Visual Experience Composer]の[!UICONTROL Experiences] ページから、[!UICONTROL Experiences] ページの左上隅にある&#x200B;**[!UICONTROL Traffic]** アイコン （![&#x200B; トラフィック見積もりアイコン &#x200B;](/help/main/assets/icons/Gauge2.svg)）をクリックします。

   [!UICONTROL Traffic Estimator]が開きます。

   ![Traffic Estimator ユーザーインターフェイス &#x200B;](assets/ap-est.png)

   アイコンをもう一度クリックすると、[!UICONTROL Traffic Estimator]を非表示にできます。

1. 一般的なコンバージョン率（またはこのアクティビティから期待されるコンバージョン率）、1日あたりの推定アクティビティインプレッション数、テスト期間を指定します。

   | 指標 | 説明 |
   | --- | --- |
   | **[!UICONTROL Number of Offers]** | この指標は、除外後、アクティビティの一部として作成されたエクスペリエンスの数に基づいて自動的に計算されます。 |
   | **[!UICONTROL Typical Conversion Rate]** | この指標は、見積もりや分析システムからの過去のデータにもとづいて、パーセントで表されます。 |
   | **[!UICONTROL Estimated Visits Per Day]** | この指標は、ターゲティング条件に基づいて、アクティビティを表示できる訪問者からの1日あたりの訪問数です。 この指標は分析データにもとづいて算出することができます。 この番号はユニーク訪問者ではなく、訪問者数である必要があります。 |
   | **[!UICONTROL Test Duration]** | アクティビティを実行する日数です。 |

   [!UICONTROL Traffic Estimator]は、これらの指標を使用して、テストを成功させるために必要な調整を決定します。

   [!UICONTROL Traffic Estimator]の上部付近で、入力した値が計算され、結果が表示されます。

   ![値と結果が表示されたトラフィックの見積もり](assets/ap-est-no.png)

   数値を変更すると、見積もりも変更されます。 例えば、多くの組み合わせをテストしており、コンバージョン率とインプレッション率が低すぎる場合、[!UICONTROL Traffic Estimator]は、テストを成功させるためにどれくらいの期間テストを実行する必要があるかを示します。 または、トラフィックが少ない場合は、[!UICONTROL Traffic Estimator]により、オファーの組み合わせ数が少ないことが提案され、希望する日数でテストを実行できます。

   十分なトラフィックがない場合は、次の点を考慮してください。

   * 1つのエクスペリエンスのバリエーションで複数のオファーの変更を含むエクスペリエンスを作成するには、[!UICONTROL Automated Personalization]ではなく[[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) アクティビティを使用することを検討してください。
   * [!UICONTROL Automated Personalization] アクティビティ内のオファーの組み合わせ数を減らします。
   * アクティビティの実行期間を長くします。

   [!UICONTROL Traffic Estimator]が十分なトラフィックがあることを示すまで数値を調整し、それに応じてテストを設計します。

   十分なトラフィック メッセージを示す![&#x200B; トラフィック見積もり](assets/ap-est-yes.png)

   トラフィックが十分な場合、[!UICONTROL Traffic] アイコンに緑色のチェックが表示されます。 トラフィックが不十分な場合は、赤の警告ラベルが表示されます。

## Traffic Estimatorに関するよくある質問

[!UICONTROL Traffic Estimator]を操作する際には、次のFAQを検討してください。

### AP アクティビティに十分なトラフィックがあるにもかかわらず、パーソナライズされたモデルが構築されないのはなぜですか？

特定の状況では、トラフィックはパーソナライズされたモデルを構築するのに十分な大きさになりますが、そのトラフィックは、パーソナライズされたモデルとランダムの間に意味のある違いがないことを[!DNL Target]に通知する可能性があります。 モデルは[!DNL Target]に組み込まれてテストされていますが、モデルがランダムよりも優れているわけではないため、デプロイされません。

モデルがランダムよりも優れていない理由として、オファーが互いに十分に異なっていないことが考えられます。 その場合は、メッセージが類似している場合は、オファーをより視覚的に異なるように設定するか、メッセージ自体を変更してみます。
