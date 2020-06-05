---
keywords: analytics for target;a4t;analytics as the reporting source
description: Analytics を Target のレポートソースとして使用すると（A4T）、Target アクティビティに関する Analytics レポートを利用できるようになります。
title: A4T レポート
subtopic: Multivariate Test
topic: Standard
uuid: bd3a7fa4-ba45-4ea3-81b6-fc2584831ce4
translation-type: tm+mt
source-git-commit: 59c26a766018affe5ef7b5fa4ea5a421ab3cc37d
workflow-type: tm+mt
source-wordcount: '669'
ht-degree: 35%

---


# A4T レポート{#a-t-reporting}

Using [!DNL Analytics] as your reporting source for [!DNL Target] (A4T) gives you access to [!DNL Analytics] reports for your [!DNL Target] activities.

You can view reports for your activities in both [!DNL Analytics] and [!DNL Target].

For reporting best practices using [!DNL Analytics] for [!DNL Target], [visit this Adobe Spark page](https://spark.adobe.com/page/Lo3Spm4oBOvwF/).

## 概要 {#section_035A62D65608423285D8A5A54731E2C5}

Both [!DNL Analytics] and [!DNL Target] reports measure entrants (the people who enter the tests), rather than visitors to the site.

Every time a visitor sees activity content on the page, [!DNL Target] makes a direct server-to-server call to [!DNL Analytics], including which activity and experience the visitor saw. [!DNL Target] また、コンバージョン [!DNL Analytics] がおこなわれるたびに呼び出されます。 [!DNL Analytics] によって、「アクティビティコンバージョン」という名前の特定の新しい [!DNL Analytics] イベントとしてコンバージョンが追加されます。このは、によって収集された他のデータと共に追跡され [!DNL Analytics]ます。

When the [!UICONTROL Select] operation is used and you sort on *Entrants*, then only experiences that received entrants during the selected time period are displayed in the reports.

>[!NOTE]
>
>Reports powered by [!DNL Target] have a latency of four minutes. For activities powered by A4T, in both the [!DNL Target] and [!DNL Analytics] reports, it can take up to 24 hours after the activity is initially saved before the report data can be broken down by experiences. 最初の 24 時間に収集されたデータも正確であり、適切なエクスペリエンスに割り当てられます。

## Analytics のレポート {#analytics}

に [!DNL Analytics]は、A4T統合を有効にした後に使用できるディメンションと指標がいくつか用意されています。

### ディメンション

* [!UICONTROL ターゲットの分析] — 統合を介して渡される親ID。 このディメンションの形式はで `Activity ID:Experience ID:3rd ID`す。 次のディメンションは、このディメンションの分類です。
* [!UICONTROL ターゲットアクティビティ]
* [!UICONTROL ターゲットエクスペリエンス]
* [!UICONTROL ターゲットアクティビティ] / [!UICONTROL エクスペリエンス]
* [!UICONTROL 3番目のID] — 無視可能

### 指標

* [!UICONTROL アクティビティのインプレッション] — レ [!UICONTROL ポートの][!DNL Target] 参加者数に一致します。
* [!UICONTROL アクティビティコンバージョン] — レポート内の [!UICONTROL カスタムコンバージョン][!DNL Target] 数に一致します。

で [!DNL Analysis Workspace]は、 [!UICONTROL Analyticsのターゲット用パネルを使用して、] 上昇率と信頼性を持つ [!DNL Target] アクティビティとエクスペリエンスを分析します。 詳しくは、Analyticsツールガイドの [ターゲット用の](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/a4t-panel.html) Analytics(A4T)パネル *(* Analyticsツールガイド)を参照してください。

>[!IMPORTANT]
>
>If your [!UICONTROL Target Activities] report in [!DNL Analytics] lists &quot;unspecified&quot; instead of listing your activities, an update is required to your provisioned account. カスタマーケアに連絡して、この問題を解決してください。

For detailed information and examples, open the [Analytics &amp; Target: Best Practices for Analysis](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) tutorial, provided by Adobe Experience League.

## Target のレポート {#section_C0D1F17F88374B6690BF904D7B83B42E}

When [!DNL Analytics] is used as the reporting source, reports in [!DNL Target] show the data gathered from [!DNL Analytics]. The report differs somewhat from other [!DNL Target] reports:

* The [!UICONTROL Audiences] list shows the audiences available to your [!DNL Analytics] report suite.
* The [!UICONTROL Metric] list shows every metric available through [!DNL Analytics].

   Every metric is available, including any custom or calculated metrics that are built-in in [!DNL Analytics].

   このレポートでは、実際には数値の上昇が好ましくない状況であっても、数値の上昇が肯定的な現象として表示されることに注意してください。例えば、バウンス率を低く抑えたい場合であっても、最も高いバウンス率を持つものが勝者として表示されます。このような指標の取り扱いには注意が必要です。ポートに基づいて判断をおこなう場合には、数値が低下した方が好ましいのか、上昇した方が好ましいのかを確認してください。

You can apply the metric or audience to the report in [!DNL Target] after the activity has started, or even after the test has completed. 測定する内容を事前に正確に知っておく必要はありません。

Click to view the full [!DNL Analytics] report directly from the activity report page.

## アクティビティの作成 {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

アクティビティを作成する場合は、[!UICONTROL 設定]ページでアクティビティの目標を指定する必要があります。この目標は、レポートのデフォルトの指標となり、指標セレクターで常に先頭に表示されます。通常の Target アクティビティとは異なり、レポート用のセグメントを自由に選択できません。A test with [!DNL Analytics] uses [!DNL Adobe Analytics] segments rather than [!DNL Target] audiences.

## Performing offline calculations for Analytics for Target (A4T) {#section_33A97A691F3A45D497DAF57A844388F0}

A4T でオフライン計算を実行することはできますが、[!DNL Analytics] でのデータエクスポートを含む手順が必要になります。

詳しくは、[Analytics for Target（A4T）でのオフライン計算の実行](../../c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B)を参照してください。
