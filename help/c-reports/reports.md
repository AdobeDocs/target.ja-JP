---
keywords: reports;block ip address;block visitor from ip address;download reports;csv;reporting
description: レポートは、Adobe Targetアクティビティのパフォーマンスに関する情報を提供します
title: レポート
feature: reports
topic: Standard
uuid: 8d20f4e7-72fd-4872-a21f-54ce16a2d2ab
translation-type: tm+mt
source-git-commit: e18f18e6d6e0b8fc6eb5ada845e2fe5377d6c5d0
workflow-type: tm+mt
source-wordcount: '827'
ht-degree: 66%

---


# レポート{#reports}

Reports provide information about the progress and results of your [!DNL Adobe Target] activities that help you make decisions based on your data. レポートデータは、アクティビティを終了するタイミングの決定、推奨結果であるオファーのエクスペリエンスの表示、次のアクションを決定するために必要なインサイトや学習の提供に役立ちます。

## レポートの表示 {#section_C4591A32F6D04C95A1AD5A377C27C28B}

1. 「**[!UICONTROL アクティビティ]**」をクリックし、リストから目的のアクティビティをクリックします。

   多数のアクティビティが表示される場合は、[!UICONTROL 種類]、[!UICONTROL ステータス]、[!UICONTROL レポートソース]、[!UICONTROL Experience Composer]、[!UICONTROL 指標のタイプ]、[!UICONTROL アクティビティソース]のドロップダウンリストからオプションを選択して、リストにフィルターを適用できます。

   例えば、[!UICONTROL タイプ]ドロップダウンリストから「[!UICONTROL A/B テスト]」と「[!UICONTROL エクスペリエンスターゲット設定]」を選択し、[!UICONTROL ステータス]ドロップダウンリストから「[!UICONTROL ライブ]」を選択すると、アクティブな状態にある A/B テストとエクスペリエンスターゲット設定のアクティビティのみが表示されます。

   以下の図に、2 つのタイプが選択された[!UICONTROL タイプ]ドロップダウンリストを示します [!UICONTROL A/B Test] and [!UICONTROL Experience Targeting]. A/B テストの 3 つのタイプ（手動、[自動配分](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)、[自動ターゲット](/help/c-activities/auto-target/auto-target-to-optimize.md)）がデフォルトで選択されていることに注意してください。必要に応じて、1 つ以上のタイプの選択を解除できます。

   ![タイプによるレポートのフィルタリング](/help/c-reports/assets/report_filters-new.png)

1. 「**[!UICONTROL レポート]**」タブをクリックします。

   各レポートには、レポートを理解しやすくするための凡例が含まれます。

   ![レポートの凡例](/help/c-reports/assets/report_menu_bar-new.png)

   この凡例には、以下の情報が表示されます。

   * アクティビティが実行された日付範囲を含むアクティビティステータス
   * The [projected winning experience](/help/c-activities/automated-traffic-allocation/determine-winner.md) (if available).

   >[!NOTE]
   >
   >エクスペリエンスの結果は、少なくとも 1 人の参加者がエクスペリエンスを閲覧した後に表示されます。

1. （オプション）必要に応じて [レポートを設定](../c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA)します。
1. （オプション）[CSV 形式のレポートをダウンロード](../c-reports/downloading-data-in-csv-file.md#concept_3F276FF2BBB2499388F97451D6DE2E75)して、Excel や他のツールで分析をおこないます。

   以下のオプションがあります。

   * [!UICONTROL レポートを CSV に書き出す]
   * [!UICONTROL 注文の詳細を CSV に書き出す]

1. （オプション）**[!UICONTROL テーブル表示]**&#x200B;および&#x200B;****&#x200B;グラフ表示アイコンをクリックして、レポートの形式を切り替えます。

   ![テーブルとグラフの表示アイコン](/help/c-reports/assets/table-and-graph-icons.png)

   選択したレポートのタイプに応じて、次のような他の表示やレポートを利用できます。

   | レポートタイプ | 表示 |
   | --- | --- |
   | [自動ターゲット](/help/c-activities/auto-target/auto-target-to-optimize.md) | 「 **[!UICONTROL 自動セグメント]** 」アイコンまたは「 **[!UICONTROL 重要な属性]** 」アイコンをクリックします。<ul><li>[自動セグメントレポート](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md) は、AP/ATアクティビティのオファー/エクスペリエンスに対する訪問者の反応が異なる様子を示します。 このレポートは、Target のパーソナライゼーションモデルで定義された様々な自動セグメントがアクティビティのオファー／エクスペリエンスにどう反応しているかを示します。</li><li>The [Important Attributes report](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md) shows how, in different activities, different attributes are more (or less) important to how the model decides to personalize. このレポートは、モデルに影響を及ぼした上位の属性とそれら属性の相対的重要性を示します。</li></ul> |
   | [自動パーソナライゼーション](/help/c-activities/t-automated-personalization/automated-personalization.md)（AP） | [Automated Personalizationサマリレポートに加えて](/help/c-reports/reports-ap.md)、 **[!UICONTROL 自動セグメント]** (Automated Segments)アイコンまたは **[!UICONTROL 重要な属性]** (Important Attributes)アイコンをクリックできます。<ul><li>[自動セグメントレポート](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md) は、AP/ATアクティビティのオファー/エクスペリエンスに対する訪問者の反応が異なる様子を示します。 このレポートは、Target のパーソナライゼーションモデルで定義された様々な自動セグメントがアクティビティのオファー／エクスペリエンスにどう反応しているかを示します。</li><li>The [Important Attributes report](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md) hows how, in different activities, different attributes are more (or less) important to how the model decides to personalize. このレポートは、モデルに影響を及ぼした上位の属性とそれら属性の相対的重要性を示します。</li></ul> |
   | [多変量分析テスト](/help/c-activities/c-multivariate-testing/multivariate-testing.md) （MVT） | エ [クスペリエンスのパフォーマンスレポートに加えて](/help/c-reports/experience-performance-report.md)、「場所の貢献度 [](/help/c-reports/location-contribution-report.md) 」アイコンをクリックして、レポートを切り替え、場所ごとの貢献度を表示できます。 |

## Additional reporting information for specific activity types {#section_DFE037B9E1C345D3B3BDFCB3AC0359CA}

このトピックおよびそのサブトピックに記載されている一般的なレポート情報に加え、個々のアクティビティタイプに固有の追加情報が本ガイドの他の節に記載されています。

| アクティビティのタイプ | 詳細 |
|--- |--- |
| [A/B テスト](/help/c-activities/t-test-ab/test-ab.md) | [!DNL Target] で使用している上昇率、信頼性、統計的アプローチを理解するには、「[A/Bテストのプラン](/help/c-activities/t-test-ab/sample-size-determination.md)」を参照してください。 |
| [自動配分レポートの解釈](/help/c-activities/automated-traffic-allocation/determine-winner.md) | [!UICONTROL 自動配分] A/Bアクティビティの結果を解釈します。そのためには、 [!DNL Target] UIの上昇率や信頼性など、重要な指標を調べます。 |
| [自動ターゲット](/help/c-activities/auto-target/auto-target-to-optimize.md)（AT） | AT アクティビティの[!UICONTROL 概要]レポートに関する情報です。詳しくは、「[自動ターゲットの概要レポート](/help/c-reports/auto-target-summary-report.md)」を参照してください。<br>AT および AP アクティビティの 2 つの[!UICONTROL パーソナライゼーションインサイト]レポートに関する情報：[!UICONTROL 自動セグメント]レポートと[!UICONTROL 重要属性]レポート。詳しくは、「[パーソナライゼーションインサイトレポート](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md)」を参照してください。 |
| [自動パーソナライゼーション](/help/c-activities/t-automated-personalization/automated-personalization.md)（AP） | AP アクティビティに関する、2 つの [!UICONTROL 自動パーソナライゼーション概要レポートの情報]：[!UICONTROL アクティビティレベル]レポートおよび[!UICONTROL オファーレベル]レポート。詳しくは、「[自動パーソナライゼーション概要レポート](/help/c-reports/reports-ap.md)」を参照してください。<br>AT および AP アクティビティの 2 つの[!UICONTROL パーソナライゼーションインサイト]レポートに関する情報：[!UICONTROL 自動セグメント]レポートと[!UICONTROL 重要属性]レポート。詳しくは、「[パーソナライゼーションインサイトレポート](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md)」を参照してください。 |
| [多変量分析テスト](/help/c-activities/c-multivariate-testing/multivariate-testing.md) （MVT） | MVT アクティビティの 2 つのレポートに関する情報：[!UICONTROL エクスペリエンスのパフォーマンス]レポートおよび[!UICONTROL 場所の貢献度]レポート。詳しくは、「[エクスペリエンスのパフォーマンスレポート（MVT）](/help/c-reports/experience-performance-report.md) 」と「[場所の貢献度レポート（MVT）](/help/c-reports/location-contribution-report.md)」を参照してください。 |
| [Adobe Target のレポートソースとしての Adobe Analytics](/help/c-integrating-target-with-mac/a4t/a4t.md) （A4T） | レポートソース [!DNL Adobe Analytics] としての使用に関する情報 [!DNL Target] です。A4T では、[!DNL Target] アクティビティの [!DNL Analytics] レポートにアクセスできます。詳しくは、「[Analytics for Target（A4T）レポート](/help/c-reports/analytics-for-target-a4t-reporting.md)」を参照してください。 |

## 指定したIPアドレスからレポートデータをブロックする

指定したIPアドレスからの訪問者をレポートでカウントすることができます。これは、例えば、内部訪問者からのレポートデータをブロックする場合に便利です。

[IP フィルターの設定については、ClientCare にお問い合わせください。](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)このフィルターは、[Analytics for Target](../c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE)（A4T）をレポートソースとして使用している場合は適用されません。
