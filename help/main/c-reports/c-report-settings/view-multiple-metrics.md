---
keywords: Target、レポート、レポート設定、複数の指標、指標、表示される指標、非表示の指標
description: Adobe Targetを使用して、1 つのレポートに表示する複数の指標を選択する方法を説明します。
title: レポートに複数の指標を表示する方法を教えてください。
feature: Reports
exl-id: 8d8aedd8-4583-4131-8ae0-df14e071940a
source-git-commit: d90e541588f51e16dd9b11ead1ece77e9ca1408b
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 59%

---

# レポートでの複数の指標の表示

複数の指標を選択して、 [!DNL Adobe Target] レポート。

複数の指標をレポートに表示する際は、次の点に注意してください。

* 複数の指標を表示する機能は、 [A/B テスト](/help/main/c-activities/t-test-ab/test-ab.md), [自動配分](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md)、および [エクスペリエンスのターゲット設定](/help/main/c-activities/t-experience-target/experience-target.md) (XT) アクティビティのみ。
* を使用するアクティビティのレポートに 20 個を超える指標を追加することはできません [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)。 アクティビティのレポートには、アクティビティ内の指標をいくつでも追加できます *not* A4T を使用します。
* 複数の指標を選択した場合は、「[](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md)ダウンロード」オプションを使用して CSV 形式でレポートをダウンロードすることはできません。「[!UICONTROL ダウンロード]」オプションを利用するには、指標を 1 つだけ選択する必要があります。
* 2015 年 7 月より前に作成されたアクティビティに対して、複数の指標を表示することはできません [!DNL Target] リリース（2015 年 7 月 31 日）。

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

   「[!UICONTROL 表示されている指標]」リストでは、ドラッグ＆ドロップで指標の順番を自由に並べ替えることができます。選択した順序は、 [!UICONTROL テーブル表示] および [!UICONTROL グラフ表示]. 「[!UICONTROL 表示されている指標]」リストから指標を削除するには、該当の指標にマウスポインターを置いて **X** アイコンをクリックします。

1. 終了したら「**[!UICONTROL 保存]**」をクリックします。
1. （条件付き） [!UICONTROL テーブル表示]をクリックし、指標の列見出しにマウスポインターを置くと、青い矢印が表示されます。 この矢印をクリックして表を展開すると、対象の指標の「[!UICONTROL 上昇率]」と「[!UICONTROL 信頼性]」が表示されます。

   ![](assets/multiple_metrics_table.png)

   指標と列は、一度に 1 つのみ展開できます。再度矢印をクリックすると、列が折りたたまれます。

1. （条件付き）レポートのグラフ表示時に、ドロップダウンリストから表示する指標を個別に選択できます。

   ![](assets/multiple_metrics_graph.png)
