---
keywords: A4T;分析;ターゲットの分析;analytics レポートソース;ターゲットのレポートソースとしての adobe analytics
description: Analytics forターゲット(A4T)を使用して、Analyticsのコンバージョン指標とオーディエンスセグメントに基づいてアクティビティを作成し、Analyticsレポートを使用して結果を調べます。
title: ターゲット用Analytics(A4T)とは何ですか。
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '1279'
ht-degree: 41%

---


# Adobe Target のレポートソースとしての Adobe Analytics（A4T）

[!DNL Adobe Analytics for Target] (A4T)は、コンバージョン指標とオーディエンスセグメントに基づいてアクティビティを作成できる、ソリューション間の統合 [!DNL Analytics] です。A4T統合では、[!DNL Analytics]レポートを使用して結果を調査できます。 [!DNL Analytics]をアクティビティのレポートソースとして使用する場合、そのアクティビティのレポートとセグメントはすべて[!DNL Analytics]データ収集に基づきます。

## A4T の概要 {#section_92B66069210C40DBA937790E8CC596CF}

[!DNL Analytics]と[!DNL Target]の[!DNL Analytics for Target]統合は、最適化プログラムの強力な分析と時間節約ツールを提供します。

[!DNL Target]で[!DNL Analytics]データを使用する主な利点は次の3つです。

* マーケティング担当者は、[!DNL Analytics]成功指標やレポートセグメントを[!DNL Target]アクティビティレポートにいつでも動的に適用できます。 アクティビティを実行する前にすべての項目を指定する必要がありません。
* 単一のデータソースにより、2 つの異なるシステムのデータを収集した場合に生じる偏差が排除されます。
* 既存の[!DNL Analytics]実装は、必要なすべてのデータを収集します。 レポート用のデータを収集する目的のためだけにページに mbox を実装する必要はありません。ただし、[Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md)(AP)アクティビティに注文確認mboxを実装することをお勧めします。

>[!IMPORTANT]
>
>A4T を使用する際は、事前にアカウントで統合のプロビジョニングを依頼しておく必要があります。プロビジョニングの依頼には[このフォーム](https://www.adobe.com/go/audiences)を使用します。
>
>[!DNL Analytics]を[!DNL Target]のデータソースとして有効にする統合(A4T)は、Test&amp;ターゲットのSiteCatalystプラグインの次世代を表します。 このプラグインは廃止されていますが、既存の利用者のために今でもサポートされています。

[!DNL Analytics]をアクティビティのレポートソースとして使用する場合、そのアクティビティのレポートとセグメントはすべて[!DNL Analytics]に基づきます。

計算指標を含むすべての[!DNL Analytics]指標は、[!DNL Target]および[!DNL Analytics]の[!UICONTROL ターゲットアクティビティ]レポートで使用できます。 同様に、[!DNL Analytics]で利用できるすべてのセグメントは、両方のソリューションに適用できます。 指標やオーディエンスは、アクティビティの開始後、またはアクティビティの完了後でも、[!DNL Target]のレポートに適用できます。

[!DNL Analytics]に組み込まれている顧客指標や計算指標を含め、すべての指標が含まれます。

分類期間後、これらのレポートでは、データが Web サイトから収集された約 1 時間後にデータが表示されます。レポート内のすべての指標、セグメントおよび値は、アクティビティを設定したときに選択したレポートスイートから収集されます。

A4T の使用を検討している場合は、次の点に注意してください。

* [!DNL Analytics]を[!DNL Target]のレポートソースとして使用するには、ユーザーと会社の両方が[!DNL Analytics]と[!DNL Target]にアクセスできる必要があります。 [アカウント担当者にお問い合わせください](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB)。
* レポートソースはアクティビティごとに設定されます。[!DNL Target] レポートで使用するデータを引き続き収集します。によって収集されたデータを基にアクティビティを行う場合は、 [!DNL Target] データを引き続き使用でき [!DNL Target]ます。
* どちらか 1 つのレポートソースを選ぶ必要があります。両方のソースから 1 つのアクティビティのデータを収集することはできません。
* A4Tを使用する場合、アクティビティが使用できる成功指標はすべて[!DNL Analytics]指標です。 ただし、目標指標は mbox の呼び出しをベースにすることができます。例えば、[!DNL Analytics]クリック追跡コードを実装する代わりに、A4Tでターゲットのそのまま使用できるクリック追跡機能を使用できます。
* [!DNL Target] UIでA4Tアクティビティのレポートを表示すると、[!DNL Analytics]データが表示されます。 例えば、[!DNL Target]で[!UICONTROL 訪問者]指標を使用する場合、[!UICONTROL 参加者]と呼ばれる[!DNL Target][!UICONTROL 訪問者]指標ではなく、[!DNL Analytics] [!UICONTROL 訪問者]指標を使用します。 この違いは、特に基本的なトラフィック指標([!UICONTROL 訪問者]、[!UICONTROL 訪問回数]、[!UICONTROL ページ表示])およびコンバージョン指標で重要です。
* 既存の[!DNL Target]アクティビティは引き続き[!DNL Target]データ収集を使用するので、A4Tを有効にしても影響を受けません。
* [!DNL Analytics]をレポートソースとして使用する場合は、1つのmboxベースの指標のみ使用できます。
* [!DNL Target]から[!DNL Analytics]へのサーバー間呼び出しは、アクティビティとエクスペリエンスの情報を[!DNL Analytics]に送信します。 この統合によって、[!DNL Target]または[!DNL Analytics]に対する追加のサーバーコールは発生しません。

   状況によっては、[!DNL Target]から[!DNL Analytics]への分類呼び出しが失敗し、アクティビティが[!DNL Analytics]にデータを表示しない場合があります。 この問題が発生した場合は、[Analyticsとターゲットの統合のトラブルシューティング(A4T)](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md)を参照してください。 また、[ClientCare](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB)にお問い合わせの上、詳しくお問い合わせください。

## サポートされるアクティビティの種類{#section_F487896214BF4803AF78C552EF1669AA}

次の表に、[!DNL Target](A4T)のレポートソースとして[!DNL Analytics]をサポートするアクティビティタイプを示します。

| アクティビティのタイプ | A4T との互換性 | メモ（該当する場合） |
|--- |--- |--- |
| 手動トラフィック分割を使用した A/B アクティビティ | ○ |  |
| 自動配分を使用した A/B アクティビティ | ○ | 「[自動配分と自動ターゲットアクティビティのA4Tのサポート](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md)」を参照してください。 |
| 自動ターゲットを使用した A/B アクティビティ | ○ | 「[自動配分と自動ターゲットアクティビティのA4Tのサポート](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md)」を参照してください。 |
| エクスペリエンスターゲット設定（XT） | ○ |  |
| 多変量分析テスト（MVT） | ○ | [!UICONTROL 要素貢献度]レポートを取得するには、mboxベースの目標指標の目標が必要です。  [!UICONTROL 要素貢献度]レポートは、現在、[!DNL Analytics]指標をサポートしていません。 |
| 自動パーソナライゼーション（AP）アクティビティ | × |  |
| Recommendations アクティビティ | ○ |  |
| モバイルアプリ | ○ | Mobile Services SDK バージョン 4.13.1 以降でサポートされています。詳しくは、[Mobile Services のドキュメント](https://experienceleague.adobe.com/docs/mobile-services/using/home.html)を参照してください。 |
| 電子メール | × |  |
| Server Side Delivery API | ○ | 詳細については、「[サーバー側：Target の実装](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md)」を参照してください。 |
| NodeJS SDK | ○ | 詳細については、「[サーバー側：Target の実装](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md)」を参照してください。 |
| AEM 6.1（またはそれ以前）のクラウドサービス統合 | × |  |
| AEM 6.2（またはそれ以降）のクラウドサービス統合 | ○ | 詳しくは、[!DNL Adobe Experience Manager] 6.2ドキュメントの[Adobe Target](https://helpx.adobe.com/experience-manager/6-2/sites/administering/using/target.html)との統合を参照してください。 |
| リダイレクトオファーを使用するアクティビティ | ○ | A4T でリダイレクトオファーを使用する場合は、より厳格な最小要件が適用されます。詳しくは、[リダイレクトオファー - A4T に関する FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md) を参照してください。 |
| Node.JS | ○ | 詳しくは、*Adobe TargetSDK*&#x200B;ガイドの[Node.js SDK](https://adobetarget-sdks.gitbook.io/docs/sdk-reference-guides/nodejs-sdk)を参照してください。 |
| Java SDK | ○ | 詳しくは、*Adobe Target* SDKガイドの[Java SDK](https://adobetarget-sdks.gitbook.io/docs/sdk-reference-guides/java-sdk)を参照してください。 |

まだA4Tをサポートしていないアクティビティタイプがあるので、`orderConfirmPage` mboxなど、重要なコンバージョンmboxを保持または実装することをお勧めします。

## A4Tレポートの例{#section_F0A43A1CB2F04E8282B909E4D7034361}

[!DNL Target]でA4Tレポートを表示するには、**[!UICONTROL アクティビティ]**&#x200B;をクリックし、[!DNL Analytics]をレポートソースとして使用するリストから目的のアクティビティをクリックして、「**[!UICONTROL レポート]**」タブをクリックします。

>[!NOTE]
>
>[!UICONTROL アクティビティ]ページの最上部にある「[!UICONTROL レポートソース]」ドロップダウンリストを使用して、[!DNL Analytics] をレポートソースとして使用するアクティビティのみを表示できます。

レポートの右上にある適切なアイコンをクリックして、レポートの[!UICONTROL テーブル表示]と[!UICONTROL グラフ表示]を切り替えることができます。

以下の図に、使用可能な [!UICONTROL  目標指標を表示する]レポート指標[!UICONTROL ドロップダウンリストを含む、A4T レポートの]グラフ表示[!DNL Analytics]を示します。

![](assets/a4t_report_graph1.png)

以下の図に、使用可能な [!UICONTROL  オーディエンスを表示する ]Audience[!UICONTROL  ドロップダウンリストを含む、A4T レポートの]グラフ表示[!DNL Analytics]を示します。

![](assets/a4t_report_graph2.png)

以下の図に、A4T レポートの[!UICONTROL テーブル表示]を示します。

![](assets/a4t_report_table.png)

[!DNL Analytics] ではなく [!DNL Target] でレポートを表示するには、レポートの上部にある「**[!UICONTROL Analytics で表示]**」をクリックします。

## 「Analytics＆Target：分析のベストプラクティス」チュートリアル{#section_3438E6E77A464424B717A4FD333B84B2}

[Analytics &amp;ターゲットを開きます。[!DNL Adobe Experience League]が提供する分析](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)のベストプラクティスのチュートリアル。

## トレーニングビデオ：

このトピックで説明されている概念の詳細については、次のビデオを参照してください。

### ターゲット分析(A4T)(4:32)![概要バッジ](/help/assets/overview.png)

このビデオでは、[!DNL Target]のレポートソースとして[!DNL Analytics]を使用して最適化プログラムの分析を推進する方法を説明します。

* A4T とは何かと、使用する理由の説明
* A4T の仕組みの説明
* A4T を使用する前に必要な前提条件の理解

>[!VIDEO](https://video.tv.adobe.com/v/17384)

### Analytics/ターゲット統合(A4T)(40:33)![チュートリアルバッジ](/help/assets/tutorial.png)

このビデオは、「[Office Hours](/help/cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)」（アドビカスタマーケアチーム主導による取り組みの 1 つ）の録画です。

* 統合を設定し、統合が機能することを検証する方法
* 統合の仕組み
* Analytics での使用に最適なレポートの詳細
* A4T に関するよくある質問への回答

[Analytics/ターゲット統合(A4T)の営業時間](https://helpx.adobe.com/customer-care-office-hours/target/analytics-target-A4T-integration.html)