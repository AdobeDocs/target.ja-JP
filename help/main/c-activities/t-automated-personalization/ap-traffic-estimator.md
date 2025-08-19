---
keywords: トラフィック見積もり；automated personalization;ap；トラフィックの見積もり
description: '[!UICONTROL Traffic Estimator] を使用して、[!UICONTROL Automated Personalization] のアクティビティが成功するだけの十分なトラフィックがあるかどうかを評価します。'
title: '[!UICONTROL Automated Personalization] アクティビティを成功させるにはどの程度のトラフィックが必要ですか？'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Automated Personalization
exl-id: 11f9e239-700b-45cd-bf77-39f7f8967a2e
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '721'
ht-degree: 11%

---

# 成功のために必要なトラフィックの見積もり

[!DNL Adobe Target] [!UICONTROL Traffic Estimator] は、[!UICONTROL Automated Personalization] （AP）アクティビティを成功させるために十分なトラフィックがあるかどうかを知ることができるフィードバックを提供します。

アクティビティ [!UICONTROL Automated Personalization] は複数のオファーの組み合わせを使用するので、有意義な結果を得るためにどの程度のトラフィックが必要かを知ることが重要です。 この [!UICONTROL Traffic Estimator] では、ページとテストしているエクスペリエンスの数に関する統計を使用して、トラフィックの量と、アクティビティを成功させるために必要なテスト期間を推定します。

[!UICONTROL Traffic Estimator] は、予測されるページインプレッション数とページの一般的なコンバージョン率を比較することにより、パーソナライズされたモデルを生成できるだけのトラフィックがあるかどうかを判断します。 アクティビティの成功のためには、パーソナライズされたコンテンツがアクティビティ期間の 50％以内または 14 日以内（どちらか短い方）に準備されるようなサンプルサイズにするのが理想的です。このプロセスでは、パーソナライズされたコンテンツを取得し、配信するコンテンツを学習するのに十分な時間がかかります。

パーソナライゼーションアルゴリズム [!DNL Target] 作成されるまで、エクスペリエンスがランダムに提供されることに注意してください。 各オファーの横にあるチェックマークアイコンは、そのオファーのモデルの準備が整い、パーソナライズされ [!DNL Target] コンテンツの配信を開始できるタイミングを示します。 上昇率はモデルの準備が整った後にのみ期待されるので、視覚的な表示によって適切な期待値を設定できます。 [!UICONTROL Traffic Estimator] （VEC）の [!UICONTROL Visual Experience Composer] を使用して、モデルの準備が整ったタイミングのガイドラインを取得します。

## トラフィック見積もりを使用

1. [!UICONTROL Experiences] アクティビティの [!UICONTROL Visual Experience Composer] の [!UICONTROL Automated Personalization] ページで、**[!UICONTROL Traffic]** ページの左上隅にある ![ アイコン ](/help/main/assets/icons/Gauge2.svg) トラフィック見積もりアイコン [!UICONTROL Experiences]）をクリックします。

   [!UICONTROL Traffic Estimator] が開きます。

   ![ トラフィック見積もりユーザーインターフェイス ](assets/ap-est.png)

   アイコンをもう一度クリックすると、ア [!UICONTROL Traffic Estimator] ットを非表示にできます。

1. 一般的なコンバージョン率（または、このアクティビティから予測されるコンバージョン率）、1 日あたりの推定アクティビティインプレッション数、およびテスト期間を指定します。

   | 指標 | 説明 |
   | --- | --- |
   | **[!UICONTROL Number of Offers]** | この指標は、除外の後、アクティビティの一部として作成されたエクスペリエンスの数に基づいて自動的に計算されます。 |
   | **[!UICONTROL Typical Conversion Rate]** | この指標は、分析システムからの推定または過去のデータに基づいて割合で表されます。 |
   | **[!UICONTROL Estimated Visits Per Day]** | この指標は、ターゲティング条件に基づいて、アクティビティを表示できる訪問者の 1 日あたりの訪問回数です。 この指標は、分析データに基づいている可能性があります。 この数は、ユニーク訪問者ではなく、訪問数にする必要があります。 |
   | **[!UICONTROL Test Duration]** | アクティビティを実行する日数です。 |

   [!UICONTROL Traffic Estimator] では、これらの指標を使用して、テストを正常に実行するために必要な調整を判断します。

   [!UICONTROL Traffic Estimator] の上部付近で、入力した値が計算され、結果が表示されます。

   ![ 値と結果を表示したトラフィックの見積もり ](assets/ap-est-no.png)

   数値を変更すると、見積もりも変更されます。例えば、テストする組み合わせが多く、コンバージョン率とインプレッション数が低すぎる場合、テストを成功させるためには、テストを実行する必要がある期間を [!UICONTROL Traffic Estimator] に示します。 または、トラフィックが少ない場合は、オファーの組み合わせの数を減らして、目的の日数で [!UICONTROL Traffic Estimator] ストを実行できるようにすることも可能です。

   十分なトラフィックがない場合は、次の点を考慮してください。

   * [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) の代わりに [!UICONTROL Automated Personalization] アクティビティを使用して、1 つのエクスペリエンスのバリエーション内で、複数のオファーの変更を含むエクスペリエンスを作成することを検討してください。
   * [!UICONTROL Automated Personalization] アクティビティ内のオファーの組み合わせの数を減らします。
   * アクティビティの実行期間を長くします。

   [!UICONTROL Traffic Estimator] が十分なトラフィックがあることを示すまで数値を調整し、それに応じてテストを設計します。

   ![ 十分なトラフィックメッセージを示すトラフィック見積もり ](assets/ap-est-yes.png)

   トラフィックが十分な場合、[!UICONTROL Traffic] のアイコンは緑色のチェックを示します。 トラフィックが不十分な場合は、赤の警告ラベルが表示されます。

## トラフィック見積もりに関するよくある質問（Faq）

[!UICONTROL Traffic Estimator] を使用する際は、次の FAQ を考慮してください。

### AP アクティビティに十分なトラフィックがあるにもかかわらず、パーソナライズされたモデルが構築されないのはなぜですか？

状況によっては、パーソナライズされたモデルを構築するのに十分なトラフィックの大きさがありますが、そのトラフィックは、パーソナライズされたモデルとランダムなモデルの間に意味のある違いがないことを [!DNL Target] に知らせる可能性があります。 モデルは [!DNL Target] で作成およびテストされていますが、モデルはランダムな場合と変わらないので、デプロイされません。

モデルがランダムよりも優れていない理由として、オファーが互いに十分に異なっていないことが考えられます。 その場合、メッセージが似ている場合は、オファーの視覚的な違いを増やすか、メッセージ自体を変更してみてください。
