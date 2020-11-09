---
keywords: Target;reports;report settings;multiple metrics;metrics;shown metrics;hidden metrics
description: Adobe Targetを使用したレポートで表示する複数の指標を選択します。
title: Adobe Targetを使用したレポートでの複数の指標の表示
feature: report settings
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 61%

---


# レポートでの複数の指標の表示{#view-multiple-metrics-in-a-report}

レポート内で表示する複数の指標を選択でき [!DNL Adobe Target] ます。

複数の指標をレポートに表示する際は、次の点に注意してください。

* The ability to view multiple metrics is available for [A/B Test](/help/c-activities/t-test-ab/test-ab.md), [Auto-Allocate](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [Auto-Target](/help/c-activities/auto-target/auto-target-to-optimize.md), and [Experience Targeting](/help/c-activities/t-experience-target/experience-target.md) (XT) activities only.
* You cannot add more than 20 metrics to a report for an activity that uses [Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T). You can add as many metrics as you have in your activity to reports for activities that do *not* use A4T.
* 複数の指標を選択した場合は、「[](/help/c-reports/downloading-data-in-csv-file.md)ダウンロード」オプションを使用して CSV 形式でレポートをダウンロードすることはできません。「[!UICONTROL ダウンロード]」オプションを利用するには、指標を 1 つだけ選択する必要があります。
* You cannot view multiple metrics for activities created before the July 2015 [!DNL Target] release (July 30, 2015).

**複数の指標を選択してレポートに表示する方法は次のとおりです。**

1. レポートをを表示するには、「**[!UICONTROL アクティビティ]**」をクリックし、リストから目的のアクティビティをクリックして、「**[!UICONTROL レポート]**」タブをクリックします。
1. **[!UICONTROL レポート指標]**&#x200B;ドロップダウンリストをクリックし、「[!UICONTROL 表示されている指標]」と「[!UICONTROL 非表示の指標]」リストを表示します。

   ![](assets/multiple_metrics.png)

   [!UICONTROL 検索]ボックスを使用すると、利用できる指標をすばやく検索し、「[!UICONTROL 表示されている指標]」リストに追加できます。

   レポートの[!UICONTROL テーブル表示]と[!UICONTROL グラフ表示]モードの両方で複数の指標を選択できます。

1. 「[!UICONTROL 非表示の指標]」リストの目的の指標にマウスポインターを置いて「**[!UICONTROL 選択]**」をクリックすると、「[!UICONTROL 表示されている指標]」リストに移動できます。

   または

   「[!UICONTROL 非表示の指標]」リストの目的の指標を「[!UICONTROL 表示されている指標]」リストにドラッグ＆ドロップします。

   「[!UICONTROL 表示されている指標]」リストには、1 つ以上の指標を選択する必要があります。

   「[!UICONTROL 表示されている指標]」リストでは、ドラッグ＆ドロップで指標の順番を自由に並べ替えることができます。The selected order will be reflected in the [!UICONTROL Table View] and [!UICONTROL Graph View]. 「[!UICONTROL 表示されている指標]」リストから指標を削除するには、該当の指標にマウスポインターを置いて **X** アイコンをクリックします。

1. 終了したら「**[!UICONTROL 保存]**」をクリックします。
1. (Conditional) While viewing the report in the [!UICONTROL Table View], hover your mouse pointer on any metric&#39;s column header to display a blue arrow. この矢印をクリックして表を展開すると、対象の指標の「[!UICONTROL 上昇率]」と「[!UICONTROL 信頼性]」が表示されます。

   ![](assets/multiple_metrics_table.png)

   指標と列は、一度に 1 つのみ展開できます。再度矢印をクリックすると、列が折りたたまれます。

1. （条件付き）グラフ表示でレポートを表示中に、ドロップダウンリストから表示する指標を個別に選択できます。

   ![](assets/multiple_metrics_graph.png)

