---
description: レポートには、アクティビティのパフォーマンスに関する情報が表示されます。
keywords: レポート、ip address、訪問者をIPアドレスからブロックする、ダウンロードレポート、csv
seo-description: レポートには、アクティビティのパフォーマンスに関する情報が表示されます
seo-title: レポート
solution: 'Target '
subtopic: 多変量分析テスト
title: レポート
topic: Standard
uuid: 8d20f4e7-72fd-4872-a21f-54ce16a2d2ab
translation-type: tm+mt
source-git-commit: 634ea3ccbd875aff27391e79812028f236f53608

---


# レポート{#reports}

レポートには、データに基づいて決定を下す際に役立つアクティビティの進捗状況と結果に関する情報が表示されます。レポートデータを使用すると、テストを終了するタイミングを決定したり、勝者のエクスペリエンスを表示したり、次のアクションを決定するために必要なインサイトや学習を提供したりできます。

>[!NOTE]
>
>指定したIPアドレスからの訪問者をレポートでカウントすることができます。IP フィルターの設定については、ClientCare にお問い合わせください。このフィルターは、[Analytics for Target](../c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE)（A4T）をレポートソースとして使用している場合は適用されません。

## 特定のアクティビティタイプのレポート情報 {#section_DFE037B9E1C345D3B3BDFCB3AC0359CA}

このトピックおよびそのサブトピックに記載されている一般的なレポート情報に加え、個々のアクティビティタイプに固有の追加情報が本ガイドの他の節に記載されています。

| アクティビティのタイプ | 詳細 |
|--- |--- |
| [A/B テスト](/help/c-activities/t-test-ab/test-ab.md) | [!DNL Target] で使用している上昇率、信頼性、統計的アプローチを理解するには、「[A/Bテストのプラン](/help/c-activities/t-test-ab/sample-size-determination.md)」を参照してください。 |
| [自動ターゲット](/help/c-activities/auto-target-to-optimize.md)（AT） | AT アクティビティの[!UICONTROL 概要]レポートに関する情報です。詳しくは、「[自動ターゲットの概要レポート](/help/c-reports/auto-target-summary-report.md)」を参照してください。<br>AT および AP アクティビティの 2 つの[!UICONTROL パーソナライゼーションインサイト]レポートに関する情報：[!UICONTROL 自動セグメント]レポートと[!UICONTROL 重要属性]レポート。詳しくは、「[パーソナライゼーションインサイトレポート](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md)」を参照してください。 |
| [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md)（AP） | AP アクティビティに関する、2 つの [!UICONTROL Automated Personalization 概要レポートの情報]：[!UICONTROL アクティビティレベル]レポートおよび[!UICONTROL オファーレベル]レポート。詳しくは、「[Automated Personalization 概要レポート](/help/c-reports/reports-ap.md)」を参照してください。<br>AT および AP アクティビティの 2 つの[!UICONTROL パーソナライゼーションインサイト]レポートに関する情報：[!UICONTROL 自動セグメント]レポートと[!UICONTROL 重要属性]レポート。詳しくは、「[パーソナライゼーションインサイトレポート](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md)」を参照してください。 |
| [多変量分析テスト](/help/c-activities/c-multivariate-testing/multivariate-testing.md) （MVT） | MVT アクティビティの 2 つのレポートに関する情報：[!UICONTROL エクスペリエンスのパフォーマンス]レポートおよび[!UICONTROL 場所の貢献度]レポート。詳しくは、「[エクスペリエンスのパフォーマンスレポート（MVT）](/help/c-reports/experience-performance-report.md) 」と「[場所の貢献度レポート（MVT）](/help/c-reports/location-contribution-report.md)」を参照してください。 |
| [Adobe Target のレポートソースとしての Adobe Analytics](/help/c-integrating-target-with-mac/a4t/a4t.md) （A4T） | レポートソース [!DNL Adobe Analytics] としての使用に関する情報 [!DNL Target] です。A4T では、[!DNL Target] アクティビティの [!DNL Analytics] レポートにアクセスできます。詳しくは、「[Analytics for Target（A4T）レポート](/help/c-reports/analytics-for-target-a4t-reporting.md)」を参照してください。 |

## レポートの表示 {#section_C4591A32F6D04C95A1AD5A377C27C28B}

1. 「**[!UICONTROL アクティビティ]**」をクリックし、リストから目的のアクティビティをクリックします。

   多数のアクティビティが表示される場合は、「[!UICONTROL 種類]」、「[!UICONTROL ステータス]」、「[!UICONTROL レポートソース]」、「[!UICONTROL Experience Composer]」、「[!UICONTROL 指標のタイプ]」、「[!UICONTROL アクティビティソース]」のドロップダウンリストからオプションを選択して、リストにフィルターを適用できます。

   例えば、[!UICONTROL タイプ]ドロップダウンリストから「[!UICONTROL A/B テスト]」と「[!UICONTROL エクスペリエンスターゲット設定]」を選択し、[!UICONTROL ステータス]ドロップダウンリストから「[!UICONTROL ライブ]」を選択すると、アクティブな状態にある A/B テストとエクスペリエンスターゲット設定のアクティビティのみが表示されます。

   以下の図に、2 つのタイプが選択された[!UICONTROL タイプ]ドロップダウンリストを示します。A/Bテストおよびエクスペリエンスのターゲット設定を参照してください。デフォルトでは、3種類のA/Bテスト（手動 [、自動配分](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)、 [自動ターゲット](/help/c-activities/auto-target-to-optimize.md)）が選択されています。必要に応じて、1つまたは複数のタイプを選択解除できます。

   ![タイプ別のレポートのフィルター](/help/c-reports/assets/report_filters-new.png)

1. 「**[!UICONTROL レポート]**」タブをクリックします。

   各レポートには、レポートを理解しやすくするための凡例が含まれます。

   ![レポートの凡例](/help/c-reports/assets/report_menu_bar-new.png)

   この凡例には、以下の情報が表示されます。

   * アクティビティが実行された日付範囲を含むアクティビティステータス
   * 予測される勝者エクスペリエンス（ある場合）。
   >[!NOTE]
   >
   >エクスペリエンスの結果は、少なくとも 1 人の参加者がエクスペリエンスを閲覧した後に表示されます。

1. （オプション）必要に応じて [レポートを設定](../c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA)します。
1. （オプション）[CSV 形式のレポートをダウンロード](../c-reports/downloading-data-in-csv-file.md#concept_3F276FF2BBB2499388F97451D6DE2E75)して、Excel や他のツールで分析をおこないます。

   以下のオプションがあります。

   * [!UICONTROL レポートを CSV に書き出す]
   * [!UICONTROL 注文の詳細を CSV に書き出す]

1. （オプション）**[!UICONTROL テーブル表示]** および **]グラフ表示[!UICONTROL ** アイコンをクリックして、レポートの形式を切り替えます。

   多変量分析テストの場合のみ、**[!UICONTROL 場所の貢献度]** （![場所の貢献度アイコン](assets/icon_location_contribution.png)）アイコンをクリックして、場所ごとの貢献度を表示するレポートを切り替えます。
