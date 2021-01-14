---
keywords: Target;reports;report settings;multiple metrics;metrics;shown metrics;hidden metrics
description: Adobe Targetを使用したレポートで表示する複数の指標を選択します。
title: Adobe Targetを使用したレポートでの複数の指標の表示
feature: Reports
translation-type: tm+mt
source-git-commit: 7b86db4b45f93a3c6169caf81c2cd52236bb5a45
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 61%

---


# レポートでの複数の指標の表示{#view-multiple-metrics-in-a-report}

[!DNL Adobe Target]レポートで表示する複数の指標を選択できます。

複数の指標をレポートに表示する際は、次の点に注意してください。

* 複数の指標を表示する機能は、[A/Bテスト](/help/c-activities/t-test-ab/test-ab.md)、[自動配分](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)、[自動ターゲット](/help/c-activities/auto-target/auto-target-to-optimize.md)、[エクスペリエンスのターゲット設定](/help/c-activities/t-experience-target/experience-target.md)(XT)アクティビティでのみ使用できます。
* [ターゲット](/help/c-integrating-target-with-mac/a4t/a4t.md)(A4T)用のAnalyticsを使用するアクティビティのレポートには、20を超える指標を追加できません。 A4Tを使用&#x200B;*しない*&#x200B;アクティビティのレポートに、アクティビティ内の指標をいくつでも追加できます。
* 複数の指標を選択した場合は、「[](/help/c-reports/downloading-data-in-csv-file.md)ダウンロード」オプションを使用して CSV 形式でレポートをダウンロードすることはできません。「[!UICONTROL ダウンロード]」オプションを利用するには、指標を 1 つだけ選択する必要があります。
* 2015年7月[!DNL Target]リリース（2015年7月30日）より前に作成されたアクティビティに対しては、複数の指標を表示できません。

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

   「[!UICONTROL 表示されている指標]」リストでは、ドラッグ＆ドロップで指標の順番を自由に並べ替えることができます。選択した順序が[!UICONTROL テーブル表示]と[!UICONTROL グラフ表示]に反映されます。 「[!UICONTROL 表示されている指標]」リストから指標を削除するには、該当の指標にマウスポインターを置いて **X** アイコンをクリックします。

1. 終了したら「**[!UICONTROL 保存]**」をクリックします。
1. （条件付き）[!UICONTROL テーブル表示]でレポートを表示中に、指標の列見出しにマウスポインターを置くと、青い矢印が表示されます。 この矢印をクリックして表を展開すると、対象の指標の「[!UICONTROL 上昇率]」と「[!UICONTROL 信頼性]」が表示されます。

   ![](assets/multiple_metrics_table.png)

   指標と列は、一度に 1 つのみ展開できます。再度矢印をクリックすると、列が折りたたまれます。

1. （条件付き）グラフ表示でレポートを表示中に、ドロップダウンリストから表示する指標を個別に選択できます。

   ![](assets/multiple_metrics_graph.png)

