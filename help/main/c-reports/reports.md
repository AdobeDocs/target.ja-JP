---
keywords: レポート；ip アドレスをブロック；ip アドレスからの訪問者をブロック；レポートをダウンロード；csv；レポート
description: のレポート機能を習得  [!DNL Adobe Target] て意思決定を強化し、ROI を向上させることで、アクティビティを最適化します。
title: レポートの表示方法
feature: Reports
exl-id: c5710eb3-0c72-47f8-870d-df50453ecf08
source-git-commit: bd65cb9339dbe4b79d26c314cfb81d1fc7226fd2
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 26%

---

# レポート

レポートは、データに基づいた意思決定を支援する、[!DNL Adobe Target] アクティビティの進行状況と結果に関する情報を提供します。 レポートデータは、アクティビティを終了するタイミングの決定に役立ち、どのエクスペリエンスまたはオファーが勝者かを示し、次のアクションを決定するために必要なインサイトや知識を提供できます。

## レポートを表示 {#section_C4591A32F6D04C95A1AD5A377C27C28B}

1. をクリック **[!UICONTROL Activities]** し、リストから目的のアクティビティをクリックします。

   アクティビティが多数ある場合は、フィルターアイコン（![ フィルターアイコン ](/help/main/assets/icons/Filter.svg)）をクリックし、「[!UICONTROL Type]」、「[!UICONTROL Status]」、「[!UICONTROL Reporting Source]」、「[!UICONTROL Experience Composer]」、「[!UICONTROL Metrics Type]」、「[!UICONTROL Decisioning Method]」、「[!UICONTROL Activity Source]」の各リストからオプションを選択してリストをフィルタリングできます。

   例えば、「[!UICONTROL A/B Test]」ドロップダウンリストから「[!UICONTROL Experience Targeting]」と「[!UICONTROL Type]」を選択し、「[!UICONTROL Live]」ドロップダウンリストから「[!UICONTROL Status]」を選択すると、アクティブ状態の [!UICONTROL A/B Test] アクティビティと [!UICONTROL Experience Targeting] アクティビティのみが表示されます。

   次の図は、[!UICONTROL Type] と [!UICONTROL A/B Test] の 2 つのタイプが選択された [!UICONTROL Experience Targeting] ドロップダウンリストを示しています。 A/B テストの 3 つのタイプ（手動、[自動配分](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)、[自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md)）がデフォルトで選択されていることに注意してください。必要に応じて、1 つ以上のタイプの選択を解除できます。

   ![タイプによるレポートのフィルタリング](/help/main/c-reports/assets/report-filters-refresh.png)

1. リストから目的のアクティビティをクリックして、[!UICONTROL Overview] のページを表示します。

1. 左側のレールで「**[!UICONTROL Reports]**」タブをクリックします。

   ![A/B レポート ](/help/main/c-reports/assets/reports-refresh.png)

   各レポートには、レポートを理解しやすくするための凡例が含まれます。

   この凡例には、以下の情報が表示されます。

   * アクティビティが実行された日付範囲を含むアクティビティステータス
   * [ 見込み勝者エクスペリエンス ](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) （使用可能な場合）。

   >[!NOTE]
   >
   >エクスペリエンスの結果は、少なくとも 1 人の参加者がエクスペリエンスを閲覧した後に表示されます。

1. （任意） [ レポート設定アイコン ](/help/main/c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA) レポート設定アイコン ![ レポート設定アイコン ](/help/main/assets/icons/Setting.svg)）をクリックしてレポートを設定します。
1. （任意）「レポートをダウンロード」アイコン（![ レポートをダウンロードアイコン ](/help/main/assets/icons/Download.svg)）をクリックして [CSV 形式でレポートをダウンロード ](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md) し、Excel やその他のツールで分析します。

   以下のオプションがあります。

   * [!UICONTROL Export Report to CSV]
   * [!UICONTROL Export Order Details to CSV]

1. （オプション） **[!UICONTROL Table View]** （![ テーブル表示アイコン ](/help/main/assets/icons/Table.svg)）アイコンと **[!UICONTROL Graph View]** （![ グラフ表示アイコン ](/help/main/assets/icons/GraphTrend.svg)）アイコンをクリックして、レポート形式を切り替えます。

   選択したレポートのタイプによっては、他のビューやレポートを使用できる場合があります。

   | レポートタイプ | 表示 |
   | --- | --- |
   | [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | **[!UICONTROL Automated Segments]** （![ 自動セグメントレポート ](/help/main/assets/icons/AutomatedSegment.svg)）または **[!UICONTROL Important Attributes]** （![ 重要な属性アイコン ](/help/main/assets/icons/ViewList.svg)）アイコンをクリックします。<ul><li>[[!UICONTROL Automated Segments] レポートは ](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md)[!UICONTROL Automated Personalization] ーザーまたは [!UICONTROL Auto-Target] ーザーアクティビティのオファーおよびエクスペリエンスに対する様々な訪問者の反応を示します。 このレポートでは、[!DNL Target] のパーソナライゼーションモデルで定義された様々な自動セグメントがアクティビティのオファーとエクスペリエンスにどのように応答したかを示します。</li><li>[[!UICONTROL Important Attributes] のレポートでは ](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) モデルがどのようにパーソナライズを決定するかについて、様々なアクティビティで様々な属性がより重要（または重要でないかを示します。 このレポートは、モデルに影響を及ぼした上位の属性とそれら属性の相対的重要性を示します。</li></ul> |
   | [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md) （AP） | [[!UICONTROL Automated Personalization Summary] レポートに加えて ](/help/main/c-reports/personalization-reports/reports-ap.md)**[!UICONTROL Automated Segments]** アイコン（![ 自動セグメントレポート ](/help/main/assets/icons/AutomatedSegment.svg)）または **[!UICONTROL Important Attributes]** アイコン（![ 重要な属性アイコン ](/help/main/assets/icons/ViewList.svg)）をクリックできます。<ul><li>[[!UICONTROL Automated Segments] レポートは ](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md)[!UICONTROL Automated Personalization] ーザーまたは [!UICONTROL Auto-Target] ーザーアクティビティのオファーおよびエクスペリエンスに対する様々な訪問者の反応を示します。 このレポートでは、[!DNL Target] のパーソナライゼーションモデルで定義された様々な自動セグメントがアクティビティのオファーとエクスペリエンスにどのように応答したかを示します。</li><li>[[!UICONTROL Important Attributes] のレポートでは ](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) モデルがどのようにパーソナライズを決定するかについて、様々なアクティビティで様々な属性がより重要（または重要でないかを示します。 このレポートは、モデルに影響を及ぼした上位の属性とそれら属性の相対的重要性を示します。</li></ul> |
   | [[!UICONTROL Multivariate Test]](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) （MVT） | [[!UICONTROL Experience Performance] レポートに加えて ](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md)[[!UICONTROL Location Contribution]](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) （![ 場所の投稿アイコン ](/help/main/assets/icons/LocationContribution.svg)）アイコンをクリックすると、レポートを切り替えて場所による投稿を表示できます。 |

## 特定のアクティビティタイプに関するその他のレポート情報 {#section_DFE037B9E1C345D3B3BDFCB3AC0359CA}

このトピックおよびそのサブトピックに記載されている一般的なレポート情報に加え、個々のアクティビティタイプに固有の追加情報が本ガイドの他の節に記載されています。

| アクティビティのタイプ | 詳細 |
|--- |--- |
| [[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md) | [!DNL Target] で使用している上昇率、信頼性、統計的アプローチを理解するには、「[A/Bテストのプラン](/help/main/c-activities/t-test-ab/sample-size-determination.md)」を参照してください。 |
| [ 報告書 [!UICONTROL Auto-Allocate] 解釈 ](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) | [!UICONTROL Auto-Allocate] UI で上昇率や信頼性を含む重要な指標を調べることで、[!DNL Target] A/B アクティビティの結果を解釈します。 |
| [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) （時） | AT アクティビティの [!UICONTROL Summary] レポートに関する情報。 詳しくは、[[!UICONTROL Auto-Target Summary] Report](/help/main/c-reports/personalization-reports/auto-target-summary-report.md) を参照してください。<br>AT アクティビティと AP アクティビティの 2 つの [!UICONTROL Personalization Insights] レポートに関する情報：[!UICONTROL Automated Segments] レポートと [!UICONTROL Important Attributes] レポート。 詳しくは、「[パーソナライゼーションインサイトレポート](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md)」を参照してください。 |
| [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md) （AP） | AP アクティビティに関する、[!UICONTROL Automated Personalization Summary] レポートと [!UICONTROL Activity Level] レポートの 2 つの [!UICONTROL Offer Level] レポートの情報。 詳しくは、「[Automated Personalization概要レポート](/help/main/c-reports/personalization-reports/reports-ap.md)」を参照してください。<br>AT アクティビティと AP アクティビティの 2 つの [!UICONTROL Personalization Insights] レポートに関する情報：[!UICONTROL Automated Segments] レポートと [!UICONTROL Important Attributes] レポート。 詳しくは、「[パーソナライゼーションインサイトレポート](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md)」を参照してください。 |
| [[!UICONTROL Multivariate Test]](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) （MVT） | MVT アクティビティには、[!UICONTROL Experience Performance] レポートと [!UICONTROL Location Contribution] レポートの 2 つのレポートに関する情報です。 詳しくは、[ エクスペリエンスパフォーマンスレポート ](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md) （MVT）および [ 場所の貢献度レポート ](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) （MVT）を参照してください。 |
| [[!DNL Adobe Analytics] Adobe Targetのレポート用Sourceとして ](/help/main/c-integrating-target-with-mac/a4t/a4t.md) （A4T） | [!DNL Adobe Analytics] を [!DNL Target] （A4T）のレポートソースとして使用する方法に関する情報です。 A4T では、[!DNL Target] アクティビティの [!DNL Analytics] レポートにアクセスできます。詳しくは、「[Analytics for Target（A4T）レポート](/help/main/c-reports/analytics-for-target-a4t-reporting.md)」を参照してください。 |
|  [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) での [[!DNL Target]  レポート | 最適化プログラムに適した強力な分析機能と時間節約ツールを提供する [0}Adobe Customer Journey Analytics} と ](https://experienceleague.adobe.com/ja/docs/customer-journey-analytics){target=_blank} の統合に関する情報です。[!DNL Target] |

## 指定された IP アドレスからのレポート データをブロックする

指定したIPアドレスからの訪問者をレポートでカウントすることができます。このオプションは、例えば、内部訪問者からのレポートデータをブロックする場合に役立ちます。

IP フィルターの設定については、[Client Care にお問い合わせ ](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) ください。 このフィルタリングは、[Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) （A4T）をレポートソースとして使用する場合には適用されません。
