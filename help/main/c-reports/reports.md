---
keywords: レポート；ブロック ip アドレス；ブロック訪問者のip アドレス；レポートのダウンロード；csv；レポート
description: ' [!DNL Adobe Target]のレポート機能を使いこなしてアクティビティを最適化し、意思決定を強化してROIを向上させます。'
title: レポートを表示するにはどうすればよいですか？
feature: Reports
exl-id: c5710eb3-0c72-47f8-870d-df50453ecf08
TQID: https://experienceleague.adobe.com/aRp-t-Z-Hfu5O01RqfxnKyHHL2suM2ahkteDQJShGQI
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 947
ht-degree: 25%

---

# レポート

レポートでは、データに基づいた意思決定に役立つ、[!DNL Adobe Target] アクティビティの進捗状況と結果に関する情報が提供されます。 レポートデータは、アクティビティを終了するタイミングを決定し、勝者となるエクスペリエンスやオファーを示し、次のアクションを決定するために必要なインサイトや学びを提供するのに役立ちます。

## レポートの表示 {#section_C4591A32F6D04C95A1AD5A377C27C28B}

1. 「**[!UICONTROL アクティビティ]**」をクリックしてから、希望するアクティビティをリストからクリックします。

   アクティビティが多い場合は、フィルターアイコン（![&#x200B; フィルターアイコン &#x200B;](/help/main/assets/icons/Filter.svg)）をクリックして、[!UICONTROL Type]、[!UICONTROL Status]、[!UICONTROL Reporting Source]、[!UICONTROL Experience Composer]、[!UICONTROL Metrics Type]、[!UICONTROL Decisioning Method]、および[!UICONTROL Activity Source] リストからオプションを選択して、リストをフィルタリングできます。

   例えば、[!UICONTROL &#x200B; タイプ &#x200B;] ドロップダウンリストから[!UICONTROL A/B テスト &#x200B;]と[!UICONTROL &#x200B; エクスペリエンスターゲティング &#x200B;]を選択し、[!UICONTROL &#x200B; ステータス &#x200B;] ドロップダウンリストから[!UICONTROL &#x200B; ライブ &#x200B;]を選択して、アクティブな状態にある[!UICONTROL A/B テスト &#x200B;]と[!UICONTROL &#x200B; エクスペリエンスターゲティング &#x200B;] アクティビティのみを表示できます。

   次の図は、2つのタイプが選択された[!UICONTROL Type] ドロップダウンリストを示しています：[!UICONTROL A/B テスト &#x200B;]と[!UICONTROL &#x200B; エクスペリエンスのターゲット設定]。 A/B テストの 3 つのタイプ（手動、[自動配分](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)、[自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md)）がデフォルトで選択されていることに注意してください。 必要に応じて、1 つ以上のタイプの選択を解除できます。

   ![タイプによるレポートのフィルタリング](/help/main/c-reports/assets/report-filters-refresh.png)

1. リストから目的のアクティビティをクリックして、[!UICONTROL 概要] ページを表示します。

1. 左側のパネルの「**[!UICONTROL レポート]**」タブをクリックします。

   ![A/B レポート &#x200B;](/help/main/c-reports/assets/reports-refresh.png)

   各レポートには、レポートを理解しやすくするための凡例が含まれます。

   この凡例には、以下の情報が表示されます。

   * アクティビティが実行された日付範囲を含むアクティビティステータス
   * [予測される勝者エクスペリエンス &#x200B;](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) （使用可能な場合）。

   >[!NOTE]
   >
   >エクスペリエンスの結果は、少なくとも 1 人の参加者がエクスペリエンスを閲覧した後に表示されます。

1. （オプション） [&#x200B; レポート設定アイコン（![&#x200B; レポート設定アイコン &#x200B;](/help/main/assets/icons/Setting.svg)）をクリックして、レポート &#x200B;](/help/main/c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA)を設定します。
1. （オプション）レポートのダウンロードアイコン（![&#x200B; レポートのダウンロードアイコン &#x200B;](/help/main/assets/icons/Download.svg)）をクリックして、[Excelやその他のツールでの分析のためにCSV形式](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md)でレポートをダウンロードします。

   以下のオプションがあります。

   * [!UICONTROL レポートを CSV に書き出す]
   * [!UICONTROL 注文の詳細を CSV に書き出す]

1. （オプション）レポート形式を切り替えるには、**[!UICONTROL テーブルビュー]** （![&#x200B; テーブルビューアイコン &#x200B;](/help/main/assets/icons/Table.svg)）および&#x200B;**[!UICONTROL グラフビュー]** （![&#x200B; グラフビューアイコン &#x200B;](/help/main/assets/icons/GraphTrend.svg)）アイコンをクリックします。

   選択したレポートのタイプによっては、他のビューやレポートが使用できる場合があります。

   | レポートタイプ | 表示 |
   | --- | --- |
   | [[!UICONTROL 自動ターゲット]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | **[!UICONTROL 自動セグメント]** （![自動セグメントレポート &#x200B;](/help/main/assets/icons/AutomatedSegment.svg)）または&#x200B;**[!UICONTROL 重要な属性]** （![重要な属性アイコン &#x200B;](/help/main/assets/icons/ViewList.svg)）アイコンをクリックします。<ul><li>[[!UICONTROL 自動セグメント &#x200B;] レポート &#x200B;](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md)は、[!UICONTROL Automated Personalization]または[!UICONTROL 自動ターゲット &#x200B;] アクティビティでのオファーや体験に対して、様々な訪問者がどのように異なる反応を示すかを示しています。 このレポートでは、[!DNL Target]個のパーソナライゼーションモデルによって定義されたさまざまな自動セグメントが、アクティビティのオファーとエクスペリエンスにどのように反応したかを示します。</li><li>[[!UICONTROL 重要な属性] レポート &#x200B;](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md)は、異なるアクティビティにおいて、モデルがパーソナライズを決定する際に、異なる属性が多かれ少なかれ重要であることを示しています。 このレポートは、モデルに影響を及ぼした上位の属性とそれら属性の相対的重要性を示します。</li></ul> |
   | [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md)（AP） | [[!UICONTROL Automated Personalizationの概要] レポート &#x200B;](/help/main/c-reports/personalization-reports/reports-ap.md)に加えて、**[!UICONTROL 自動セグメント]** （![自動セグメントレポート &#x200B;](/help/main/assets/icons/AutomatedSegment.svg)）または&#x200B;**[!UICONTROL 重要な属性]** （![重要な属性アイコン &#x200B;](/help/main/assets/icons/ViewList.svg)）アイコンをクリックできます。<ul><li>[[!UICONTROL 自動セグメント &#x200B;] レポート &#x200B;](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md)は、[!UICONTROL Automated Personalization]または[!UICONTROL 自動ターゲット &#x200B;] アクティビティでのオファーや体験に対して、様々な訪問者がどのように異なる反応を示すかを示しています。 このレポートでは、[!DNL Target]個のパーソナライゼーションモデルによって定義されたさまざまな自動セグメントが、アクティビティのオファーとエクスペリエンスにどのように反応したかを示します。</li><li>[[!UICONTROL 重要な属性] レポート &#x200B;](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md)は、異なるアクティビティにおいて、モデルがパーソナライズを決定する際に、異なる属性が多かれ少なかれ重要であることを示しています。 このレポートは、モデルに影響を及ぼした上位の属性とそれら属性の相対的重要性を示します。</li></ul> |
   | [[!UICONTROL 多変量分析テスト]](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) （MVT） | [[!UICONTROL Experience Performance] レポート &#x200B;](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md)に加えて、[[!UICONTROL 場所の貢献度]](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) （![場所の貢献度アイコン &#x200B;](/help/main/assets/icons/LocationContribution.svg)）アイコンをクリックすると、レポートを切り替えて、場所ごとの貢献度を表示できます。 |

## 特定のアクティビティタイプに関する追加レポート情報 {#section_DFE037B9E1C345D3B3BDFCB3AC0359CA}

このトピックおよびそのサブトピックに記載されている一般的なレポート情報に加え、個々のアクティビティタイプに固有の追加情報が本ガイドの他の節に記載されています。

| アクティビティのタイプ | 詳細 |
|--- |--- |
| [[!UICONTROL A/B テスト]](/help/main/c-activities/t-test-ab/test-ab.md) | [!DNL Target] で使用している上昇率、信頼性、統計的アプローチを理解するには、「[A/Bテストのプラン](/help/main/c-activities/t-test-ab/sample-size-determination.md)」を参照してください。 |
| [[!UICONTROL 自動割り当て] レポートを解釈](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) | [!DNL Target] UIで上昇率と信頼性を含む重要な指標を調べることで、[!UICONTROL 自動配分]A/B アクティビティの結果を解釈します。 |
| [[!UICONTROL 自動ターゲット &#x200B;]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) （AT） | AT アクティビティの[!UICONTROL 概要] レポートに関する情報。 詳細については、[[!UICONTROL 自動ターゲットサマリー] レポート &#x200B;](/help/main/c-reports/personalization-reports/auto-target-summary-report.md)を参照してください。<br>ATおよびAP アクティビティに関する2つの[!UICONTROL Personalization インサイト &#x200B;] レポートについて：[!UICONTROL 自動セグメント &#x200B;] レポートと[!UICONTROL 重要な属性] レポート。 詳しくは、「[パーソナライゼーションインサイトレポート](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md)」を参照してください。 |
| [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md)（AP） | AP アクティビティに関する2つの[!UICONTROL Automated Personalization概要] レポートに関する情報：[!UICONTROL &#x200B; アクティビティレベル &#x200B;] レポートと[!UICONTROL &#x200B; オファーレベル &#x200B;] レポート。 詳細については、[Automated Personalizationの概要レポート &#x200B;](/help/main/c-reports/personalization-reports/reports-ap.md)を参照してください。<br>ATおよびAP アクティビティに関する2つの[!UICONTROL Personalization インサイト &#x200B;] レポートに関する情報：[!UICONTROL 自動セグメント &#x200B;] レポートと[!UICONTROL 重要な属性] レポート。 詳しくは、「[パーソナライゼーションインサイトレポート](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md)」を参照してください。 |
| [[!UICONTROL 多変量分析テスト]](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) （MVT） | MVT アクティビティの2つのレポートに関する情報：[!UICONTROL Experience Performance] レポートと[!UICONTROL Location Contribution] レポート。 詳しくは、[Experience Performance Report](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md) （MVT）および[Location Contribution Report](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) （MVT）を参照してください。 |
| [[!DNL Adobe Analytics] Adobe Target用Reporting Sourceとして](/help/main/c-integrating-target-with-mac/a4t/a4t.md) （A4T） | [!DNL Target] （A4T）のレポートソースとして[!DNL Adobe Analytics]を使用する方法について説明します。 A4T では、[!DNL Target] アクティビティの [!DNL Analytics] レポートにアクセスできます。 詳しくは、「[Analytics for Target（A4T）レポート](/help/main/c-reports/analytics-for-target-a4t-reporting.md)」を参照してください。 |
|  [!DNL Adobe Customer Journey Analytics][&#128279;](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) での [!DNL Target]  レポート | [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/ja/docs/customer-journey-analytics){target=_blank}と[!DNL Target]の間の統合に関する情報で、最適化プログラムに強力な分析ツールと時間節約ツールを提供します。 |

## 指定されたIP アドレスからのレポート データをブロック

指定したIPアドレスからの訪問者をレポートでカウントすることができます。 このオプションは、例えば、内部訪問者からのレポートデータをブロックするのに役立ちます。

[&#x200B; クライアントケア &#x200B;](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)に連絡して、IP フィルターを設定してください。 このフィルタリングは、レポートソースとして[Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) （A4T）を使用する場合は適用されません。
