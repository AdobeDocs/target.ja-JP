---
keywords: A4T;Analytics;Analytics for Target;Analytics レポートソース；Adobe Analytics For Target;atjs;at.js;Adobe Experience Platform Web SDK;Platform Web SDK;Platform SDK
description: 用途 [!DNL Analytics] 対象 [!DNL Target] (A4T) [!DNL Analytics] コンバージョン指標およびオーディエンスセグメントと、 [!DNL Analytics] 結果を調べるレポート。
title: 説明 [!DNL Analytics] 対象 [!DNL Target] (A4T)?
feature: Analytics for Target (A4T)
exl-id: 5bb80b03-8209-4932-a838-0e11c5865133
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1125'
ht-degree: 30%

---

# [!DNL Adobe Analytics] レポートソースとして [!DNL Adobe Target] (A4T)

[!DNL Adobe Analytics for Target] (A4T) は、 [!DNL Analytics] コンバージョン指標およびオーディエンスセグメント。 A4T 統合により、 [!DNL Analytics] レポートを使用して結果を確認します。 次を使用する場合、 [!DNL Analytics] をアクティビティのレポートソースとして使用する場合、そのアクティビティのレポートとセグメント化はすべて、 [!DNL Analytics] データ収集。

## 概要 {#section_92B66069210C40DBA937790E8CC596CF}

この [!DNL Analytics for Target] ～間の統合 [!DNL Analytics] および [!DNL Target] は、最適化プログラム用の強力な分析および時間節約ツールを提供します。

を使用する主な 3 つのメリット [!DNL Analytics] データ [!DNL Target] 次の場合：

* マーケターは動的に適用できます [!DNL Analytics] 成功指標またはレポートセグメント [!DNL Target] アクティビティレポートをいつでも作成できます。 アクティビティを実行する前にすべての項目を指定する必要がありません。
* 単一のデータソースにより、2 つの異なるシステムのデータを収集した場合に生じる偏差が排除されます。
* 既存の [!DNL Analytics] 実装は、必要なすべてのデータを収集します。 レポート用のデータを収集する目的のためだけにページに mbox を実装する必要はありません。

次を使用する場合、 [!DNL Analytics] をアクティビティのレポートソースとして使用する場合、そのアクティビティのレポートとセグメント化はすべて、 [!DNL Analytics].

すべて [!DNL Analytics] 指標（計算指標を含む）は、 [!DNL Target] そして [!UICONTROL Target アクティビティ] レポート [!DNL Analytics]（ただし 1 つだけ例外があります）。 の計算指標 [!UICONTROL 上昇率と信頼性] はサポートされていません。 同様に、で使用可能な任意のセグメント [!DNL Analytics] は両方のソリューションに適用できます。 指標またはオーディエンスを [!DNL Target] アクティビティが開始した後、またはアクティビティが完了した後でも、

組み込みのカスタム指標や計算指標を含め、すべての指標が含まれます [!DNL Analytics].

分類完了後、データが web サイトから収集された約 1 時間後に、これらのレポートでデータが表示されます。レポート内のすべての指標、セグメントおよび値は、アクティビティを設定したときに選択したレポートスイートから収集されます。

A4T の使用を検討している場合は、次の点に注意してください。

* 使用する [!DNL Analytics] レポートソースとして [!DNL Target]にアクセスするには、自分と会社の両方が [!DNL Analytics] および [!DNL Target]. [アカウント担当者にお問い合わせください](/help/main/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB)。
* レポートソースはアクティビティごとに設定されます。[!DNL Target] は引き続きレポートで使用するデータを収集し、 [!DNL Target] データは、 [!DNL Target].
* 1 つのレポートソースか、他のレポートソースを使用します。 両方のソースから 1 つのアクティビティのデータを収集することはできません。
* A4T を使用する場合、アクティビティで使用できるすべての成功指標は次のようになります。 [!DNL Analytics] 指標。 ただし、at.js を使用している場合、目標指標は mbox 呼び出しに基づくことができます。 例えば、Target の標準のクリック追跡機能を、A4T を使用して、 [!DNL Analytics] クリック追跡コード。
* で A4T アクティビティのレポートを表示する場合 [!DNL Target] UI、表示中 [!DNL Analytics] データ。 例えば、 [!UICONTROL 訪問者] 指標 [!DNL Target]を使用している場合、 [!DNL Analytics] [!UICONTROL 訪問者] 指標ではなく [!DNL Target] [!UICONTROL 訪問者] 指標 ( 現在は [!UICONTROL 参加者]. この違いは、特に基本的なトラフィック指標 ([!UICONTROL 訪問者], [!UICONTROL 訪問回数], [!UICONTROL ページビュー数]) およびコンバージョン指標を使用します。
* 既存の [!DNL Target] アクティビティは引き続き使用 [!DNL Target] データ収集機能に影響を与えず、A4T を有効にしても影響を受けません。
* A4T を使用する場合、使用できる mbox ベースの指標は 1 つだけです。
* からのサーバー間呼び出し [!DNL Target] から [!DNL Analytics] アクティビティとエクスペリエンスの情報をに送信 [!DNL Analytics]. この統合によって、 [!DNL Target] または [!DNL Analytics].

   状況によっては、 [!DNL Target] から [!DNL Analytics] 失敗し、アクティビティにデータが表示されない [!DNL Analytics]. 詳しくは、 [Analytics と Target の統合 (A4T) のトラブルシューティング](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md). また、 [ClientCare にお問い合わせください](/help/main/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) さらなる支援が必要です。

## A4T の実装

at.js および [!DNL Adobe Experience Platform Web SDK]を参照してください。 [の分析 [!DNL Target] 実装](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md).

## サポートされるアクティビティのタイプ {#section_F487896214BF4803AF78C552EF1669AA}

以下の節では、 [!DNL Adobe Experience Platform Web SDK] または at.js:

| アクティビティのタイプ | A4T との互換性 | メモ（該当する場合） |
|--- |--- |--- |
| [手動トラフィック分割を使用した A/B アクティビティ](/help/main/c-activities/t-test-ab/test-ab.md) | ○ |  |
| [自動配分を使用した A/B アクティビティ](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | ○ | 詳しくは、 [自動配分と自動ターゲットアクティビティに対する A4T のサポート](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md) |
| [自動ターゲットを使用した A/B アクティビティ](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | ○ | 詳しくは、 [自動配分と自動ターゲットアクティビティに対する A4T のサポート](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md). |
| [エクスペリエンスのターゲット設定（XT）](/help/main/c-activities/t-experience-target/experience-target.md) | ○ |  |
| [多変量分析テスト（MVT）](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | ○ | を取得するには、mbox ベースの目標指標の目標が必要です [!UICONTROL 要素貢献度] レポート。 この [!UICONTROL 要素貢献度] レポートは現在サポートされていません [!DNL Analytics] 指標。 |
| [自動パーソナライゼーション（AP）アクティビティ](/help/main/c-activities/t-automated-personalization/automated-personalization.md) | × |  |
| [Recommendations アクティビティ](/help/main/c-recommendations/recommendations.md) | ○ |  |
| [リダイレクトオファーを使用するすべてのアクティビティ](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md) | ○ |

すべてのアクティビティタイプはまだ A4T をサポートしていないので、 `orderConfirmPage` mbox.

## A4T レポートの例 {#section_F0A43A1CB2F04E8282B909E4D7034361}

で A4T レポートを表示するには、以下を実行します。 [!DNL Target]をクリックし、 **[!UICONTROL アクティビティ]**&#x200B;をクリックし、を使用するリストから目的のアクティビティをクリックします。 [!DNL Analytics] をレポートソースとして使用し、 **[!UICONTROL レポート]** タブをクリックします。

>[!NOTE]
>
>以下を使用して、 [!UICONTROL レポートソース] ドロップダウンリスト [!UICONTROL アクティビティ] A4T を使用するアクティビティのみを表示するページ

次の項目を切り替えることができます。 [!UICONTROL テーブル表示] および [!UICONTROL グラフ表示] 」をクリックします。

以下の図に、使用可能な [!UICONTROL  目標指標を表示する]レポート指標[!UICONTROL ドロップダウンリストを含む、A4T レポートの]グラフ表示[!DNL Analytics]を示します。

![](assets/a4t_report_graph1.png)

以下の図に、使用可能な [!UICONTROL  オーディエンスを表示する ]Audience[!UICONTROL  ドロップダウンリストを含む、A4T レポートの]グラフ表示[!DNL Analytics]を示します。

![](assets/a4t_report_graph2.png)

以下の図に、A4T レポートの[!UICONTROL テーブル表示]を示します。

![](assets/a4t_report_table.png)

[!DNL Analytics] ではなく [!DNL Target] でレポートを表示するには、レポートの上部にある「**[!UICONTROL Analytics で表示]**」をクリックします。

## 「Analytics＆Target：分析のベストプラクティス」チュートリアル {#section_3438E6E77A464424B717A4FD333B84B2}

を開きます。 [Analytics &amp; Target:分析のベストプラクティス](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) チュートリアル：提供元 [!DNL Adobe Experience League].

## トレーニングビデオ：

次のビデオでは、このトピックで説明する概念の詳細を説明します。

### Analytics for Adobe Target(A4T)(4:32) ![概要バッジ](/help/main/assets/overview.png)

このビデオでは、の使用方法を説明します。 [!DNL Analytics] レポートソースとして [!DNL Target] 最適化プログラムの分析を促進します。

* A4T とは何かと、使用する理由の説明
* A4T の仕組みの説明
* A4T を使用する前に必要な前提条件の理解

>[!VIDEO](https://video.tv.adobe.com/v/17384)

### Analytics とAdobe Targetの統合 (A4T)(40:33) ![チュートリアルバッジ](/help/main/assets/tutorial.png)

このビデオは、「[Office Hours](/help/main/cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)」（アドビカスタマーケアチーム主導による取り組みの 1 つ）の録画です。

* 統合を設定し、統合が機能することを検証する方法
* 統合の仕組み
* Analytics での使用に最適なレポートの詳細
* A4T に関するよくある質問への回答

[Analytics/Target 統合 (A4T) 営業時間](https://helpx.adobe.com/jp/customer-care-office-hours/target/analytics-target-A4T-integration.html)

>[!MORELIKETHIS]
>
>* [の分析 [!DNL Target] 実装](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md):at.js および Platform Web SDK の実装情報が含まれます。
>* [リダイレクトオファー - A4T FAQ](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md)
>* [Adobe Experience Platform Web SDK とは](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html):Platform Web SDK に関する概要情報が含まれています。
>* [Target の概要](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html):次に特有の情報を含む [!DNL Target] そして [!DNL Platform Web SDK].

