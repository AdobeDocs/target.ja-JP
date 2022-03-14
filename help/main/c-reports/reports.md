---
keywords: レポート、ip アドレスのブロック、ip アドレスからの訪問者のブロック、レポートのダウンロード、csv、レポート
description: Adobe [!DNL Target] をクリックして、アクティビティのパフォーマンスを確認します。 データに基づいてより的確な意思決定を行い、ROI を向上させます。
title: レポートの表示方法
feature: Reports
exl-id: c5710eb3-0c72-47f8-870d-df50453ecf08
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '859'
ht-degree: 63%

---

# レポート

レポートには、 [!DNL Adobe Target] アクティビティを使用してデータに基づいた意思決定をおこなうことができます。 レポートデータは、アクティビティを終了するタイミングの決定に役立ち、どのエクスペリエンスのオファーが勝者かを示し、次のアクションを決定するために必要なインサイトや知識を提供できます。

## レポートの表示 {#section_C4591A32F6D04C95A1AD5A377C27C28B}

1. 「**[!UICONTROL アクティビティ]**」をクリックし、リストから目的のアクティビティをクリックします。

   多数のアクティビティが表示される場合は、[!UICONTROL 種類]、[!UICONTROL ステータス]、[!UICONTROL レポートソース]、[!UICONTROL Experience Composer]、[!UICONTROL 指標のタイプ]、[!UICONTROL アクティビティソース]のドロップダウンリストからオプションを選択して、リストにフィルターを適用できます。

   例えば、[!UICONTROL タイプ]ドロップダウンリストから「[!UICONTROL A/B テスト]」と「[!UICONTROL エクスペリエンスターゲット設定]」を選択し、[!UICONTROL ステータス]ドロップダウンリストから「[!UICONTROL ライブ]」を選択すると、アクティブな状態にある A/B テストとエクスペリエンスターゲット設定のアクティビティのみが表示されます。

   以下の図に、2 つのタイプが選択された[!UICONTROL タイプ]ドロップダウンリストを示します [!UICONTROL A/B テスト] および [!UICONTROL エクスペリエンスのターゲット設定]. A/B テストの 3 つのタイプ（手動、[自動配分](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)、[自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md)）がデフォルトで選択されていることに注意してください。必要に応じて、1 つ以上のタイプの選択を解除できます。

   ![タイプによるレポートのフィルタリング](/help/main/c-reports/assets/report_filters-new.png)

1. 「**[!UICONTROL レポート]**」タブをクリックします。

   各レポートには、レポートを理解しやすくするための凡例が含まれます。

   ![レポートの凡例](/help/main/c-reports/assets/report_menu_bar-new.png)

   この凡例には、以下の情報が表示されます。

   * アクティビティが実行された日付範囲を含むアクティビティステータス
   * この [予測される勝者エクスペリエンス](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) （使用可能な場合）

   >[!NOTE]
   >
   >エクスペリエンスの結果は、少なくとも 1 人の参加者がエクスペリエンスを閲覧した後に表示されます。

1. （オプション）必要に応じて [レポートを設定](/help/main/c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA)します。
1. （オプション）[CSV 形式のレポートをダウンロード](/help/main/c-reports/downloading-data-in-csv-file.md#concept_3F276FF2BBB2499388F97451D6DE2E75)して、Excel や他のツールで分析をおこないます。

   以下のオプションがあります。

   * [!UICONTROL レポートを CSV に書き出す]
   * [!UICONTROL 注文の詳細を CSV に書き出す]

1. （オプション）**[!UICONTROL テーブル表示]**&#x200B;および&#x200B;****&#x200B;グラフ表示アイコンをクリックして、レポートの形式を切り替えます。

   ![テーブルおよびグラフ表示のアイコン](/help/main/c-reports/assets/table-and-graph-icons.png)

   選択したレポートのタイプに応じて、他のビューやレポートも使用できる場合があります。

   | レポートタイプ | 表示 |
   | --- | --- |
   | [自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | 次をクリック： **[!UICONTROL 自動セグメント]** または **[!UICONTROL 重要な属性]** アイコン。<ul><li>この [自動セグメントレポート](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md) は、AP/AT アクティビティでのオファーやエクスペリエンスに対する異なる訪問者の反応を示します。 このレポートは、Target のパーソナライゼーションモデルで定義された様々な自動セグメントがアクティビティのオファー／エクスペリエンスにどう反応しているかを示します。</li><li>この [重要な属性レポート](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) は、異なるアクティビティで、モデルによるパーソナライゼーションの決定にとって異なる属性が重要である（あるいはそれ以下である）方法を示しています。 このレポートは、モデルに影響を及ぼした上位の属性とそれら属性の相対的重要性を示します。</li></ul> |
   | [自動パーソナライゼーション](/help/main/c-activities/t-automated-personalization/automated-personalization.md)（AP） | また、 [Automated Personalizationサマリレポート](/help/main/c-reports/reports-ap.md)をクリックした場合、 **[!UICONTROL 自動セグメント]** または **[!UICONTROL 重要な属性]** アイコン。<ul><li>この [自動セグメントレポート](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md) は、AP/AT アクティビティでのオファーやエクスペリエンスに対する異なる訪問者の反応を示します。 このレポートは、Target のパーソナライゼーションモデルで定義された様々な自動セグメントがアクティビティのオファー／エクスペリエンスにどう反応しているかを示します。</li><li>この [重要な属性レポート](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) 様々なアクティビティで、モデルによるパーソナライゼーションの決定にとって異なる属性が重要である（あるいはそれほど重要でない）方法を示します。 このレポートは、モデルに影響を及ぼした上位の属性とそれら属性の相対的重要性を示します。</li></ul> |
   | [多変量分析テスト](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) （MVT） | また、 [エクスペリエンスのパフォーマンスレポート](/help/main/c-reports/experience-performance-report.md)をクリックした場合、 [場所の貢献度](/help/main/c-reports/location-contribution-report.md) アイコンをクリックし、場所別の貢献度を表示するレポートを切り替えます。 |

## 特定のアクティビティタイプに関する追加のレポート情報 {#section_DFE037B9E1C345D3B3BDFCB3AC0359CA}

このトピックおよびそのサブトピックに記載されている一般的なレポート情報に加え、個々のアクティビティタイプに固有の追加情報が本ガイドの他の節に記載されています。

| アクティビティのタイプ | 詳細 |
|--- |--- |
| [A/B テスト](/help/main/c-activities/t-test-ab/test-ab.md) | [!DNL Target] で使用している上昇率、信頼性、統計的アプローチを理解するには、「[A/Bテストのプラン](/help/main/c-activities/t-test-ab/sample-size-determination.md)」を参照してください。 |
| [自動配分レポートの解釈](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) | 結果の解釈 [!UICONTROL 自動配分] 上昇率や信頼性を含む、 [!DNL Target] UI |
| [自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md)（AT） | AT アクティビティの[!UICONTROL 概要]レポートに関する情報です。詳しくは、「[自動ターゲットの概要レポート](/help/main/c-reports/auto-target-summary-report.md)」を参照してください。<br>AT および AP アクティビティの 2 つの[!UICONTROL パーソナライゼーションインサイト]レポートに関する情報：[!UICONTROL 自動セグメント]レポートと[!UICONTROL 重要属性]レポート。詳しくは、「[パーソナライゼーションインサイトレポート](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md)」を参照してください。 |
| [自動パーソナライゼーション](/help/main/c-activities/t-automated-personalization/automated-personalization.md)（AP） | AP アクティビティに関する、2 つの [!UICONTROL 自動パーソナライゼーション概要レポートの情報]：[!UICONTROL アクティビティレベル]レポートおよび[!UICONTROL オファーレベル]レポート。詳しくは、「[自動パーソナライゼーション概要レポート](/help/main/c-reports/reports-ap.md)」を参照してください。<br>AT および AP アクティビティの 2 つの[!UICONTROL パーソナライゼーションインサイト]レポートに関する情報：[!UICONTROL 自動セグメント]レポートと[!UICONTROL 重要属性]レポート。詳しくは、「[パーソナライゼーションインサイトレポート](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md)」を参照してください。 |
| [多変量分析テスト](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) （MVT） | MVT アクティビティの 2 つのレポートに関する情報：[!UICONTROL エクスペリエンスのパフォーマンス]レポートおよび[!UICONTROL 場所の貢献度]レポート。詳しくは、「[エクスペリエンスのパフォーマンスレポート（MVT）](/help/main/c-reports/experience-performance-report.md) 」と「[場所の貢献度レポート（MVT）](/help/main/c-reports/location-contribution-report.md)」を参照してください。 |
| [Adobe Target のレポートソースとしての Adobe Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md) （A4T） | レポートソース [!DNL Adobe Analytics] としての使用に関する情報 [!DNL Target] です。A4T では、[!DNL Target] アクティビティの [!DNL Analytics] レポートにアクセスできます。詳しくは、「[Analytics for Target（A4T）レポート](/help/main/c-reports/analytics-for-target-a4t-reporting.md)」を参照してください。 |

## 指定した IP アドレスからのレポートデータをブロックする

指定したIPアドレスからの訪問者をレポートでカウントすることができます。これは、例えば、内部訪問者からのレポートデータをブロックする場合に役立ちます。

[IP フィルターの設定については、ClientCare にお問い合わせください。](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)このフィルターは、[Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE)（A4T）をレポートソースとして使用している場合は適用されません。
