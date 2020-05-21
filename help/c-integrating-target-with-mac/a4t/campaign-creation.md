---
keywords: a4t;A4T;Analytics as the reporting source for Target
description: Target Standard/Premium のアクティビティを設定するときに、Adobe Analytics をレポートソースとして使用できます（A4T）。
title: アクティビティの作成
topic: Advanced,Standard,Classic
uuid: b04ad535-62fb-4dd3-ab3f-23da60fbffbd
translation-type: tm+mt
source-git-commit: 68f356b0711abf9acf7ef631edf3656bd3dd49e3
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 42%

---


# アクティビティの作成{#activity-creation}

You can configure an activity in [!DNL Target] to use [!DNL Adobe Analytics] as the reporting source (A4T).

Before you set up an activity that uses [!DNL Analytics] as the reporting source, establish the goal for the activity, such as improving revenue per visitor (RPV) or increasing clicks on your shopping cart. アクティビティの最終的な成功指標を選択します。Although you can select additional metrics at any time in [!DNL Analytics], you must still specify a particular metric you expect this test to affect.

Creating a [!DNL Target] activity that uses [!DNL Analytics] as the reporting source is similar to setting up a regular [!DNL Target] activity, with a few important differences. For example, you cannot select a segment for reporting while creating the activity because all segments available in [!DNL Analytics] can be applied when viewing a report.

1. 「**[!UICONTROL アクティビティを作成]**」をクリックします。

   >[!NOTE]
   >
   >An activity name cannot include the &quot;%&quot; character if [!DNL Analytics] is used as the reporting source.

1. アクティビティのタイプを選択して、アクティビティの設定を開始します。
1. アクティビティ作成フローの&#x200B;**[!UICONTROL 設定]**&#x200B;の段階までたどり着いたら、「**[!UICONTROL Adobe Analytics]**」を選択し、会社を指定します。
1. レポートスイートを選択します。

   You can choose any report suite that is available to you in [!DNL Analytics]. レポートスイートによって、収集されたデータを利用できる場所が定義されます。仮想レポートスイートはレポートスイートのリストに含まれません。.

   レポートスイートを選択する際に、次の 2 つのエラーが発生する可能性があります。

   * レポートスイートが利用できないが、アカウントが正しく設定されているというエラーが表示されます。

      You might need to check your [!DNL Analytics] company. If your [!DNL Adobe Experience Cloud] account is tied to more than one [!DNL Analytics] company, log out of [!DNL Target], and log in to [!DNL Analytics] under the right company. Then return to [!DNL Target], and the report suites will load.

   * 対象のレポートスイートが表示されません。

      Only report suites that are provisioned to connect to [!DNL Target] will be available for selection. If you don&#39;t see the report suite(s) you expect, first try logging out and logging back in to the [!DNL Adobe Experience Cloud] to try again.
   それでもレポートスイートがリストに表示されない場合、[カスタマーケアまでお問い合わせください](../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。

1. トラッキングサーバーを指定します。

   詳細については、「[Analytics トラッキングサーバーの使用](../../c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)」を参照してください。

1. エクスペリエンスを定義します。
1. アクティビティの目標を指定します。

   各アクティビティの目標として使用する成功指標を選択する必要があります。 アクティビティの目標は、アクティビティの成功を示すコンバージョンアクティビティです。ベストプラクティスは、必ず何らかの意味で向上が図れる目標を設定してからテストを実行することです。You can choose any [!DNL Analytics] metric available in the [!DNL Analytics] metric selector.

   >[!NOTE]
   >
   >You can send a custom Target-based metric to [!DNL Analytics] rather than relying only on [!DNL Analytics] data. For example, you can monitor clicking on a page, which is usually not tracked by [!DNL Analytics]. This custom metric is sent to [!DNL Analytics] automatically from the [!DNL Target] server, and appears as the &quot;[!DNL Target] Conversion&quot; metric in the metrics selector in [!DNL Analytics]. The [!DNL Target] Conversion metric is empty if you choose to use [!DNL Analytics] metrics.

   目標を設定した場合でも、テスト結果を評価する際に他の指標を使用することは可能です。ただし、この目標は、アクティビティにおいて向上させたいものを明確にする役割を果たします。

   訪問者は、目標を達成した後もアクティビティ内にとどまります。訪問者には引き続きアクティビティコンテンツが表示されますが、新たなアクティビティエントリとしてはカウントされません。

   >[!NOTE]
   >
   >When setting up an activity after setting up [!DNL Analytics] as your reporting source, there is no option to set up audiences for reporting. [!DNL Analytics] セグメントは [!DNL Target] アクティビティレポートで使用できます。

1. 「**[!UICONTROL 保存]**」をクリックします。
