---
keywords: a4t;analytics;ターゲットの分析；レポートソースの分析；ターゲットのレポートソースとしてのadobe analytics;atjs;at.js;adobe experience platform web sdk;platform web sdk;platform sdk
description: ' [!DNL Analytics] for [!DNL Target] (A4T) to create activities based on [!DNL Analytics] conversion metrics and audience segments and use [!DNL Analytics] レポートを使用して結果を調べます。'
title: ' [!DNL Analytics] for [!DNL Target] (A4T)とは'
feature: Analytics for Target（A4T）
exl-id: 5bb80b03-8209-4932-a838-0e11c5865133
source-git-commit: b14c9bb4bc0363c77de084c7ae7110e73c5f2f13
workflow-type: tm+mt
source-wordcount: '1127'
ht-degree: 30%

---

# [!DNL Adobe Analytics] を [!DNL Adobe Target] (A4T)のレポートソースとして

[!DNL Adobe Analytics for Target] (A4T)は、コンバージョン指標とオーディエンスセグメントに基づいてアクティビティを作成できる、ソリューション間の統合 [!DNL Analytics] です。A4T統合では、[!DNL Analytics]レポートを使用して結果を調査できます。 [!DNL Analytics]をアクティビティのレポートソースとして使用する場合、そのアクティビティのレポートとセグメントはすべて[!DNL Analytics]データ収集に基づきます。

>[!NOTE]
>
>この記事で説明する[!DNL Adobe Experience Platform Web SDK]実装のA4Tのサポートは、[!DNL Platform Web SDK]バージョン2.5.0リリース（2021年5月24日）で利用可能になる予定です。

## 概要 {#section_92B66069210C40DBA937790E8CC596CF}

[!DNL Analytics]と[!DNL Target]の[!DNL Analytics for Target]統合は、最適化プログラムの強力な分析と時間節約ツールを提供します。

[!DNL Target]で[!DNL Analytics]データを使用する主な利点は次の3つです。

* マーケティング担当者は、[!DNL Analytics]成功指標やレポートセグメントを[!DNL Target]アクティビティレポートにいつでも動的に適用できます。 アクティビティを実行する前にすべての項目を指定する必要がありません。
* 単一のデータソースにより、2 つの異なるシステムのデータを収集した場合に生じる偏差が排除されます。
* 既存の[!DNL Analytics]実装は、必要なすべてのデータを収集します。 レポート用のデータを収集する目的のためだけにページに mbox を実装する必要はありません。

[!DNL Analytics]をアクティビティのレポートソースとして使用する場合、そのアクティビティのレポートとセグメントはすべて[!DNL Analytics]に基づきます。

計算指標を含むすべての[!DNL Analytics]指標は、[!DNL Analytics]の[!DNL Target]および[!UICONTROL ターゲットアクティビティ]レポートで1つの例外を除いて使用できます。 [!UICONTROL 上昇率と信頼性]の計算指標はサポートされていません。 同様に、[!DNL Analytics]で利用できるすべてのセグメントは、両方のソリューションに適用できます。 指標やオーディエンスは、アクティビティの開始後、またはアクティビティの完了後でも、[!DNL Target]のレポートに適用できます。

[!DNL Analytics]に組み込まれているカスタム指標や計算指標を含む、すべての指標が含まれます。

分類期間後、これらのレポートでは、データが Web サイトから収集された約 1 時間後にデータが表示されます。レポート内のすべての指標、セグメントおよび値は、アクティビティを設定したときに選択したレポートスイートから収集されます。

A4T の使用を検討している場合は、次の点に注意してください。

* [!DNL Analytics]を[!DNL Target]のレポートソースとして使用するには、ユーザーと会社の両方が[!DNL Analytics]と[!DNL Target]にアクセスできる必要があります。 [アカウント担当者にお問い合わせください](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB)。
* レポートソースはアクティビティごとに設定されます。[!DNL Target] レポートで使用するデータを引き続き収集します。によって収集されたデータを基にアクティビティを行う場合は、 [!DNL Target] データを引き続き使用でき [!DNL Target]ます。
* 1つのレポートソースか、もう1つのデータソースを使用します。 両方のソースから 1 つのアクティビティのデータを収集することはできません。
* A4Tを使用する場合、アクティビティが使用できる成功指標はすべて[!DNL Analytics]指標です。 ただし、at.jsを使用する場合、目標指標はmbox呼び出しに基づくことができます。 例えば、[!DNL Analytics]クリック追跡コードを実装する代わりに、A4Tでターゲットのそのまま使用できるクリック追跡機能を使用できます。
* [!DNL Target] UIでA4Tアクティビティのレポートを表示すると、[!DNL Analytics]データが表示されます。 例えば、[!DNL Target]で[!UICONTROL 訪問者]指標を使用する場合、[!UICONTROL 参加者]と呼ばれる[!DNL Target][!UICONTROL 訪問者]指標ではなく、[!DNL Analytics] [!UICONTROL 訪問者]指標を使用します。 この違いは、特に基本的なトラフィック指標([!UICONTROL 訪問者]、[!UICONTROL 訪問回数]、[!UICONTROL ページ表示])およびコンバージョン指標で重要です。
* 既存の[!DNL Target]アクティビティは引き続き[!DNL Target]データ収集を使用するので、A4Tを有効にしても影響を受けません。
* A4Tを使用する場合は、1つのmboxベースの指標のみが許可されます。
* [!DNL Target]から[!DNL Analytics]へのサーバー間呼び出しは、アクティビティとエクスペリエンスの情報を[!DNL Analytics]に送信します。 この統合によって、[!DNL Target]または[!DNL Analytics]に対する追加のサーバーコールは発生しません。

   状況によっては、[!DNL Target]から[!DNL Analytics]への分類が失敗し、アクティビティに[!DNL Analytics]内のデータが表示されないことがあります。 [Analyticsとターゲットの統合のトラブルシューティング(A4T)](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md)を参照してください。 また、[ClientCare](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB)にお問い合わせの上、詳しくお問い合わせください。

## A4Tの実装

at.jsと[!DNL Adobe Experience Platform Web SDK]を使用したA4Tの実装について詳しくは、[Analytics for [!DNL Target] 実装](/help/c-integrating-target-with-mac/a4t/a4timplementation.md)を参照してください。

## サポートされるアクティビティタイプ {#section_F487896214BF4803AF78C552EF1669AA}

次の節では、[!DNL Adobe Experience Platform Web SDK]またはat.jsを使用する場合にサポートされるアクティビティタイプについて説明します。

| アクティビティのタイプ | A4T との互換性 | メモ（該当する場合） |
|--- |--- |--- |
| [手動トラフィック分割を使用した A/B アクティビティ](/help/c-activities/t-test-ab/test-ab.md) | ○ |  |
| [自動配分を使用した A/B アクティビティ](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | ○ | 「[自動配分と自動ターゲットアクティビティのA4Tのサポート](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md)」を参照してください。 |
| [自動ターゲットを使用した A/B アクティビティ](/help/c-activities/auto-target/auto-target-to-optimize.md) | ○ | 「[自動配分と自動ターゲットアクティビティのA4Tのサポート](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md)」を参照してください。 |
| [エクスペリエンスターゲット設定（XT）](/help/c-activities/t-experience-target/experience-target.md) | ○ |  |
| [多変量分析テスト（MVT）](/help/c-activities/c-multivariate-testing/multivariate-testing.md) | ○ | [!UICONTROL 要素貢献度]レポートを取得するには、mboxベースの目標指標の目標が必要です。 [!UICONTROL 要素貢献度]レポートは、現在、[!DNL Analytics]指標をサポートしていません。 |
| [自動パーソナライゼーション（AP）アクティビティ](/help/c-activities/t-automated-personalization/automated-personalization.md) | × |  |
| [Recommendations アクティビティ](/help/c-recommendations/recommendations.md) | ○ |  |

まだA4Tをサポートしていないアクティビティタイプがあるので、`orderConfirmPage` mboxなど、重要なコンバージョンmboxを保持または実装することをお勧めします。

## A4Tレポートの例 {#section_F0A43A1CB2F04E8282B909E4D7034361}

[!DNL Target]でA4Tレポートを表示するには、**[!UICONTROL アクティビティ]**&#x200B;をクリックし、[!DNL Analytics]をレポートソースとして使用するリストから目的のアクティビティをクリックして、「**[!UICONTROL レポート]**」タブをクリックします。

>[!NOTE]
>
>[!UICONTROL レポート]ページの上部にある[!UICONTROL アクティビティソース]ドロップダウンリストを使用すると、A4Tを使用しているアクティビティのみを表示できます。

レポートの右上にある適切なアイコンをクリックして、レポートの[!UICONTROL テーブル表示]と[!UICONTROL グラフ表示]を切り替えることができます。

以下の図に、使用可能な [!UICONTROL  目標指標を表示する]レポート指標[!UICONTROL ドロップダウンリストを含む、A4T レポートの]グラフ表示[!DNL Analytics]を示します。

![](assets/a4t_report_graph1.png)

以下の図に、使用可能な [!UICONTROL  オーディエンスを表示する ]Audience[!UICONTROL  ドロップダウンリストを含む、A4T レポートの]グラフ表示[!DNL Analytics]を示します。

![](assets/a4t_report_graph2.png)

以下の図に、A4T レポートの[!UICONTROL テーブル表示]を示します。

![](assets/a4t_report_table.png)

[!DNL Analytics] ではなく [!DNL Target] でレポートを表示するには、レポートの上部にある「**[!UICONTROL Analytics で表示]**」をクリックします。

## 「Analytics＆Target：分析のベストプラクティス」チュートリアル {#section_3438E6E77A464424B717A4FD333B84B2}

[Analytics &amp;ターゲットを開きます。[!DNL Adobe Experience League]が提供する分析](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)のベストプラクティスのチュートリアル。

## トレーニングビデオ：

このトピックで説明されている概念の詳細については、次のビデオを参照してください。

### Analytics forAdobe Target(A4T)(4:32)![概要バッジ](/help/assets/overview.png)

このビデオでは、[!DNL Target]のレポートソースとして[!DNL Analytics]を使用して最適化プログラムの分析を推進する方法を説明します。

* A4T とは何かと、使用する理由の説明
* A4T の仕組みの説明
* A4T を使用する前に必要な前提条件の理解

>[!VIDEO](https://video.tv.adobe.com/v/17384)

### Analytics/Adobe Target統合(A4T)(40:33)![チュートリアルバッジ](/help/assets/tutorial.png)

このビデオは、「[Office Hours](/help/cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)」（アドビカスタマーケアチーム主導による取り組みの 1 つ）の録画です。

* 統合を設定し、統合が機能することを検証する方法
* 統合の仕組み
* Analytics での使用に最適なレポートの詳細
* A4T に関するよくある質問への回答

[Analytics/ターゲット統合(A4T)の営業時間](https://helpx.adobe.com/jp/customer-care-office-hours/target/analytics-target-A4T-integration.html)

>[!MORELIKETHIS]
>
>* [Analytics [!DNL Target] の導入](/help/c-integrating-target-with-mac/a4t/a4timplementation.md):at.jsおよびプラットフォームWeb SDKの実装情報が含まれています。
>* [リダイレクトオファー - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md)
* [Adobe Experience PlatformWeb SDKとは](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html):プラットフォームWeb SDKの概要情報が含まれています。
* [ターゲットの概要](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html):およびに固有の情報 [!DNL Target] が含まれ [!DNL Platform Web SDK]ます。

