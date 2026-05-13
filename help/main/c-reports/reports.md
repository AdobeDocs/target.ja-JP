---
keywords: レポート；ブロック ip アドレス；ブロック訪問者のip アドレス；レポートのダウンロード；csv；レポート
description: ' [!DNL Adobe Target]のレポート機能を使いこなしてアクティビティを最適化し、意思決定を強化してROIを向上させます。'
title: レポートを表示するにはどうすればよいですか？
feature: Reports
exl-id: c5710eb3-0c72-47f8-870d-df50453ecf08
TQID: https://experienceleague.adobe.com/aRp-t-Z-Hfu5O01RqfxnKyHHL2suM2ahkteDQJShGQI
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: e0eb8757-182f-49f3-94a4-1587d16f5094id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 823
ht-degree: 26%

---

# レポート

レポートでは、データに基づいた意思決定に役立つ、[!DNL Adobe Target] アクティビティの進捗状況と結果に関する情報が提供されます。 レポートデータは、アクティビティを終了するタイミングを決定し、勝者となるエクスペリエンスやオファーを示し、次のアクションを決定するために必要なインサイトや学びを提供するのに役立ちます。

## レポートの表示 {#section_C4591A32F6D04C95A1AD5A377C27C28B}

1. をクリック **[!UICONTROL Activities]** し、リストから目的のアクティビティをクリックします。

   アクティビティが多い場合は、フィルターアイコン（![ フィルターアイコン ](/help/main/assets/icons/Filter.svg)）をクリックして、[!UICONTROL Type]、[!UICONTROL Status]、[!UICONTROL Reporting Source]、[!UICONTROL Experience Composer]、[!UICONTROL Metrics Type]、[!UICONTROL Decisioning Method]、および[!UICONTROL Activity Source] リストからオプションを選択して、リストをフィルタリングできます。

   例えば、[!UICONTROL Type] ドロップダウンリストから[!UICONTROL A/B Test]と[!UICONTROL Experience Targeting]を選択し、[!UICONTROL Status] ドロップダウンリストから[!UICONTROL Live]を選択して、アクティブな状態にある[!UICONTROL A/B Test]と[!UICONTROL Experience Targeting]のアクティビティのみを表示できます。

   次の図は、[!UICONTROL Type] ドロップダウンリストを示しており、2種類が選択されています：[!UICONTROL A/B Test]と[!UICONTROL Experience Targeting]。 A/B テストの 3 つのタイプ（手動、[自動配分](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)、[自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md)）がデフォルトで選択されていることに注意してください。 必要に応じて、1 つ以上のタイプの選択を解除できます。

   ![タイプによるレポートのフィルタリング](/help/main/c-reports/assets/report-filters-refresh.png)

1. リストから目的のアクティビティをクリックして、[!UICONTROL Overview] ページを表示します。

1. 左側のパネルの「**[!UICONTROL Reports]**」タブをクリックします。

   ![A/B レポート ](/help/main/c-reports/assets/reports-refresh.png)

   各レポートには、レポートを理解しやすくするための凡例が含まれます。

   この凡例には、以下の情報が表示されます。

   * アクティビティが実行された日付範囲を含むアクティビティステータス
   * [予測される勝者エクスペリエンス ](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) （使用可能な場合）。

   >[!NOTE]
   >
   >エクスペリエンスの結果は、少なくとも 1 人の参加者がエクスペリエンスを閲覧した後に表示されます。

1. （オプション） [ レポート設定アイコン（![ レポート設定アイコン ](/help/main/assets/icons/Setting.svg)）をクリックして、レポート ](/help/main/c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA)を設定します。
1. （オプション）レポートのダウンロードアイコン（![ レポートのダウンロードアイコン ](/help/main/assets/icons/Download.svg)）をクリックして、[Excelやその他のツールでの分析のためにCSV形式](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md)でレポートをダウンロードします。

   以下のオプションがあります。

   * [!UICONTROL Export Report to CSV]
   * [!UICONTROL Export Order Details to CSV]

1. （オプション） **[!UICONTROL Table View]** （![ テーブル表示アイコン ](/help/main/assets/icons/Table.svg)）と&#x200B;**[!UICONTROL Graph View]** （![ グラフ表示アイコン ](/help/main/assets/icons/GraphTrend.svg)）アイコンをクリックして、レポート形式を切り替えます。

   選択したレポートのタイプによっては、他のビューやレポートが使用できる場合があります。

   | レポートタイプ | 表示 |
   | --- | --- |
   | [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | **[!UICONTROL Automated Segments]** （![自動セグメントレポート ](/help/main/assets/icons/AutomatedSegment.svg)）または&#x200B;**[!UICONTROL Important Attributes]** （![重要な属性アイコン ](/help/main/assets/icons/ViewList.svg)）アイコンをクリックします。<ul><li>[[!UICONTROL Automated Segments] レポート ](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md)は、[!UICONTROL Automated Personalization]または[!UICONTROL Auto-Target] アクティビティのオファーとエクスペリエンスに対する様々な訪問者の反応の違いを示しています。 このレポートでは、[!DNL Target]個のパーソナライゼーションモデルによって定義されたさまざまな自動セグメントが、アクティビティのオファーとエクスペリエンスにどのように反応したかを示します。</li><li>[[!UICONTROL Important Attributes] レポート ](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md)は、異なるアクティビティにおいて、モデルがパーソナライズを決定する際に、異なる属性が多かれ少なかれ重要であることを示しています。 このレポートは、モデルに影響を及ぼした上位の属性とそれら属性の相対的重要性を示します。</li></ul> |
   | [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md) （AP） | [[!UICONTROL Automated Personalization Summary] レポート ](/help/main/c-reports/personalization-reports/reports-ap.md)に加えて、**[!UICONTROL Automated Segments]** （![自動セグメントレポート ](/help/main/assets/icons/AutomatedSegment.svg)）または&#x200B;**[!UICONTROL Important Attributes]** （![重要な属性アイコン ](/help/main/assets/icons/ViewList.svg)）アイコンをクリックできます。<ul><li>[[!UICONTROL Automated Segments] レポート ](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md)は、[!UICONTROL Automated Personalization]または[!UICONTROL Auto-Target] アクティビティのオファーとエクスペリエンスに対する様々な訪問者の反応の違いを示しています。 このレポートでは、[!DNL Target]個のパーソナライゼーションモデルによって定義されたさまざまな自動セグメントが、アクティビティのオファーとエクスペリエンスにどのように反応したかを示します。</li><li>[[!UICONTROL Important Attributes] レポート ](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md)は、異なるアクティビティにおいて、モデルがパーソナライズを決定する際に、異なる属性が多かれ少なかれ重要であることを示しています。 このレポートは、モデルに影響を及ぼした上位の属性とそれら属性の相対的重要性を示します。</li></ul> |
   | [[!UICONTROL Multivariate Test]](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) （MVT） | [[!UICONTROL Experience Performance] レポート ](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md)に加えて、[[!UICONTROL Location Contribution]](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) （![場所の貢献度アイコン ](/help/main/assets/icons/LocationContribution.svg)）アイコンをクリックすると、レポートを切り替えて、場所ごとの貢献度を表示できます。 |

## 特定のアクティビティタイプに関する追加レポート情報 {#section_DFE037B9E1C345D3B3BDFCB3AC0359CA}

このトピックおよびそのサブトピックに記載されている一般的なレポート情報に加え、個々のアクティビティタイプに固有の追加情報が本ガイドの他の節に記載されています。

| アクティビティのタイプ | 詳細 |
|--- |--- |
| [[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md) | [!DNL Target] で使用している上昇率、信頼性、統計的アプローチを理解するには、「[A/Bテストのプラン](/help/main/c-activities/t-test-ab/sample-size-determination.md)」を参照してください。 |
| [[!UICONTROL Auto-Allocate]件のレポートを解釈](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) | [!DNL Target] UIで上昇率と信頼性を含む重要な指標を調べることで、[!UICONTROL Auto-Allocate] A/B アクティビティの結果を解釈します。 |
| [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) （AT） | AT アクティビティの[!UICONTROL Summary] レポートに関する情報。 詳細については、[[!UICONTROL Auto-Target Summary] レポート ](/help/main/c-reports/personalization-reports/auto-target-summary-report.md)を参照してください。<br>ATおよびAP アクティビティの2つの[!UICONTROL Personalization Insights] レポートに関する情報：[!UICONTROL Automated Segments] レポートと[!UICONTROL Important Attributes] レポート。 詳しくは、「[パーソナライゼーションインサイトレポート](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md)」を参照してください。 |
| [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md) （AP） | AP アクティビティの2つの[!UICONTROL Automated Personalization Summary] レポートに関する情報：[!UICONTROL Activity Level] レポートと[!UICONTROL Offer Level] レポート。 詳細については、[Automated Personalization概要レポート ](/help/main/c-reports/personalization-reports/reports-ap.md)を参照してください。<br>ATおよびAP アクティビティの2つの[!UICONTROL Personalization Insights] レポートに関する情報：[!UICONTROL Automated Segments] レポートと[!UICONTROL Important Attributes] レポート。 詳しくは、「[パーソナライゼーションインサイトレポート](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md)」を参照してください。 |
| [[!UICONTROL Multivariate Test]](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) （MVT） | MVT アクティビティの2つのレポートに関する情報：[!UICONTROL Experience Performance] レポートと[!UICONTROL Location Contribution] レポート。 詳しくは、[Experience Performance Report](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md) （MVT）および[Location Contribution Report](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) （MVT）を参照してください。 |
| [[!DNL Adobe Analytics] Adobe Target用Reporting Sourceとして](/help/main/c-integrating-target-with-mac/a4t/a4t.md) （A4T） | [!DNL Target] （A4T）のレポートソースとして[!DNL Adobe Analytics]を使用する方法について説明します。 A4T では、[!DNL Target] アクティビティの [!DNL Analytics] レポートにアクセスできます。 詳しくは、「[Analytics for Target（A4T）レポート](/help/main/c-reports/analytics-for-target-a4t-reporting.md)」を参照してください。 |
|  [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) での [[!DNL Target]  レポート | [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/ja/docs/customer-journey-analytics){target=_blank}と[!DNL Target]の間の統合に関する情報で、最適化プログラムに強力な分析ツールと時間節約ツールを提供します。 |

## 指定されたIP アドレスからのレポート データをブロック

指定したIPアドレスからの訪問者をレポートでカウントすることができます。 このオプションは、例えば、内部訪問者からのレポートデータをブロックするのに役立ちます。

[ クライアントケア ](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)に連絡して、IP フィルターを設定してください。 このフィルタリングは、レポートソースとして[Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) （A4T）を使用する場合は適用されません。
