---
keywords: ターゲット；レポート；レポート設定；複数の指標；指標；表示される指標；非表示の指標
description: Adobe Targetを使用して、レポートで表示する複数の指標を選択する方法について説明します。
title: レポートで複数の指標を表示するにはどうすればよいですか？
feature: Reports
exl-id: 8d8aedd8-4583-4131-8ae0-df14e071940a
TQID: https://experienceleague.adobe.com/mXLlrS1wwfISfxWxq2c-sMDJP1vqxQjbqM-DsLJK9bY
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 397
ht-degree: 12%

---

# レポートでの複数の指標の表示

[!DNL Adobe Target] レポートで表示する複数の指標を選択できます。

複数の指標をレポートに表示する際は、次の点に注意してください。

* 複数の指標を表示する機能は、[A/B テスト ](/help/main/c-activities/t-test-ab/test-ab.md)、[自動割り当て](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)、[自動ターゲット ](/help/main/c-activities/auto-target/auto-target-to-optimize.md)、[ エクスペリエンスのターゲット設定](/help/main/c-activities/t-experience-target/experience-target.md) （XT）アクティビティでのみ使用できます。
* Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) （A4T）に[Analyticsを使用するアクティビティのレポートに20個を超える指標を追加することはできません。 A4Tを使用する&#x200B;*not* アクティビティのレポートに、アクティビティに含まれる指標をいくつでも追加できます。
* 複数の指標を選択している場合、[ ダウンロードオプション ](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md)を使用してレポートをCSVにダウンロードすることはできません。 [!UICONTROL Download] オプションを有効にするには、単一の指標のみを選択する必要があります。
* 2015年7月[!DNL Target] リリース（2015年7月30日）より前に作成されたアクティビティの複数の指標を表示することはできません。

**複数の指標を選択してレポートに表示する方法は次のとおりです。**

1. レポートを表示するには、**[!UICONTROL Activities]**&#x200B;をクリックし、リストから目的のアクティビティをクリックしてから、**[!UICONTROL Reports]** タブをクリックします。
1. **[!UICONTROL Report Metric]** ドロップダウンリストをクリックして、[!UICONTROL Shown Metrics]と[!UICONTROL Hidden Metrics] リストを表示します。

   [!UICONTROL Search] ボックスを使用して、[!UICONTROL Shown Metrics] リストに追加する利用可能な指標をすばやく検索できます。

   レポートの[!UICONTROL Table View]と[!UICONTROL Graph View]の両方のモードから複数の指標を選択できます。

1. [!UICONTROL Hidden Metrics] リストの目的の指標にマウスポインターを合わせ、**[!UICONTROL Select]**&#x200B;をクリックして[!UICONTROL Shown Metrics] リストに移動します。

   または

   目的の指標を[!UICONTROL Hidden Metrics] リストから[!UICONTROL Shown Metrics] リストにドラッグ&amp;ドロップします。

   [!UICONTROL Shown Metrics] リストに少なくとも1つの指標が必要です。

   [!UICONTROL Shown Metrics] リストの目的の順序に指標をドラッグ&amp;ドロップすることで、指標を並べ替えることができます。 選択した順序は[!UICONTROL Table View]と[!UICONTROL Graph View]に反映されます。 [!UICONTROL Shown Metrics] リストから指標を削除するには、指標の上にマウスポインターを置き、**X** アイコンをクリックします。

1. 完了したら、**[!UICONTROL Save]**&#x200B;をクリックします。
1. （条件付き） [!UICONTROL Table View]でレポートを表示する際に、指標の列ヘッダーにマウスポインターを置くと、青い矢印が表示されます。 矢印をクリックしてテーブルを展開し、その指標の[!UICONTROL Lift]と[!UICONTROL Confidence]を表示します。

   指標と列は、一度に 1 つのみ展開できます。 再度矢印をクリックすると、列が折りたたまれます。

1. （条件付き） [!UICONTROL Graph View]でレポートを表示する際に、ドロップダウンリストから表示する個々の指標を選択できます。
