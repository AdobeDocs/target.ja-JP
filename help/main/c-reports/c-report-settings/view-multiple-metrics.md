---
keywords: ターゲット；レポート；レポート設定；複数の指標；指標；表示される指標；非表示の指標
description: Adobe Targetを使用して、レポートで表示する複数の指標を選択する方法を説明します。
title: レポートで複数の指標を表示するにはどうすればよいですか？
feature: Reports
exl-id: 8d8aedd8-4583-4131-8ae0-df14e071940a
source-git-commit: c1a71d1fb6fa9b5c14e22fa3199358a4594bb4a1
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 12%

---

# レポートでの複数の指標の表示

複数の指標を選択して、[!DNL Adobe Target] のレポートに表示できます。

複数の指標をレポートに表示する際は、次の点に注意してください。

* 複数の指標を表示する機能は、[A/B テスト &#x200B;](/help/main/c-activities/t-test-ab/test-ab.md)、[&#x200B; 自動配分 &#x200B;](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)、[&#x200B; 自動ターゲット &#x200B;](/help/main/c-activities/auto-target/auto-target-to-optimize.md) および [&#x200B; エクスペリエンスのターゲット設定 &#x200B;](/help/main/c-activities/t-experience-target/experience-target.md) （XT）アクティビティでのみ使用できます。
* [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) （A4T）を使用するアクティビティのレポートに追加できる指標は 20 個までです。 A4T を使用しない *使用しない* アクティビティのレポートには、アクティビティに含める指標の数だけレポートを追加できます。
* 複数の指標を選択した場合、[&#x200B; ダウンロードオプション &#x200B;](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md) を使用してレポートを CSV にダウンロードすることはできません。 [!UICONTROL Download] オプションを有効にするには、1 つの指標のみを選択する必要があります。
* 2015 年 7 月リリース（2015 年 7 月 30 日（PT））より前に作成されたアクティビティでは、複数の指標を [!DNL Target] 示することはできません。

**複数の指標を選択してレポートに表示する方法は次のとおりです。**

1. レポートを表示するには、「**[!UICONTROL Activities]**」をクリックし、リストから目的のアクティビティをクリックして、「**[!UICONTROL Reports]**」タブをクリックします。
1. 「**[!UICONTROL Report Metric]**」ドロップダウンリストをクリックして、「[!UICONTROL Shown Metrics]」リストと「[!UICONTROL Hidden Metrics]」リストを表示します。

   [!UICONTROL Search] ボックスを使用すると、[!UICONTROL Shown Metrics] リストに追加できる指標をすばやく見つけることができます。

   レポートの [!UICONTROL Table View] モードと [!UICONTROL Graph View] モードの両方から複数の指標を選択できます。

1. [!UICONTROL Hidden Metrics] リスト内の目的の指標にマウスポインターを置いてから、「**[!UICONTROL Select]**」をクリックして [!UICONTROL Shown Metrics] リストに移動します。

   または

   [!UICONTROL Hidden Metrics] リストから [!UICONTROL Shown Metrics] リストに目的の指標をドラッグ&amp;ドロップします。

   [!UICONTROL Shown Metrics] リストには少なくとも 1 つの指標が必要です。

   指標を並べ替えるには、指標リスト内の目的の順序にドラッグ&amp;ドロップ [!UICONTROL Shown Metrics] ます。 選択した順序は、[!UICONTROL Table View] と [!UICONTROL Graph View] に反映されます。 指標リストから指標を削除するには、[!UICONTROL Shown Metrics] 標の上にマウスポインターを置き、「**X**」アイコンをクリックします。

1. 終了したら「**[!UICONTROL Save]**」をクリックします。
1. （条件付き） [!UICONTROL Table View] でレポートを表示している間、任意の指標の列見出しにマウスポインターを置くと、青い矢印が表示されます。 矢印をクリックしてテーブルを展開し、その指標の [!UICONTROL Lift] と [!UICONTROL Confidence] を表示します。

   指標と列は、一度に 1 つのみ展開できます。再度矢印をクリックすると、列が折りたたまれます。

1. （条件付き） [!UICONTROL Graph View] でレポートを表示している際に、ドロップダウンリストから表示する個々の指標を選択できます。
