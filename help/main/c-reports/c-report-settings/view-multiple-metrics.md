---
keywords: ターゲット；レポート；レポート設定；複数の指標；指標；表示される指標；非表示の指標
description: Adobe Targetを使用して、レポートで表示する複数の指標を選択する方法について説明します。
title: レポートで複数の指標を表示するにはどうすればよいですか？
feature: Reports
exl-id: 8d8aedd8-4583-4131-8ae0-df14e071940a
TQID: https://experienceleague.adobe.com/mXLlrS1wwfISfxWxq2c-sMDJP1vqxQjbqM-DsLJK9bY
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 439
ht-degree: 55%

---

# レポートでの複数の指標の表示

[!DNL Adobe Target] レポートで表示する複数の指標を選択できます。

複数の指標をレポートに表示する際は、次の点に注意してください。

* 複数の指標を表示する機能は、[A/B テスト &#x200B;](/help/main/c-activities/t-test-ab/test-ab.md)、[自動割り当て](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)、[自動ターゲット &#x200B;](/help/main/c-activities/auto-target/auto-target-to-optimize.md)、[&#x200B; エクスペリエンスのターゲット設定](/help/main/c-activities/t-experience-target/experience-target.md) （XT）アクティビティでのみ使用できます。
* Target[&#128279;](/help/main/c-integrating-target-with-mac/a4t/a4t.md) （A4T）にAnalyticsを使用するアクティビティのレポートに20個を超える指標を追加することはできません。 A4Tを使用する&#x200B;*not* アクティビティのレポートに、アクティビティに含まれる指標をいくつでも追加できます。
* 複数の指標を選択している場合、[&#x200B; ダウンロードオプション &#x200B;](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md)を使用してレポートをCSVにダウンロードすることはできません。 「[!UICONTROL ダウンロード]」オプションを利用するには、指標を 1 つだけ選択する必要があります。
* 2015年7月[!DNL Target] リリース（2015年7月30日）より前に作成されたアクティビティの複数の指標を表示することはできません。

**複数の指標を選択してレポートに表示する方法は次のとおりです。**

1. レポートを表示するには、「**[!UICONTROL アクティビティ]**」をクリックし、リストから目的のアクティビティをクリックして、「**[!UICONTROL レポート]**」タブをクリックします。
1. **[!UICONTROL レポート指標]**&#x200B;ドロップダウンリストをクリックし、「[!UICONTROL 表示されている指標]」と「[!UICONTROL 非表示の指標]」リストを表示します。

   [!UICONTROL 検索]ボックスを使用すると、利用できる指標をすばやく検索し、「[!UICONTROL 表示されている指標]」リストに追加できます。

   レポートの[!UICONTROL テーブル表示]と[!UICONTROL グラフ表示]モードの両方で複数の指標を選択できます。

1. 「[!UICONTROL 非表示の指標]」リストの目的の指標にカーソルを合わせて「**[!UICONTROL 選択]**」をクリックすると、「[!UICONTROL 表示されている指標]」リストに移動できます。

   または

   「[!UICONTROL 非表示の指標]」リストの目的の指標を「[!UICONTROL 表示されている指標]」リストにドラッグ＆ドロップします。

   「[!UICONTROL 表示されている指標]」リストには、1 つ以上の指標を選択する必要があります。

   「[!UICONTROL 表示されている指標]」リストでは、ドラッグ＆ドロップで指標の順番を自由に並べ替えることができます。 選択した順序は、[!UICONTROL &#x200B; テーブル ビュー]および[!UICONTROL &#x200B; グラフ ビュー]に反映されます。 「[!UICONTROL 表示されている指標]」リストから指標を削除するには、該当の指標にカーソルを合わせて **X** アイコンをクリックします。

1. 終了したら「**[!UICONTROL 保存]**」をクリックします。
1. （条件付き） [!UICONTROL &#x200B; テーブル表示]でレポートを表示する際に、指標の列ヘッダーにマウスポインターを置くと、青い矢印が表示されます。 この矢印をクリックして表を展開すると、対象の指標の「[!UICONTROL 上昇率]」と「[!UICONTROL 信頼性]」が表示されます。

   指標と列は、一度に 1 つのみ展開できます。 再度矢印をクリックすると、列が折りたたまれます。

1. （条件付き） [!UICONTROL &#x200B; グラフ ビュー]でレポートを表示する際に、ドロップダウンリストから表示する個々の指標を選択できます。
