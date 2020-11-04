---
keywords: a4t;A4T;Analytics as the reporting source for Target
description: Target Standard/Premium のアクティビティを設定するときに、Adobe Analytics をレポートソースとして使用できます（A4T）。
title: A4Tをレポートソースとして使用するアクティビティの作成
feature: a4t general
topic: Advanced,Standard,Classic
uuid: b04ad535-62fb-4dd3-ab3f-23da60fbffbd
translation-type: tm+mt
source-git-commit: e18f18e6d6e0b8fc6eb5ada845e2fe5377d6c5d0
workflow-type: tm+mt
source-wordcount: '1393'
ht-degree: 18%

---


# Analyticsをレポートソースとして使用するアクティビティの作成

You can configure an activity in [!DNL Target] to use [!DNL Adobe Analytics] as the reporting source (A4T).

Before you set up an activity that uses [!DNL Analytics] as the reporting source, establish the goal for the activity, such as improving revenue per visitor (RPV) or increasing clicks on your shopping cart. アクティビティの最終的な成功指標を選択します。Although you can select additional metrics at any time in [!DNL Analytics], you must still specify a particular metric you expect this test to affect.

## アクティビティの作成

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

## 自動配分と自動ターゲットアクティビティのターゲット分析(A4T)のサポート {#a4t-aa}

Adobe TargetとAdobe Analyticsの統合をアップグレードしました。これは、 [Analytics forターゲットと呼ばれ](/help/c-integrating-target-with-mac/a4t/a4t.md)ます。 自動配分および自動ターゲットアクティビティで、Analyticsのターゲットがサポートされるようになりました。

この統合により、次のことが可能になります。

* [自動配分のマルチアームバンディット機能を使用して](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)、勝者エクスペリエンスにトラフィックを誘導します。
* [自動ターゲットのアンサンブル機械学習アルゴリズムを使用して](/help/c-activities/auto-target/auto-target-to-optimize.md)[!DNL Adobe Analytics][!DNL Adobe Analytics]、目標指標と豊富なレポート機能と分析機能を使用しながら、訪問者のプロファイル、行動、コンテキストに基づいて、各に最適なエクスペリエンスを選択します。

A/Bテストおよびエクスペリエンスのターゲット設定アクティビティで使用するA4Tが [実装されていることを確認します](/help/c-integrating-target-with-mac/a4t/a4timplementation.md)。 を使用している場合 `analyticsLogging = client_side`は、に `sessionId` 値を渡す必要もあり [!DNL Analytics]ます。 詳しくは、『 [Adobe TargetSDK](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting) 』ガイドの「ターゲット用の *Analytics(A4T)のレポート* 」を参照してください。

開始するには

1. A/Bテストアクティビティの作成時に、 **[!UICONTROL ターゲット]** ページで、「 **[!UICONTROL トラフィック配分方法]**」として次のいずれかのオプションを選択します。

   * 最高のエクスペリエンスへの自動配分
   * パーソナライズされたエクスペリエンスの自動ターゲット

1. **[!UICONTROL 目標と設定]** ページで、 **[!UICONTROL レポートソース]** ( **** Adobe Analytics)を選択し、目的の最適化目標に対応するレポートスイートを選択します。

1. プライマリ目標指標を選択します。

   * 最適化目標の指定に使用する **[!UICONTROL コンバージョン]**[!DNL Adobe Target] を選択します。
   * 「Analytics指標 **[!UICONTROL を使用」を選択し]** 、最適化目標として使用 [!DNL Analytics] する指標を選択します。 すぐに使用できるコンバージョン指標または [!DNL Analytics] カスタム [!DNL Analytics] イベントを使用できます。

1. アクティビティを保存してアクティブ化します。

   [!UICONTROL 自動配分は] 、選択した指標を使用してアクティビティを最適化し、訪問者を目標指標を最大化するエクスペリエンスに誘導します。

   または

   [!UICONTROL 自動ターゲット] は、選択した指標を使用してアクティビティを最適化し、訪問者をパーソナライズされた最高のエクスペリエンスに誘導します。

1. 「 **[!UICONTROL レポート]** 」タブを使用して、指 [!DNL Adobe Analytics] 標を選択してアクティビティのレポートを表示します。 Analyticsの **** 表示をクリックして、レポートデータを詳細に分析し、さらにセグメント化します。

### サポートされる目標指標

[!UICONTROL 自動配分] と [!UICONTROL 自動ターゲットのA4T] では、次の指標タイプを最適化の主な目標指標として選択できます。

* [!DNL Adobe Target] コンバージョン指標と考えることができます
* [!DNL Adobe Analytics] コンバージョン指標と考えることができます
* [!DNL Adobe Analytics] つのカスタムイベント

[!UICONTROL 自動配分] と [!UICONTROL 自動ターゲットのA4T] では、2項イベントに基づく指標、つまり、クリック、コンバージョン、注文など、発生しない、または発生しないイベントを選択する必要があります。 (この種のイベントは、ベルヌーイイベント、バイナリモジュール、離散とも呼ばれます)。

[!UICONTROL 自動配分] と [!UICONTROL 自動ターゲットのA4T] ( [!UICONTROL 自動配分] )は、売上高、注文された商品数、セッション期間、セッション内のページ表示数などの継続的な指標の最適化をサポートしていません。 （これらのサポートされていないタイプの指標は、非二項指標または非ベルヌーイ指標とも呼ばれます）。

次の指標タイプは、主要目標指標としてサポートされていません。

* [!DNL Adobe Target] エンゲージメントと売上高の指標
* [!DNL Adobe Analytics] エンゲージメントと売上高の指標

   エンゲージメント指標または [!DNL Analytics] 売上高指標を主要目標指標として選択できる場合があります。これは、すべてのエンゲージメント指標と売上高指標を特定したり、それらの指標から除外したり [!DNL Target] できないからです [!DNL Analytics]。 2項コンバージョン指標またはカスタムイベントのみを選択する場合は、注意が必要 [!DNL Analytics]です。

* [!DNL Adobe Analytics] 計算指標

### 制限事項とメモ

自動配分と自動ターゲットの両方に適用される制限と注意事項がいくつかあります。 その他の制限や注意事項は、1つのアクティビティタイプまたは他のタイプに適用されます。

#### 自動配分と自動ターゲット

* アクティビティがアクティブ化された後、レポートソース [!DNL Analytics] をから [!DNL Target] に、またはその逆に変更することはできません。
* 計算指標は主要目標指標としてサポートされていませんが、多くの場合、カスタムイベントを主要目標指標として選択する代わりに、意図した結果を得ることができます。 例えば、「訪問者ごとのフォームの完了」などの指標を最適化する場合は、「フォームの完了」に対応するカスタムイベントを主要目標指標として選択します。 [!DNL Target] トラフィックの偏りを考慮して、訪問あたりのコンバージョン指標を自動的に標準化するので、計算指標を使用して標準化を実行する必要はありません。
* [!DNL Target] は、 [!UICONTROL 自動配分] A4T実装で「同じタッチ」アトリビューションモデルを使用します。

#### 自動配分

* [!UICONTROL 自動配分モデルは] 、通常どおり、2時間ごとにトレーニングを続けます。

#### 自動ターゲット

* [!UICONTROL 自動ターゲット] ・モデルは、通常通り24時間ごとにトレーニングを行います。 ただし、からのコンバージョンイベントデータ [!DNL Analytics] は、さらに6 ～ 24時間遅れます。 この遅延は、に記録された最新のイベントに従っ [!DNL Target] て、によるトラフィックの配分が行われることを意味 [!DNL Analytics]します。 これは、アクティビティが最初にアクティブ化されてから最初の48時間で最大の効果を得ます。アクティビティのパフォーマンスは、5日が経過した後の [!DNL Analytics] コンバージョン動作とより密接に反映されます。 アクティビティ期間が短い場合は、 [!UICONTROL 自動ターゲットの代わりに] 自動配分を使用することをお勧めします。この場合、アクティビティ期間の最初の5日間にほとんどのトラフィックが発生します。
* を [!DNL Analytics] 自動ターゲット  アクティビティのデータソースとして使用する場合、セッションは6時間経過後に終了したと見なされます。 6時間後に発生したコンバージョンはカウントされません。

詳しくは、『 [Analyticsツールガイド』のアトリビューションモデルとルックバックウィンドウ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/models.html) ( *Windows*)を参照してください。
