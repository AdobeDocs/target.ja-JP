---
keywords: a4t;analytics;analytics for target;analytics reporting source;adobe analytics as the reporting source for target
description: アドビの「Analytics for Target」（A4T）は、Analytics のコンバージョン指標とオーディエンスセグメントに基づいてアクティビティを作成できるクロスソリューション統合です。この統合により、Analytics レポートを使用して結果を確認できます。Analytics をアクティビティのレポートソースとして使用しているときは、そのアクティビティのレポート作成とセグメント化はすべて Analytics のデータ収集に基づいておこなわれます。
title: Adobe Target のレポートソースとしての Adobe Analytics（A4T）
feature: a4t general
subtopic: Integrating
topic: Standard
uuid: 616798a6-1587-410f-9ac6-473beb39e3fc
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '1257'
ht-degree: 46%

---


# Adobe Target のレポートソースとしての Adobe Analytics（A4T）{#adobe-analytics-as-the-reporting-source-for-adobe-target-a-t}

[!DNL Adobe Analytics for Target] (A4T)は、コンバージョン指標とオーディエンスセグメントに基づいてアクティビティを作成できる、ソリューション間の統合です。 [!DNL Analytics] The A4T integration lets you use [!DNL Analytics] reports to examine your results. If you use [!DNL Analytics] as the reporting source for an activity, all reporting and segmentation for that activity is based on [!DNL Analytics] data collection.

## A4T の概要 {#section_92B66069210C40DBA937790E8CC596CF}

The [!DNL Analytics for Target] integration between [!DNL Analytics] and [!DNL Target] provides powerful analysis and timesaving tools for your optimization program.

The three primary benefits of using [!DNL Analytics] data in [!DNL Target] are:

* Marketers can dynamically apply [!DNL Analytics] success metrics or reporting segments to [!DNL Target] activity reports at any time. アクティビティを実行する前にすべての項目を指定する必要がありません。
* 単一のデータソースにより、2 つの異なるシステムのデータを収集した場合に生じる偏差が排除されます。
* Your existing [!DNL Analytics] implementation collects all required data. レポート用のデータを収集する目的のためだけにページに mbox を実装する必要はありません。Although, it is still recommended that you implement an order confirmation mbox for [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) activities.

>[!IMPORTANT]
>
>A4T を使用する際は、事前にアカウントで統合のプロビジョニングを依頼しておく必要があります。プロビジョニングの依頼には[このフォーム](https://www.adobe.com/go/audiences)を使用します。
>
>The integration that enables [!DNL Analytics] as the data source for [!DNL Target] (A4T) represents the next generation of the Test&amp;Target to SiteCatalyst plug-in. このプラグインは廃止されていますが、既存の利用者のために今でもサポートされています。

If you use [!DNL Analytics] as the reporting source for an activity, all reporting and segmentation for that activity is based on [!DNL Analytics].

All [!DNL Analytics] metrics, including calculated metrics, are available in [!DNL Target] and the [!UICONTROL Target Activities] report in [!DNL Analytics]. Likewise, any segment available in [!DNL Analytics] can be applied to both solutions. You can apply the metric or audience to the report in [!DNL Target] after the activity has started, or even after the activity has completed.

Every metric is included, including any customer or calculated metrics that are built-in in [!DNL Analytics].

分類期間後、これらのレポートでは、データが Web サイトから収集された約 1 時間後にデータが表示されます。レポート内のすべての指標、セグメントおよび値は、アクティビティを設定したときに選択したレポートスイートから収集されます。

A4T の使用を検討している場合は、次の点に注意してください。

* To use [!DNL Analytics] as the reporting source for [!DNL Target], both you and your company must have access to [!DNL Analytics] and to [!DNL Target]. [アカウント担当者にお問い合わせください](../../cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB)。
* レポートソースはアクティビティごとに設定されます。[!DNL Target] レポートで使用するデータを引き続き収集します。で収集したデータを基にアクティビティを行う場合は、 [!DNL Target] 引き続きデータを利用でき [!DNL Target]ます。
* どちらか 1 つのレポートソースを選ぶ必要があります。両方のソースから 1 つのアクティビティのデータを収集することはできません。
* When using A4T, all success metrics available to your activities are [!DNL Analytics] metrics. ただし、目標指標は mbox の呼び出しをベースにすることができます。For example, you can use Target&#39;s out-of-the-box click-tracking capabilities with A4T instead of having to implement [!DNL Analytics] click-tracking code.
* When viewing reporting of an A4T activity in the [!DNL Target] UI, you are viewing [!DNL Analytics] data. For example, if you use the [!UICONTROL Visitor] metric in [!DNL Target], you are using the [!DNL Analytics] [!UICONTROL Visitor] metric, not the [!DNL Target] [!UICONTROL Visitors] metric, which is now called [!UICONTROL Entrants]. This difference is especially important for basic traffic metrics ([!UICONTROL Visitors], [!UICONTROL Visits], [!UICONTROL Page Views]) and conversion metrics.
* Any existing [!DNL Target] activities continue to use [!DNL Target] data collection and are not affected by enabling A4T.
* Only one mbox-based metric is allowed when using [!DNL Analytics] as the reporting source.
* A server-to-server call from [!DNL Target] to [!DNL Analytics] sends activity and experience information to [!DNL Analytics]. This integration does not result in additional server calls for either [!DNL Target] or [!DNL Analytics].

   状況によっては、からへの分類呼び出しが失敗し、アクティビティ [!DNL Target] にデータが表示されない場合があり [!DNL Analytics][!DNL Analytics]ます。 この問題が発生した場合は、Analyticsとターゲットの統合の [トラブルシューティング(A4T)を参照してください](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md)。 ClientCareに [お問い合わせの上、詳しくは](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) 、

## Supported activity types {#section_F487896214BF4803AF78C552EF1669AA}

The following table shows you which activity types support [!DNL Analytics] as the reporting source in [!DNL Target] (A4T):

| アクティビティのタイプ | A4T との互換性 | メモ（該当する場合） |
|--- |--- |--- |
| 手動トラフィック分割を使用した A/B アクティビティ | ○ |  |
| 自動配分を使用した A/B アクティビティ | ○ | 自動配分アクティビティの [ターゲット用の分析(A4T)のサポートを参照してください](/help/c-integrating-target-with-mac/a4t/campaign-creation.md#a4t-aa)。 |
| 自動ターゲットを使用した A/B アクティビティ | × |  |
| エクスペリエンスターゲット設定（XT） | ○ |  |
| 多変量分析テスト（MVT） | ○ | Requires mbox-based goal metric goal to get the [!UICONTROL Element Contribution] report.  The [!UICONTROL Element Contribution] report does not currently support [!DNL Analytics] metrics. |
| 自動パーソナライゼーション（AP）アクティビティ | × |  |
| Recommendations アクティビティ | ○ |  |
| モバイルアプリ | ○ | Mobile Services SDK バージョン 4.13.1 以降でサポートされています。詳しくは、[Mobile Services のドキュメント](https://docs.adobe.com/content/help/en/mobile-services/using/home.html)を参照してください。 |
| 電子メール | × |  |
| Server Side Delivery API | ○ | 詳細については、「[サーバー側：Target の実装](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md)」を参照してください。 |
| NodeJS SDK | ○ | 詳細については、「[サーバー側：Target の実装](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md)」を参照してください。 |
| AEM 6.1（またはそれ以前）のクラウドサービス統合 | × |  |
| AEM 6.2（またはそれ以降）のクラウドサービス統合 | ○ | For more information, see [Integrating with Adobe Target](https://helpx.adobe.com/experience-manager/6-2/sites/administering/using/target.html) in the [!DNL Adobe Experience Manager] 6.2 documentation. |
| リダイレクトオファーを使用するアクティビティ | ○ | A4T でリダイレクトオファーを使用する場合は、より厳格な最小要件が適用されます。詳しくは、[リダイレクトオファー - A4T に関する FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md) を参照してください。 |
| Node.JS | ○ |  |

Because all activity types do not yet support A4T, it is recommended that you keep or implement important conversion mboxes, such as the `orderConfirmPage` mbox.

## Examples of A4T reports {#section_F0A43A1CB2F04E8282B909E4D7034361}

To view A4T reports in [!DNL Target], click **[!UICONTROL Activities]**, click the desired activity from the list that uses [!DNL Analytics] as its reporting source, then click the **[!UICONTROL Reports]** tab.

>[!NOTE]
>
>[!UICONTROL アクティビティ]ページの最上部にある「[!UICONTROL レポートソース]」ドロップダウンリストを使用して、[!DNL Analytics] をレポートソースとして使用するアクティビティのみを表示できます。

You can toggle between the [!UICONTROL Table View] and [!UICONTROL Graph View] of the report by clicking the appropriate icon at the top right side of the report.

以下の図に、使用可能な [!UICONTROL  目標指標を表示する]レポート指標[!UICONTROL ドロップダウンリストを含む、A4T レポートの]グラフ表示[!DNL Analytics]を示します。

![](assets/a4t_report_graph1.png)

以下の図に、使用可能な [!UICONTROL  オーディエンスを表示する ]Audience[!UICONTROL  ドロップダウンリストを含む、A4T レポートの]グラフ表示[!DNL Analytics]を示します。

![](assets/a4t_report_graph2.png)

以下の図に、A4T レポートの[!UICONTROL テーブル表示]を示します。

![](assets/a4t_report_table.png)

[!DNL Analytics] ではなく [!DNL Target] でレポートを表示するには、レポートの上部にある「**[!UICONTROL Analytics で表示]**」をクリックします。

## 「Analytics＆Target：分析のベストプラクティス」チュートリアル{#section_3438E6E77A464424B717A4FD333B84B2}

Open the [Analytics &amp; Target: Best Practices for Analysis](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) tutorial, provided by [!DNL Adobe Experience League].

## トレーニングビデオ：

このトピックで説明されている概念の詳細については、次のビデオを参照してください。

### ターゲット用のAnalytics(A4T)(4:32) ![概要バッジ](/help/assets/overview.png)

This video explains how to use [!DNL Analytics] as a reporting source in [!DNL Target] to drive the analysis of your optimization program.

* A4T とは何かと、使用する理由の説明
* A4T の仕組みの説明
* A4T を使用する前に必要な前提条件の理解

>[!VIDEO](https://video.tv.adobe.com/v/17384)

### Analytics/ターゲットの統合(A4T)(40:33) ![チュートリアルバッジ](/help/assets/tutorial.png)

このビデオは、「[Office Hours](../../cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)」（アドビカスタマーケアチーム主導による取り組みの 1 つ）の録画です。

* 統合を設定し、統合が機能することを検証する方法
* 統合の仕組み
* Analytics での使用に最適なレポートの詳細
* A4T に関するよくある質問への回答

[Analytics/ターゲット統合(A4T)の営業時間](https://helpx.adobe.com/customer-care-office-hours/target/analytics-target-A4T-integration.html)