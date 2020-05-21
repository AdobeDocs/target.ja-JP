---
keywords: analytics for target;a4t;analytics as the reporting source
description: Analytics を Target のレポートソースとして使用すると（A4T）、Target アクティビティに関する Analytics レポートを利用できるようになります。
title: A4T レポート
subtopic: Multivariate Test
topic: Standard
uuid: bd3a7fa4-ba45-4ea3-81b6-fc2584831ce4
translation-type: tm+mt
source-git-commit: 68f356b0711abf9acf7ef631edf3656bd3dd49e3
workflow-type: tm+mt
source-wordcount: '733'
ht-degree: 44%

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

## Analytics のレポート {#section_F6884872DC864AE7913587FAED4CD11C}

In [!DNL Analytics], click **[!UICONTROL Target]** > **[!UICONTROL Target Activities]** in the left menu. In [!DNL Target], the activity&#39;s reports automatically show [!DNL Analytics] data, metrics, and segments. これらのレポートでは、データがサイトから収集された約 1 時間後にデータが表示されます。レポート内のすべての指標、オーディエンスおよび値は、アクティビティを設定したときに選択したレポートスイートから収集されます。

In [!DNL Analytics], use the [!UICONTROL Target Activities] report to view the results of your [!DNL Target] activity. Test&amp;Target (Legacy) Reports provides information about your old Test&amp;Target plug-in style page integrations and does not include [!DNL Analytics] for [!DNL Target] data. In the [!UICONTROL Activities] report, view information about your [!DNL Target] experiences. 「**[!UICONTROL 指標]**」をクリックして、「**[!UICONTROL Target」指標タイプを選択します。]**&#x200B;レポートでは、2 つの指標を利用できます。

* **アクティビティのエントリ：**[!DNL Target] レポートの参加者数に対応します。
* **アクティビティのコンバージョン：**[!DNL Target] レポートのカスタムコンバージョン数に対応します。

>[!NOTE]
>
>[!DNL Target] 上昇率と信頼性の詳細は、でも参照でき [!DNL Analytics]ます。 詳しくは、『 [Analyticsコンポーネントガイド』の「](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/report-target-lift-confidence.html) ターゲットの上昇率と信頼性 *」を参照してください*。

>[!IMPORTANT]
>
>If your [!UICONTROL Target Activities] report in [!DNL Analytics] lists &quot;unspecified&quot; instead of listing your activities, an update is required to your provisioned account. カスタマーケアに連絡して、この問題を解決してください。

## Target のレポート {#section_C0D1F17F88374B6690BF904D7B83B42E}

When [!DNL Analytics] is used as the reporting source, reports in [!DNL Target] show the data gathered from [!DNL Analytics]. The report differs somewhat from other [!DNL Target] reports:

* The [!UICONTROL Audiences] list shows the audiences available to your [!DNL Analytics] report suite.
* The [!UICONTROL Metric] list shows every metric available through [!DNL Analytics].

   Every metric is available, including any custom or calculated metrics that are built-in in [!DNL Analytics].

   このレポートでは、実際には数値の上昇が好ましくない状況であっても、数値の上昇が肯定的な現象として表示されることに注意してください。例えば、バウンス率を低く抑えたい場合であっても、最も高いバウンス率を持つものが勝者として表示されます。このような指標の取り扱いには注意が必要です。ポートに基づいて判断をおこなう場合には、数値が低下した方が好ましいのか、上昇した方が好ましいのかを確認してください。

You can apply the metric or audience to the report in [!DNL Target] after the activity has started, or even after the test has completed. 測定する内容を事前に正確に知っておく必要はありません。

Click to view the full [!DNL Analytics] report directly from the activity report page.

## Analysis Workspace のレポート {#reports-in-analysis-workspace}

[!DNL Adobe Analysis Workspace] を使用すると、データをより深く分析したり、データを可視化したり、表に現れない隠れたインサイトを明らかにしたりできます。

For detailed information and examples, open the [Analytics &amp; Target: Best Practices for Analysis tutorial](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), provided by [!DNL Adobe Experience League].

## アクティビティの作成 {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

アクティビティを作成する場合は、[!UICONTROL 設定]ページでアクティビティの目標を指定する必要があります。この目標は、レポートのデフォルトの指標となり、指標セレクターで常に先頭に表示されます。通常の Target アクティビティとは異なり、レポート用のセグメントを自由に選択できません。A test with [!DNL Analytics] uses [!DNL Adobe Analytics] segments rather than [!DNL Target] audiences.

## Performing offline calculations for Analytics for Target (A4T) {#section_33A97A691F3A45D497DAF57A844388F0}

A4T でオフライン計算を実行することはできますが、[!DNL Analytics] でのデータエクスポートを含む手順が必要になります。

詳しくは、[Analytics for Target（A4T）でのオフライン計算の実行](../../c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B)を参照してください。
