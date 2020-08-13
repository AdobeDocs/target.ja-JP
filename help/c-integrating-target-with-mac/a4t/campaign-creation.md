---
keywords: a4t;A4T;Analytics as the reporting source for Target
description: Target Standard/Premium のアクティビティを設定するときに、Adobe Analytics をレポートソースとして使用できます（A4T）。
title: アクティビティの作成
feature: a4t general
topic: Advanced,Standard,Classic
uuid: b04ad535-62fb-4dd3-ab3f-23da60fbffbd
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '1130'
ht-degree: 22%

---


# アクティビティの作成{#activity-creation}

You can configure an activity in [!DNL Target] to use [!DNL Adobe Analytics] as the reporting source (A4T).

Before you set up an activity that uses [!DNL Analytics] as the reporting source, establish the goal for the activity, such as improving revenue per visitor (RPV) or increasing clicks on your shopping cart. アクティビティの最終的な成功指標を選択します。Although you can select additional metrics at any time in [!DNL Analytics], you must still specify a particular metric you expect this test to affect.

## Analyticsをレポートソースとして使用するアクティビティの作成

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

## 自動配分アクティビティのターゲット用のAnalytics(A4T)のサポート {#a4t-aa}

Adobe TargetとAdobe Analyticsの統合をアップグレードしました。これは、 [Analytics forターゲットと呼ばれ](/help/c-integrating-target-with-mac/a4t/a4t.md)ます。

[!UICONTROL 自動配分] アクティビティで、ターゲットの [!UICONTROL Analyticsがサポートされるようになりました]。 この統合により、自動配分のマルチアームバンディット機能を使用して、目標指標や [!DNL Adobe Analytics] レポートおよび [!DNL Adobe Analytics] 分析機能を使用しながら、トラフィックを勝者エクスペリエンスに誘導できます。 A/Bテストおよびエクスペリエンスのターゲット設定アクティビティで使用するA4Tを [既に実装している場合](/help/c-integrating-target-with-mac/a4t/a4timplementation.md)、準備は完了です。

開始するには

1. A/Bテストアクティビティを作成し、ター **[!UICONTROL ゲット設定]** ページの「トラフィック配分方法 **** 」として、「最良のエクスペリエンスに自動配分」を選択します。
1. **[!UICONTROL 目標と設定]** ページで、 **[!UICONTROL レポートソース]** ( **** Adobe Analytics)を選択し、目的の最適化目標に対応するレポートスイートを選択します。
1. プライマリ目標指標を選択します。

   最適化目標の指定に使用する **[!UICONTROL コンバージョン]**[!DNL Adobe Target] を選択します。

   または

   「Analytics指標 **[!UICONTROL を使用」を選択し]** 、最適化目標として使用 [!DNL Analytics] する指標を選択します。 既製のコンバージョン指標または [!DNL Analytics] カスタム [!DNL Analytics] イベントを使用できます。

1. アクティビティを保存してアクティブ化します。

   [!UICONTROL 自動配分は] 、選択した指標を使用してアクティビティを最適化し、訪問者を目標指標を最大化するエクスペリエンスに誘導します。

1. 「 **[!UICONTROL レポート]** 」タブを使用して、指 [!DNL Adobe Analytics] 標を選択してアクティビティのレポートを表示します。 Analyticsの **** 表示をクリックして、レポートデータを詳細に分析し、さらにセグメント化します。

### サポートされる目標指標

 自動配分のA4Tでは、最適化の主な目標指標として次の指標タイプのいずれかを選択できます。

* [!DNL Adobe Target] コンバージョン指標と考えることができます
* [!DNL Adobe Analytics] コンバージョン指標と考えることができます
* [!DNL Adobe Analytics] つのカスタムイベント

[!UICONTROL 自動配分のA4Tでは、2項イベントに基づく指標、つまり、クリック、コンバージョン、注文など] 、発生しない、または発生しないイベントを選択する必要があります。 (この種のイベントは、ベルヌーイイベント、バイナリモジュール、離散とも呼ばれます)。

 自動配分用のA4Tは、売上高、注文された商品数、セッション期間、セッション内のページ表示数などの連続的な指標の最適化をサポートしていません。 （これらのサポートされていないタイプの指標は、非二項指標または非ベルヌーイ指標とも呼ばれます）。

次の指標タイプは、主要目標指標としてサポートされていません。

* [!DNL Adobe Target] エンゲージメントと売上高の指標
* [!DNL Adobe Analytics] エンゲージメントと売上高の指標

   >[!NOTE]
   >
   >エンゲージメント指標と売上高指標は、主な目標指標として選択できる場合があります。これは、からすべてのエンゲージメント指標と売上高指標を識別 [!DNL Analytics] できないため [!DNL Target][!DNL Analytics]です。 2項コンバージョン指標またはカスタムイベントのみを選択する場合は、注意が必要 [!DNL Analytics]です。

* Adobe Analytics計算指標

### 制限事項とメモ

* アクティビティがアクティブ化された後は、レポートソース [!DNL Analytics] をから [!DNL Target] に変更したり、その逆を変更したりすることはできません。
* 計算指標は主要目標指標としてサポートされていませんが、多くの場合、カスタムイベントを主要目標指標として選択する代わりに、意図した結果を得ることができます。 例えば、「訪問者ごとのフォームの完了」などの指標を最適化する場合は、「フォームの完了」に対応するカスタムイベントを主要目標指標として選択します。 [!DNL Target] トラフィックの偏りを考慮して、訪問あたりのコンバージョン指標を自動的に標準化するので、計算指標を使用して標準化を実行する必要はありません。
* [!DNL Target] は、自動配分A4T実装の「同じタッチ」アトリビューションモデルを使用します。

詳しくは、 [Analyticsツールガイドのアトリビューションの概要](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution/attribution.html) ( *Attribution overview*)を参照してください。
