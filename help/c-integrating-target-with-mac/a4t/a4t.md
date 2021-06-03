---
keywords: a4t;analytics;analytics for target;analyticsレポートソース；adobe analytics as reporting source for target;atjs;at.js;adobe experience platform web sdk;platform web sdk;platform sdk
description: ' [!DNL Analytics] for [!DNL Target] (A4T) to create activities based on [!DNL Analytics] conversion metrics and audience segments and use [!DNL Analytics] レポートを使用して結果を調べます。'
title: ' [!DNL Analytics] for [!DNL Target] (A4T)とは'
feature: Analytics for Target（A4T）
exl-id: 5bb80b03-8209-4932-a838-0e11c5865133
source-git-commit: 14dfc3e19333848e50324a61539ddf693e17d3ce
workflow-type: tm+mt
source-wordcount: '1114'
ht-degree: 31%

---

# [!DNL Adobe Analytics] を( [!DNL Adobe Target] A4T)のレポートソースとして使用する場合

[!DNL Adobe Analytics for Target] (A4T)は、コンバージョン指標とオーディエンスセグメントに基づいてアクティビティを作成できる、クロスソリ [!DNL Analytics] ューションの統合です。A4T統合により、[!DNL Analytics]レポートを使用して結果を調べることができます。 [!DNL Analytics]をアクティビティのレポートソースとして使用する場合、そのアクティビティのレポートとセグメント化はすべて[!DNL Analytics]のデータ収集に基づきます。

## 概要 {#section_92B66069210C40DBA937790E8CC596CF}

[!DNL Analytics]と[!DNL Target]の[!DNL Analytics for Target]統合は、最適化プログラム用の強力な分析と時間節約ツールを提供します。

[!DNL Target]で[!DNL Analytics]データを使用する主な利点は次の3つです。

* マーケティング担当者は、 [!DNL Analytics]成功指標やレポートセグメントを[!DNL Target]アクティビティレポートにいつでも動的に適用できます。 アクティビティを実行する前にすべての項目を指定する必要がありません。
* 単一のデータソースにより、2 つの異なるシステムのデータを収集した場合に生じる偏差が排除されます。
* 既存の[!DNL Analytics]実装は、必要なすべてのデータを収集します。 レポート用のデータを収集する目的のためだけにページに mbox を実装する必要はありません。

[!DNL Analytics]をアクティビティのレポートソースとして使用する場合、そのアクティビティのレポートとセグメント化はすべて[!DNL Analytics]に基づきます。

計算指標を含むすべての[!DNL Analytics]指標は、[!DNL Target]および[!DNL Analytics]の[!UICONTROL Targetアクティビティ]レポートで1つの例外を除き使用できます。 [!UICONTROL 上昇率と信頼性]の計算指標はサポートされていません。 同様に、[!DNL Analytics]で使用可能なすべてのセグメントを両方のソリューションに適用できます。 アクティビティの開始後、またはアクティビティの完了後でも、[!DNL Target]のレポートに指標やオーディエンスを適用できます。

[!DNL Analytics]に組み込まれているカスタム指標や計算指標を含め、すべての指標が含まれます。

分類期間後、これらのレポートでは、データが Web サイトから収集された約 1 時間後にデータが表示されます。レポート内のすべての指標、セグメントおよび値は、アクティビティを設定したときに選択したレポートスイートから収集されます。

A4T の使用を検討している場合は、次の点に注意してください。

* [!DNL Analytics]を[!DNL Target]のレポートソースとして使用するには、ユーザーと会社の両方が[!DNL Analytics]と[!DNL Target]にアクセスできる必要があります。 [アカウント担当者にお問い合わせください](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB)。
* レポートソースはアクティビティごとに設定されます。[!DNL Target] は引き続きレポートで使用するデータを収集しま [!DNL Target] す。で収集されたデータに基づいてアクティビティを作成したい場合は、データを引き続き使用で [!DNL Target]きます。
* 1つのレポートソースまたは他のレポートソースを使用します。 両方のソースから 1 つのアクティビティのデータを収集することはできません。
* A4Tを使用する場合、アクティビティで使用できる成功指標はすべて[!DNL Analytics]指標です。 ただし、at.jsを使用している場合、目標指標はmbox呼び出しに基づくことができます。 例えば、Targetの標準搭載のクリック追跡機能をA4Tで使用すると、[!DNL Analytics]クリック追跡コードを実装する必要がなくなります。
* [!DNL Target] UIでA4Tアクティビティのレポートを表示すると、[!DNL Analytics]データが表示されます。 例えば、[!UICONTROL Visitor]指標を[!DNL Target]で使用する場合、[!DNL Target] [!UICONTROL Visitors]指標（現在は[!UICONTROL Entrits]と呼ばれています）ではなく、[!DNL Analytics] [!UICONTROL Visitor]指標を使用します。 この違いは、基本的なトラフィック指標（[!UICONTROL 訪問者]、[!UICONTROL 訪問回数]、[!UICONTROL ページビュー数]）とコンバージョン指標で特に重要です。
* 既存の[!DNL Target]アクティビティは引き続き[!DNL Target]データ収集を使用し、A4Tを有効にしても影響を受けません。
* A4Tを使用する場合は、mboxベースの指標を1つだけ使用できます。
* [!DNL Target]から[!DNL Analytics]へのサーバー間呼び出しは、アクティビティとエクスペリエンスの情報を[!DNL Analytics]に送信します。 この統合によって、[!DNL Target]または[!DNL Analytics]に対する追加のサーバー呼び出しが発生することはありません。

   状況によっては、[!DNL Target]から[!DNL Analytics]への分類が失敗し、アクティビティに[!DNL Analytics]のデータが表示されないことがあります。 [AnalyticsとTargetの統合(A4T)](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md)のトラブルシューティングを参照してください。 [詳しくは、ClientCare](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB)にお問い合わせください。

## A4Tの実装

at.jsおよび[!DNL Adobe Experience Platform Web SDK]を使用したA4Tの実装について詳しくは、[Analytics for [!DNL Target] の実装](/help/c-integrating-target-with-mac/a4t/a4timplementation.md)を参照してください。

## サポートされるアクティビティのタイプ {#section_F487896214BF4803AF78C552EF1669AA}

以下の節では、[!DNL Adobe Experience Platform Web SDK]またはat.jsを使用する際にサポートされるアクティビティのタイプについて説明します。

| アクティビティのタイプ | A4T との互換性 | メモ（該当する場合） |
|--- |--- |--- |
| [手動トラフィック分割を使用した A/B アクティビティ](/help/c-activities/t-test-ab/test-ab.md) | ○ |  |
| [自動配分を使用した A/B アクティビティ](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | ○ | 自動配分および自動ターゲットアクティビティの[A4Tのサポート](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md)を参照してください。 |
| [自動ターゲットを使用した A/B アクティビティ](/help/c-activities/auto-target/auto-target-to-optimize.md) | ○ | [自動配分および自動ターゲットアクティビティのA4Tサポート](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md)を参照してください。 |
| [エクスペリエンスターゲット設定（XT）](/help/c-activities/t-experience-target/experience-target.md) | ○ |  |
| [多変量分析テスト（MVT）](/help/c-activities/c-multivariate-testing/multivariate-testing.md) | ○ | [!UICONTROL 要素の貢献度]レポートを取得するには、mboxベースの目標指標の目標が必要です。 [!UICONTROL 要素の貢献度]レポートは、現在、[!DNL Analytics]指標をサポートしていません。 |
| [自動パーソナライゼーション（AP）アクティビティ](/help/c-activities/t-automated-personalization/automated-personalization.md) | × |  |
| [Recommendations アクティビティ](/help/c-recommendations/recommendations.md) | ○ |  |
| [リダイレクトオファーを使用するすべてのアクティビティ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md) | ○ |

すべてのアクティビティタイプはまだA4Tをサポートしていないので、 `orderConfirmPage` mboxなど、重要なコンバージョンmboxを保持するか、実装することをお勧めします。

## A4Tレポートの例 {#section_F0A43A1CB2F04E8282B909E4D7034361}

[!DNL Target]でA4Tレポートを表示するには、「**[!UICONTROL アクティビティ]**」をクリックし、[!DNL Analytics]をレポートソースとして使用するリストから目的のアクティビティをクリックして、「**[!UICONTROL レポート]**」タブをクリックします。

>[!NOTE]
>
>[!UICONTROL アクティビティ]ページの上部にある[!UICONTROL レポートソース]ドロップダウンリストを使用して、A4Tを使用するアクティビティのみを表示できます。

レポートの右上にある適切なアイコンをクリックして、レポートの[!UICONTROL テーブル表示]と[!UICONTROL グラフ表示]を切り替えることができます。

以下の図に、使用可能な [!UICONTROL  目標指標を表示する]レポート指標[!UICONTROL ドロップダウンリストを含む、A4T レポートの]グラフ表示[!DNL Analytics]を示します。

![](assets/a4t_report_graph1.png)

以下の図に、使用可能な [!UICONTROL  オーディエンスを表示する ]Audience[!UICONTROL  ドロップダウンリストを含む、A4T レポートの]グラフ表示[!DNL Analytics]を示します。

![](assets/a4t_report_graph2.png)

以下の図に、A4T レポートの[!UICONTROL テーブル表示]を示します。

![](assets/a4t_report_table.png)

[!DNL Analytics] ではなく [!DNL Target] でレポートを表示するには、レポートの上部にある「**[!UICONTROL Analytics で表示]**」をクリックします。

## 「Analytics＆Target：分析のベストプラクティス」チュートリアル {#section_3438E6E77A464424B717A4FD333B84B2}

[Analytics &amp; Targetを開きます。[!DNL Adobe Experience League]が提供する、分析のベストプラクティス](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)チュートリアル。

## トレーニングビデオ：

以下のビデオでは、このトピックで説明する概念の詳細を説明します。

### Analytics for Adobe Target(A4T)(4:32) ![概要バッジ](/help/assets/overview.png)

このビデオでは、[!DNL Analytics]を[!DNL Target]のレポートソースとして使用し、最適化プログラムの分析を推進する方法を説明します。

* A4T とは何かと、使用する理由の説明
* A4T の仕組みの説明
* A4T を使用する前に必要な前提条件の理解

>[!VIDEO](https://video.tv.adobe.com/v/17384)

### Analytics/Adobe Target統合(A4T)(40:33) ![チュートリアルバッジ](/help/assets/tutorial.png)

このビデオは、「[Office Hours](/help/cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)」（アドビカスタマーケアチーム主導による取り組みの 1 つ）の録画です。

* 統合を設定し、統合が機能することを検証する方法
* 統合の仕組み
* Analytics での使用に最適なレポートの詳細
* A4T に関するよくある質問への回答

[Analytics/Target統合(A4T)のOffice Hours](https://helpx.adobe.com/jp/customer-care-office-hours/target/analytics-target-A4T-integration.html)

>[!MORELIKETHIS]
>
>* [実装 [!DNL Target] 用のAnalytics](/help/c-integrating-target-with-mac/a4t/a4timplementation.md):at.jsおよびPlatform Web SDKの実装情報が含まれます。
>* [リダイレクトオファー - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md)
* [Adobe Experience Platform Web SDKとは](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html):Platform Web SDKに関する概要情報が含まれます。
* [Targetの概要](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html):とに固有の情報が含 [!DNL Target] まれま [!DNL Platform Web SDK]す。

