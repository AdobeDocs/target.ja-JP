---
keywords: レポート；ip アドレスをブロック；ip アドレスからの訪問者をブロック；レポートをダウンロード；csv；レポート
description: Adobeのレポート機能を使用して、アクティビティのパフォーマ  [!DNL Target]  スを確認する方法を説明します。 ROI を向上させるために、データに基づいてより優れた意思決定を行います。
title: レポートの表示方法
feature: Reports
exl-id: c5710eb3-0c72-47f8-870d-df50453ecf08
source-git-commit: a7a03cba466fbe7abfc8eb1f80292e1a2de7fe2d
workflow-type: tm+mt
source-wordcount: '807'
ht-degree: 42%

---

# レポート

レポートは、データに基づいた意思決定を支援する、[!DNL Adobe Target] アクティビティの進行状況と結果に関する情報を提供します。 レポートデータは、アクティビティを終了するタイミングの決定に役立ち、どのエクスペリエンスのオファーが勝者かを示し、次のアクションを決定するために必要なインサイトや知識を提供できます。

## レポートを表示 {#section_C4591A32F6D04C95A1AD5A377C27C28B}

1. をクリック **[!UICONTROL Activities]** し、リストから目的のアクティビティをクリックします。

   アクティビティが多数ある場合は、[!UICONTROL Type]、[!UICONTROL Status]、[!UICONTROL Reporting Source]、[!UICONTROL Experience Composer]、[!UICONTROL Metrics Type] および [!UICONTROL Activity Source] の各ドロップダウンリストからオプションを選択してリストをフィルタリングできます。

   例えば、「[!UICONTROL Type]」ドロップダウンリストから「[!UICONTROL A/B Test]」と「[!UICONTROL Experience Targeting]」、「[!UICONTROL Status]」ドロップダウンリストから「[!UICONTROL Live]」を選択して、アクティブ状態の A/B テストとエクスペリエンスのターゲット設定アクティビティのみを表示できます。

   次の図は、[!UICONTROL A/B Test] と [!UICONTROL Experience Targeting] の 2 つのタイプが選択された [!UICONTROL Type] ドロップダウンリストを示しています。 A/B テストの 3 つのタイプ（手動、[自動配分](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)、[自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md)）がデフォルトで選択されていることに注意してください。必要に応じて、1 つ以上のタイプの選択を解除できます。

   ![タイプによるレポートのフィルタリング](/help/main/c-reports/assets/report_filters-new.png)

1. 「**[!UICONTROL Reports]**」タブをクリックします。

   各レポートには、レポートを理解しやすくするための凡例が含まれます。

   ![レポートの凡例](/help/main/c-reports/assets/report_menu_bar-new.png)

   この凡例には、以下の情報が表示されます。

   * アクティビティが実行された日付範囲を含むアクティビティステータス
   * [ 見込み勝者エクスペリエンス ](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) （使用可能な場合）。

   >[!NOTE]
   >
   >エクスペリエンスの結果は、少なくとも 1 人の参加者がエクスペリエンスを閲覧した後に表示されます。

1. （オプション）必要に応じて [レポートを設定](/help/main/c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA)します。
1. （オプション）[CSV 形式のレポートをダウンロード](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md)して、Excel や他のツールで分析をおこないます。

   以下のオプションがあります。

   * [!UICONTROL Export Report to CSV]
   * [!UICONTROL Export Order Details to CSV]

1. （任意）「**[!UICONTROL Table View]**」アイコンと「**[!UICONTROL Graph View]**」アイコンをクリックして、レポート形式を切り替えます。

   ![ テーブル表示およびグラフ表示のアイコン ](/help/main/c-reports/assets/table-and-graph-icons.png)

   選択したレポートのタイプによっては、他のビューやレポートを使用できる場合があります。

   | レポートタイプ | 表示 |
   | --- | --- |
   | [自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | **[!UICONTROL Automated Segments]** または **[!UICONTROL Important Attributes]** のアイコンをクリックします。<ul><li>[ 自動セグメントレポート ](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md) は、AP/AT アクティビティのオファー/エクスペリエンスに対する様々な訪問者の反応を示します。 このレポートは、Target のパーソナライゼーションモデルで定義された様々な自動セグメントがアクティビティのオファー／エクスペリエンスにどう反応しているかを示します。</li><li>[ 重要な属性レポート ](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) では、モデルがどのようにパーソナライズを決定するかについて、様々なアクティビティで異なる属性がより重要（または重要でないかを示します。 このレポートは、モデルに影響を及ぼした上位の属性とそれら属性の相対的重要性を示します。</li></ul> |
   | [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md)（AP） | [Automated Personalizationの概要レポート ](/help/main/c-reports/personalization-reports/reports-ap.md) に加えて、「**[!UICONTROL Automated Segments]**」アイコンまたは「**[!UICONTROL Important Attributes]**」アイコンをクリックすることもできます。<ul><li>[ 自動セグメントレポート ](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md) は、AP/AT アクティビティのオファー/エクスペリエンスに対する様々な訪問者の反応を示します。 このレポートは、Target のパーソナライゼーションモデルで定義された様々な自動セグメントがアクティビティのオファー／エクスペリエンスにどう反応しているかを示します。</li><li>[ 重要な属性レポート ](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) では、モデルがどのようにパーソナライズを決定するかについて、様々なアクティビティで異なる属性がより重要（または重要でないかを示します。 このレポートは、モデルに影響を及ぼした上位の属性とそれら属性の相対的重要性を示します。</li></ul> |
   | [多変量分析テスト](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) （MVT） | [ エクスペリエンスパフォーマンスレポート ](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md) に加えて、[ 場所の投稿 ](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) アイコンをクリックして、レポートを切り替えて場所による投稿を表示できます。 |

## 特定のアクティビティタイプに関するその他のレポート情報 {#section_DFE037B9E1C345D3B3BDFCB3AC0359CA}

このトピックおよびそのサブトピックに記載されている一般的なレポート情報に加え、個々のアクティビティタイプに固有の追加情報が本ガイドの他の節に記載されています。

| アクティビティのタイプ | 詳細 |
|--- |--- |
| [A/B テスト](/help/main/c-activities/t-test-ab/test-ab.md) | [!DNL Target] で使用している上昇率、信頼性、統計的アプローチを理解するには、「[A/Bテストのプラン](/help/main/c-activities/t-test-ab/sample-size-determination.md)」を参照してください。 |
| [自動配分レポートの解釈](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) | [!DNL Target] UI で上昇率や信頼性を含む重要な指標を調べることで、[!UICONTROL Auto-Allocate] A/B アクティビティの結果を解釈します。 |
| [自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md)（AT） | AT アクティビティの [!UICONTROL Summary] レポートに関する情報。 詳しくは、「[自動ターゲットの概要レポート](/help/main/c-reports/personalization-reports/auto-target-summary-report.md)」を参照してください。<br>AT アクティビティと AP アクティビティの 2 つの [!UICONTROL Personalization Insights] レポートに関する情報：[!UICONTROL Automated Segments] レポートと [!UICONTROL Important Attributes] レポート。 詳しくは、「[パーソナライゼーションインサイトレポート](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md)」を参照してください。 |
| [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md)（AP） | AP アクティビティに関する、[!UICONTROL Activity Level] レポートと [!UICONTROL Offer Level] レポートの 2 つの [!UICONTROL Automated Personalization Summary] レポートの情報。 詳しくは、「[Automated Personalization概要レポート](/help/main/c-reports/personalization-reports/reports-ap.md)」を参照してください。<br>AT アクティビティと AP アクティビティの 2 つの [!UICONTROL Personalization Insights] レポートに関する情報：[!UICONTROL Automated Segments] レポートと [!UICONTROL Important Attributes] レポート。 詳しくは、「[パーソナライゼーションインサイトレポート](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md)」を参照してください。 |
| [多変量分析テスト](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) （MVT） | MVT アクティビティには、[!UICONTROL Experience Performance] レポートと [!UICONTROL Location Contribution] レポートの 2 つのレポートに関する情報です。 詳しくは、「[エクスペリエンスのパフォーマンスレポート（MVT）](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md) 」と「[場所の貢献度レポート（MVT）](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md)」を参照してください。 |
| [Adobe Target のレポートソースとしての Adobe Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md) （A4T） | レポートソース [!DNL Adobe Analytics] としての使用に関する情報 [!DNL Target] です。A4T では、[!DNL Target] アクティビティの [!DNL Analytics] レポートにアクセスできます。詳しくは、「[Analytics for Target（A4T）レポート](/help/main/c-reports/analytics-for-target-a4t-reporting.md)」を参照してください。 |
|  [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) での [[!DNL Target]  レポート | 最適化プログラムに適した強力な分析機能と時間節約ツールを提供する ](https://experienceleague.adobe.com/ja/docs/customer-journey-analytics){target=_blank}0}Adobe Customer Journey Analytics} と [!DNL Target] の統合に関する情報です。[ |

## 指定された IP アドレスからのレポート データをブロックする

指定したIPアドレスからの訪問者をレポートでカウントすることができます。例えば、内部訪問者からのレポートデータをブロックする場合に役立ちます。

IP フィルターの設定については、[Client Care にお問い合わせ ](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) ください。 このフィルタリングは、[Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) （A4T）をレポートソースとして使用する場合には適用されません。
