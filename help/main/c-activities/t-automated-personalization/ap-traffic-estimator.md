---
keywords: Traffic Estimator;Automated Personalization;ap；トラフィックの推定
description: '[!UICONTROL Traffic Estimator]を使用して、[!UICONTROL Automated Personalization] アクティビティが成功するのに十分なトラフィックがあるかどうかを評価します。'
title: '[!UICONTROL Automated Personalization] アクティビティを成功させるために必要なトラフィックの量を選択してください。'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Automated Personalization
exl-id: 11f9e239-700b-45cd-bf77-39f7f8967a2e
TQID: 'https://experienceleague.adobe.com/rLjNgDlAWK-r9Zv7083vo-PdWTPy3aHGS4fXEGeTdnY'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: ddd4fa83540294ee229b87f041bc2245ba9a3464
workflow-type: tm+mt
source-wordcount: '802'
ht-degree: 11%
---
# 成功のために必要なトラフィックの見積もり {#traffic-estimator}

>[!BEGINSHADEBOX]

**このページで：** **[!UICONTROL Traffic Estimator]**&#x200B;を使用して、**[!UICONTROL Automated Personalization]** アクティビティが成功するのに十分なトラフィックを持っているかどうかを確認する方法を説明します。

>[!ENDSHADEBOX]

[!DNL Adobe Target] **[!UICONTROL Traffic Estimator]**&#x200B;は、**[!UICONTROL Automated Personalization]** （AP）アクティビティを成功させるのに十分なトラフィックがあるかどうかを確認するためのフィードバックを提供します。 AP アクティビティでは、複数のオファーの組み合わせを使用するため、有意義な結果を提供するためにどの程度のトラフィックが必要かを把握することが重要です。 **[!UICONTROL トラフィック見積もり]**&#x200B;では、ページとテスト中のエクスペリエンスの数に関する統計を使用して、アクティビティを成功させるために必要なトラフィック量とテスト期間を見積もります。

**[!UICONTROL Traffic Estimator]**&#x200B;は、推定されるページのインプレッション数とページの一般的なコンバージョン率を比較することで、パーソナライズされたモデルを生成するのに十分なトラフィックがあるかどうかを判断します。 アクティビティの成功のためには、パーソナライズされたコンテンツがアクティビティ期間の 50％以内または 14 日以内（どちらか短い方）に準備されるようなサンプルサイズにするのが理想的です。 このプロセスにより、パーソナライズされたコンテンツを入手し、どのようなコンテンツを配信すべきかを学ぶのに十分な時間を確保できます。

[!DNL Target]は、パーソナライゼーション アルゴリズムが構築されるまで、ランダムにエクスペリエンスを提供します。 各オファーの横にあるチェックマークアイコンは、そのオファーのモデルの準備が完了し、[!DNL Target]がパーソナライズされたコンテンツの配信を開始できるタイミングを示します。 リフトはモデルの準備が整った後にのみ期待されるので、視覚的な表示により適切な期待を設定できます。 **[!UICONTROL Visual Experience Composer]** （VEC）の&#x200B;**[!UICONTROL Traffic Estimator]**&#x200B;を使用して、モデルの準備が整ったときのガイドラインを取得します。

>[!NOTE]
>
>パーソナライズされたモデルは、トラフィックが十分な場合でも、必ずしもデプロイされるわけではありません。 [!DNL Target]はモデルをビルドしてテストしますが、モデルがデプロイされるのは、ランダムなエクスペリエンスの選択よりもパフォーマンスが高い場合のみです。 モデルがランダムより優れていない場合、オファーはおそらく互いに十分に異なりません。 その場合、メッセージが類似している場合は、オファーをより視覚的に異なるようにするか、メッセージ自体を変更します。

## Traffic Estimatorの使用 {#use-traffic-estimator}

**[!UICONTROL Automated Personalization]** アクティビティを構築する際、**[!UICONTROL Traffic Estimator]**&#x200B;を使用すると、パーソナライズされたモデルを準備するのに十分なトラフィックがあるかどうかを確認できます。 アクティビティを開始する前にこのチェックを実行すると、パーソナライズされたコンテンツを配信するのに十分な訪問者にリーチできないテストを回避できます。また、トラフィックが十分でない場合に、オファーの組み合わせ数やアクティビティの期間を調整する方法を表示します。

1. **[!UICONTROL Automated Personalization]** アクティビティから、**[!UICONTROL Visual Experience Composer]の&#x200B;**[!UICONTROL Experiences]** ページにアクセスします。

1. 「**[!UICONTROL トラフィック]**」アイコン（![ トラフィック見積もりアイコン ](/help/main/assets/icons/Gauge2.svg)）をクリックします。

   **[!UICONTROL Traffic Estimator]**&#x200B;が開きます。 ウィンドウを終了するには、もう一度アイコンをクリックします。

   ![Traffic Estimator ユーザーインターフェイス ](assets/ap-est.png)

1. 一般的なコンバージョン率（またはこのアクティビティから期待されるコンバージョン率）、1日あたりの推定アクティビティインプレッション数、およびテスト期間を指定します。

   **[!UICONTROL Traffic Estimator]**&#x200B;は、これらの指標を使用して、テストを成功させるために必要な調整を決定します。

   | 指標 | 説明 |
   | --- | --- |
   | **[!UICONTROL オファー数]** | この指標は、除外後、アクティビティの一部として作成されたエクスペリエンスの数に基づいて自動的に計算されます。 |
   | **[!UICONTROL 一般的なコンバージョン率]** | この指標は、見積もりや分析システムからの過去のデータにもとづいて、パーセントで表されます。 |
   | **[!UICONTROL 1日あたりの推定訪問者数]** | この指標は、ターゲティング条件に基づいて、アクティビティを表示できる訪問者からの1日あたりの訪問数です。 この指標は分析データにもとづいて算出することができます。 この番号はユニーク訪問者ではなく、訪問者数である必要があります。 |
   | **[!UICONTROL テスト期間]** | アクティビティを実行する日数です。 |



1. 結果の検証： 数値を変更すると、見積もりも変更されます。

   例えば、多くの組み合わせをテストしており、コンバージョン率とインプレッション率が低すぎる場合、**[!UICONTROL Traffic Estimator]**&#x200B;は、テストを成功させるために実行する必要がある期間を示します。 または、トラフィックが少ない場合は、**[!UICONTROL Traffic Estimator]**&#x200B;でオファーの組み合わせ数が少ないことが示されるので、必要な日数でテストを実行できます。

   ![値と結果が表示されたトラフィックの見積もり](assets/ap-est-no.png)

1. 十分なトラフィックがない場合は、次のオプションを検討してください。

   * **[!UICONTROL Automated Personalization]**&#x200B;ではなく[**[!UICONTROL 自動ターゲット ]**](/help/main/c-activities/auto-target/auto-target-to-optimize.md) アクティビティを使用して、1つのエクスペリエンスのバリエーションで複数のオファーの変更を含むエクスペリエンスを作成します。
   * **[!UICONTROL Automated Personalization]** アクティビティ内のオファーの組み合わせ数を減らします。
   * アクティビティの実行期間を長くします。

1. **[!UICONTROL Traffic Estimator]**&#x200B;で十分なトラフィックがあることが示されるまで数値を調整し、それに応じてテストを設計します。

   トラフィックが十分な場合は、**[!UICONTROL トラフィック]** アイコンに緑色のチェックが表示されます。 トラフィックが不十分な場合は、赤の警告ラベルが表示されます。

   十分なトラフィック メッセージを示す![ トラフィック見積もり](assets/ap-est-yes.png)
