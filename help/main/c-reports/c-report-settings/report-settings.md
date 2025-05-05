---
keywords: Target、レポート、レポート設定、プリセット、ターゲットプリセット、metric、オーディエンス、日付範囲、設定、ダウンロード、table view、グラフビュー、平均上昇率、上昇率、上昇率バインド、頼区間、confidence、場所の貢献度、running Average、カウント手法
description: 指標、オーディエンス、日付範囲など、Adobe Targetでレポートを設定する方法について説明します。
title: レポートの設定方法
feature: Reports
exl-id: 337579d1-c678-43b6-9e80-b5abe159c2d3
source-git-commit: c1a71d1fb6fa9b5c14e22fa3199358a4594bb4a1
workflow-type: tm+mt
source-wordcount: '1778'
ht-degree: 48%

---

# レポート設定

[!DNL Adobe Target] のレポートに表示する要素の設定に役立つ情報です。 レポート設定は保存して後で使用できます。

レポートを表示するには、次の手順を実行します。

1. をクリック **[!UICONTROL Activities]** し、リストから目的のアクティビティをクリックします。
1. 「**[!UICONTROL Reports]**」タブをクリックします。

   ![レポート UI](/help/main/c-reports/c-report-settings/assets/report-ui-refresh.png)

## Target プリセット {#section_51F67341465045BEB4F1A2FB638A8EB1}

指標、日付範囲、オーディエンス、詳細設定などを必要に応じて設定した、個々のアクティビティのレポートのプリセットを最大 10 個保存できます。すべての [!DNL Target] ユーザーは、作成したユーザーに関係なく、様々なプリセットの表示、編集、削除を行うことができます。

また、個々のアクティビティのレポートを必要に応じて設定したあと、その設定をデフォルトまたはお気に入りのプリセットとして保存することもできます。これは、そのアクティビティの進行中のレポートを確認するたびに表示されるビューです。

### プリセットまたはデフォルトプリセットの作成

1. アクティビティのレポートを必要に応じて設定します。

   指標、日付範囲、オーディエンス、詳細設定などの使用可能な設定については、以下で説明します。

1. **[!UICONTROL Target Preset]** の横にある **[!UICONTROL More Options]** （![ その他のオプション アイコン ](/help/main/assets/icons/MoreSmallListVert.svg)） アイコン/**[!UICONTROL Save as New]** をクリックします。

   [!UICONTROL Create Preset] ダイアログボックスが表示されます。

   ![新しいプリセットダイアログボックス](/help/main/c-reports/c-report-settings/assets/report_preset_dialog-new.png)

1. **[!UICONTROL Filters]** の節の情報を確認してレポートが必要に応じて設定されていることを確認し、**[!UICONTROL Preset Name]** （最大 50 文字）を指定します。
1. （条件付き）これをデフォルトまたはお気に入りのレポートビューにする場合は、「**[!UICONTROL Set as default preset]**」切り替えスイッチを「オン」の位置にスライドします。
1. **[!UICONTROL Create]** をクリックします。

### 別のプリセットを選択

**[!UICONTROL Target Preset]** ドロップダウンリストから目的のプリセットを選択します。

### プリセットの編集

1. 編集するプリセットを選択します。
1. レポートの設定を必要に応じて編集します（指標、日付範囲、オーディエンス、詳細設定など）。

   レポートの設定を編集した後に [!UICONTROL Save] をクリックすると、プリセット名の後にアスタリスク（&#42;）が表示され、プリセットが変更されたことを示します。

1. **[!UICONTROL More Options]** （その他のオプションアイコン ![ アイコン ](/help/main/assets/icons/MoreSmallListVert.svg)）アイコン/**[!UICONTROL Save as New]** をクリックして、新しいプリセットを作成します。

### プリセットの削除

1. 削除するプリセットを選択します。
1. **[!UICONTROL More Options]** （その他のオプションアイコン ![）アイコン ](/help/main/assets/icons/MoreSmallListVert.svg)**[!UICONTROL Delete]** をクリックします。

1. もう一度「**[!UICONTROL Delete]**」をクリックして、削除を確認します（削除されたプリセットは復元できません）。

### プリセットのエラー処理

プリセットが無効になった場合は、レポート内のアラートやメッセージでそれが通知されます。アラートまたはメッセージでは、別のオーディエンス、指標、ホストグループ、またはエクスペリエンスを選択して有効なプリセットを作成するようにユーザーに指示します。

プリセットが無効になる可能性がある状況をいくつか以下に示します。

* レポート用オーディエンスがアクティビティから削除されましたが、プリセット定義で参照されています。
* 1 つ（または複数）の指標が削除されましたが、プリセット定義で参照されています。例えば、1 つ以上の指標をアクティビティから削除した後、新しい指標を追加するような場合です。
* 1 つ（または複数）のホストグループ（環境）が存在しませんが、プリセット定義で参照されています。
* 1 つ（または複数）のエクスペリエンスがプリセットの作成後に削除されましたが、プリセット定義で参照されています。
* 参照先のエンティティがまだ存在しているにもかかわらず更新され、プリセット定義が意味的に変わったので、プリセットが意味的に無効になります。例えば、最初「Revenue on Chrome」という名前のプリセットを作成したとしましょう。その後、売上高ではなくコンバージョン指標を測定するようにアクティビティを更新します。アクティビティ定義を更新すると、プリセット定義が意味的に無効になります。

## [!UICONTROL Report Metric] {#section_894ABD7148244806B7CE556EBBA2AD62}

**[!UICONTROL Report Metric]** ドロップダウンリストをクリックして、グラフおよびグラフに表示する別の [ 成功指標 ](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) または複数の指標を選択します。

デフォルトでは、アクティビティの作成時に、成功指標の設定で主要指標が決定されています。その設定を変更し、アクティビティを再保存すると、レポートの主要指標が更新されます。

レポートに表示する複数の指標の選択について詳しくは、「[ レポートで複数の指標を表示 ](/help/main/c-reports/c-report-settings/view-multiple-metrics.md#concept_9E3C3F6F3EC1412FAF252975AC0720B7)」を参照してください。

## [!UICONTROL Audience] {#section_70926EB4618945D9AFF2B0564FF3717B}

「**[!UICONTROL Audience]**」ドロップダウンリストをクリックして、レポートに表示するオーディエンスを変更します。

詳しくは、[オーディエンス](/help/main/c-target/target.md#concept_A782F8481A5041EBA75103CB26376522)を参照してください。

## [!UICONTROL Preset Date Range]

**[!UICONTROL Preset Date Range]** ドロップダウンリストをクリックして、プリセットされた日付範囲から選択します。

レポートの新しい **[!UICONTROL Start]** と **[!UICONTROL End]** の日付を選択します。 **[!UICONTROL Start of Activity]** および **[!UICONTROL Start of activity - End of Activity]** の範囲を使用することもできます。

定義済みの日付範囲には、過去 7 日間、過去 15 日間または過去 30 日間が含まれます。 この事前定義された日付範囲は、繰り出し範囲です。開始日が選択した日数に満たない場合、カレンダーには開始日からの範囲が表示されますが、開始日が、アクティビティ期間の増加に応じて選択された日数より古くなった場合にロールオンされます。

レポートの日付には以下の制限事項があります。

* レポートの開始日は、直近の 2 年以内でなければなりません。
* オファーグループのレポートは、今日から 99 日以内に制限されています。
* 毎時間のレポートは 15 日までに制限されています。

## 日付範囲 {#section_A410A768403C4E01891F95CB357E63ED}

[!UICONTROL Date Range] のボックスには、レポートの現在の日付範囲が表示されます。 **[!UICONTROL Calendar]** （![ カレンダーアイコン ](/help/main/assets/icons/Calendar.svg)）アイコンをクリックしてカレンダーを表示し、レポートの日付範囲を変更できます。

## 設定 {#section_D99CE462107D45CABE0960F820E1E972}

レポートを設定するには：

1. **[!UICONTROL Report Settings]** （![ レポート設定アイコン ](/help/main/assets/icons/Setting.svg)）アイコンをクリックし、（以下で説明されているように）必要な変更を行います。
1. 終了したら「**[!UICONTROL Save]**」をクリックします。

選択したアクティビティのタイプによって、オプションは変わります。

### カウント手法

目的の方法を選択します。

* 訪問者数
* 訪問
* アクティビティのインプレッション

### コントロール

上昇率を計算および比較する際に使用するコントロールエクスペリエンスを選択します。

### 環境 {#environment}

レポートに使用する環境（ホストグループ）を選択します。 詳しくは、[ホスト](/help/main/administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E)を参照してください。

>[!NOTE]
>
>組織が [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html){target=_blank} （AEP）を使用して指標データを [!DNL Target] に送信する場合、AEP データストリームの環境は、[!DNL Target] レポート設定の環境と一致する必要があります。

### レポートデータをリセット

「[!UICONTROL Reset Report Data]」をクリックします。 古いデータを削除するには、レポートデータをリセットします。 現在の訪問者はアクティビティに残ります。  このオプションは、[!UICONTROL Approver] 権限を持つユーザーのみが使用できます。

>[!IMPORTANT]
>
>これは恒久的なアクションであり、取り消すことができません。

極端な値の除外

[!UICONTROL Exclude Extreme Values] の切り替えは、売上高とエンゲージメントの指標タイプを持つアクティビティにのみ適用されます。 詳しくは、「[極端な注文の除外](/help/main/c-reports/c-report-settings/excluding-extreme-orders.md#task_2AE7743FFCDD466DAEEB720BE5F33DAA)」を参照してください。

## ダウンロード {#section_77E65C50BAAF4AB79242DB3A8778ADEF}

レポート データを [!DNL .csv] 形式でダウンロードして、Excel、Access![&#128279;](/help/main/assets/icons/Download.svg) またはその他のデータ分析プログラムにすばやくインポートするには、**[!UICONTROL Download]** ール （ ダウンロード アイコン） アイコンをクリックします。

詳しくは、「[CSV ファイルでのデータのダウンロード](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md)」を参照してください。

## 更新 {#section_E203729F2F314DF3856D2EE67C60B370}

ページ全体 ![&#128279;](/help/main/assets/icons/Refresh.svg) その設定または日付範囲を更新せずに、レポートのテーブルおよびグラフ表示を更新するには、**[!UICONTROL Refresh]** 新アイコン  更新アイコン）をクリックします。

## その他のオプション {#section_AB1B5C695D7045A0A0AC0E2698D2E7DE}

「**[!UICONTROL More Options]**」アイコン（その他のオプションアイコン ![ をクリックして ](/help/main/assets/icons/MoreSmallListVert.svg) 「[!UICONTROL Save as New]」および「[!UICONTROL Delete]」オプションにアクセスします。

## オプションを表示

レポートは、アクティビティタイプに応じて様々な形式で表示できます。 目的のオプションを選択します。

* **テーブル表示**:**[!UICONTROL Table View]** （![ テーブル表示アイコン ](/help/main/assets/icons/Table.svg)）アイコンをクリックして、レポートをテーブルとして表示します。
* **グラフ表示**:**[!UICONTROL Graph View]** （![ グラフ表示アイコン ](/help/main/assets/icons/GraphTrend.svg)）アイコンをクリックして、レポートをグラフとして表示します。
* **自動セグメント**:（[!UICONTROL Automated Personalization] （AP）および [!UICONTROL Auto-Target] （AT）アクティビティでのみ使用可能） **[!UICONTROL Automated Segments] （![ 自動セグメントアイコン ](/help/main/assets/icons/AutomatedSegment.svg)）アイコンをクリックして、[ 自動セグメントレポート ](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md) を表示します。
* **重要な属性**: （[!DNL Automated Personalization] （AP）および [!UICONTROL Auto-Target] （AT）アクティビティでのみ使用可能） **[!UICONTROL Important Attributes]** （重要な属性アイコン ![ アイコンをクリックして ](/help/main/assets/icons/ViewList.svg) [ 重要な属性レポート ](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) を表示します。

## 平均上昇率、上昇率範囲および信頼区間 {#section_0D87615B1D3344B3858BA494EEBC16FB}

レポートには様々なデータポイントと視覚表現があり、アクティビティの上昇率範囲や信頼区間を把握する一助になります。こうした情報を参考にすれば、より的確に勝者を見極めることができます。

詳しくは、[A/Bn テストでの統計計算 ](/help/main/c-reports/statistical-methodology/statistical-calculations.md) を参照してください。

次の点に留意してください。

* [!UICONTROL Table View] でレポートを表示する場合にのみ使用できます。
* この機能は、Analytics をレポートソースに使用する（A4T）[アクティビティでは利用できません。](/help/main/c-integrating-target-with-mac/a4t/a4t.md)。

## 場所の貢献度 {#section_5832F126AC114AE1ABFFF4D9B904393B}

[[!UICONTROL Location Contribution]](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) （場所の投稿アイコン ![ アイコンをクリックして ](/help/main/assets/icons/LocationContribution.svg) レポートを切り替え、多変量分析テスト（MVT）アクティビティの場所による投稿を表示します。

## エクスペリエンス {#section_3A450DE1FA7E43F0AAB73165EC3D1C34}

[!UICONTROL Graph View] でレポートを表示する場合にのみ使用できます。

チャートの左側でエクスペリエンスを選択（または非選択に）することで、対応するエクスペリエンスをチャートに表示（または非表示に）します。

## 現在の平均 {#section_59066693158C4433B87D07402C2BC6CD}

[!UICONTROL Graph View] でレポートを表示する場合にのみ使用できます。

「実行中の平均」は、レポートウィンドウの開始からグラフに表示される日付までの累積コンバージョンを、累積訪問者数で割った値を反映します。

目的のグラフ表示を選択します。

* 現在の平均
* 現在の平均上昇率
* 毎日
* 日別上昇率（Daily Lift）

このドロップダウンリストの名前は、選択したビューによって異なりますが、上記のビューのいずれかになります。

## カウント手法 {#section_01B0ED5665C74AE1AE97259800190C3E}

[!UICONTROL Graph View] でレポートを表示する場合にのみ使用できます。

レポート内のグラフのカウント手法を選択できます。この機能は [!UICONTROL Automated Personalization] （AP）アクティビティには対応していません。

グラフモードでレポートを表示しているときに「[!UICONTROL Counting Methodology]」オプションにアクセスするには、「**[!UICONTROL My Primary Goal]**」ドロップダウンをクリックし、カウント方法を選択します。

カウント方法は、前述の [!UICONTROL Settings] ダイアログで選択した方法と同じです。

デフォルトでは、グラフは [!UICONTROL Daily] モードでプロットされます。

[!UICONTROL Daily] ドロップダウンリストをクリックし、累積オプションを選択すると、モードを変更できます。

>[!NOTE]
>
>このドロップダウンリストの名前は、選択したモードによって異なります。

[!UICONTROL Auto-Target] アクティビティには、[!UICONTROL Daily Control]、[!UICONTROL Daily Targeted]、[!UICONTROL Cumulative Control]、[!UICONTROL Cumulative Targeted] の 4 つのモードがあります。

グラフがプロットされる順番は、デフォルトでは次のようになります。

* **[!UICONTROL A/B Test]（[!UICONTROL Auto-Allocate] および [!UICONTROL Automated Personalization] を含む）**：エクスペリエンス作成の順序（降順）。
* **[!UICONTROL Experience Targeting]（XT）**：アクティビティ内のエクスペリエンスの順序。
* **[!UICONTROL Multivariate Test]（MVT）**：エクスペリエンス名のアルファベット順。
* **[!UICONTROL Recommendations]**：エクスペリエンス作成の順序（降順）。

[!UICONTROL Counting Methodology] のオプションを使用する場合は、次の点に注意してください。

* [[!UICONTROL Auto-Target] アクティビティの場合 ](/help/main/c-activities/auto-target/auto-target-to-optimize.md) カウント方法として「訪問者」を選択するオプションはありません。 訪問者がプロットできない唯一のアクティビティタイプは [!UICONTROL Auto-Target] です。
* [Analytics をレポートソースとして使用（A4T） ](/help/main/c-integrating-target-with-mac/a4t/a4t.md) するアクティビティの場合、訪問者、訪問、インプレッションを累積的にプロットすることはできません。

## アクティビティのエクスペリエンスが 16 を超えるグラフの操作

エクスペリエンスが 16 個以下のアクティビティの場合は、それぞれのエクスペリエンスが違う色でグラフにプロットされます。

エクスペリエンスが 17 個以上の場合は、最初の 16 個のエクスペリエンスが色分けされた線でグラフに表示されます。残りのエクスペリエンスは、左側のエクスペリエンスパネルに灰色で表示され、対応するプロット線はグラフに表示されません。一度に表示できるエクスペリエンスの線は 16 個までです。

灰色表示のエクスペリエンスにマウスポインターを置くと、そのエクスペリエンスに対応する新しい灰色のプロット線が一時的にグラフに表示されます。灰色表示になっているエクスペリエンスのプロット線を色付きで表示するには、色付きで表示されているエクスペリエンスの名前をクリックして選択を解除してから、灰色表示のエクスペリエンスの名前を選択します。

グラフには、最初の 16 個のエクスペリエンスの線が表示されています（いくつかは重複しているので、16 個よりも少なく見えます）。左側にあるエクスペリエンスパネルに表示されている各エクスペリエンス名の横にある色付きの点は、対応するエクスペリエンスのプロット線が、その色で表示されていることを示しています。

エクスペリエンスパネルを下にスクロールすると、次の図のように、17 個目から 26 個目までのエクスペリエンスの名前が灰色表示になっていることがわかります。

灰色表示のエクスペリエンスにマウスポインターを置くと、そのエクスペリエンスに対応する新しい灰色のプロット線が一時的にグラフに表示されます。

例えば、エクスペリエンス R のプロット線を表示し、エクスペリエンス P の線を非表示にしたい場合は、次の図のようにエクスペリエンス P の名前をクリックして選択を解除し、エクスペリエンス R の名前をクリックして選択します。
