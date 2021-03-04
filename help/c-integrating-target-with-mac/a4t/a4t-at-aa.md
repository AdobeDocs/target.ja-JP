---
keywords: a4t;A4T;Target のレポートソースとしての Analytics
description: Analyticsをレポートソースとして使用するAdobe Targetで自動配分および自動ターゲットアクティビティを作成する方法を説明します(A4T)。
title: A4Tは自動配分と自動ターゲットのアクティビティをサポートしますか。
feature: Analytics for Target（A4T）
translation-type: tm+mt
source-git-commit: 4abf975095c5e29eea42d67119a426a3922d8d79
workflow-type: tm+mt
source-wordcount: '862'
ht-degree: 3%

---


# 自動配分と自動ターゲットアクティビティのA4Tのサポート

[!DNL Adobe Target]-to-[!DNL Adobe Analytics]統合([ターゲット](/help/c-integrating-target-with-mac/a4t/a4t.md)の分析(A4T)は、[!UICONTROL 自動配分]および[!UICONTROL 自動ターゲット]アクティビティをサポートします。

A4T統合では、次のことが可能です。

* [自動配分](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)のマルチアームバンディット機能を使用して、勝者エクスペリエンスにトラフィックを誘導します。
* [自動ターゲット](/help/c-activities/auto-target/auto-target-to-optimize.md)のアンサンブル機械学習アルゴリズムを使用して、各訪問者に最適なエクスペリエンスを選択します。 自動ターゲットは、[!DNL Adobe Analytics]目標指標と[!DNL Adobe Analytics]’豊富なレポート機能と分析機能を使用しながら、ユーザーのプロファイル、行動、およびコンテキストに基づいて最適なエクスペリエンスを選択します。

A/Bテストおよびエクスペリエンスのターゲット設定アクティビティで使用する[A4Tを実装したことを確認してください](/help/c-integrating-target-with-mac/a4t/a4timplementation.md)。 `analyticsLogging = client_side`を使用する場合は、`sessionId`値を[!DNL Analytics]に渡す必要もあります。 詳しくは、*Adobe TargetSDK*&#x200B;ガイドの[ターゲット用のAnalytics(A4T)レポート](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting)を参照してください。

開始するには

1. A/Bテストアクティビティの作成時に、**[!UICONTROL ターゲティング]**&#x200B;ページで、**[!UICONTROL トラフィック配分方法]**&#x200B;として次のいずれかのオプションを選択します。

   * [!UICONTROL 最適なエクスペリエンスへの自動配分]
   * [!UICONTROL パーソナライズされたエクスペリエンスの自動ターゲット]

   ![トラフィック配分方法のオプション：手動、自動配分、自動ターゲット](/help/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   詳細と手順については、[自動配分アクティビティの作成](/help/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md)および[自動ターゲットアクティビティの作成](/help/c-activities/auto-target/create-auto-target.md)を参照してください。

1. **[!UICONTROL 目標と設定]**&#x200B;ページで&#x200B;**[!UICONTROL レポートソース]**&#x200B;に対して&#x200B;**[!UICONTROL Adobe Analytics]**&#x200B;を選択し、目的の最適化目標に対応するレポートスイートを選択します。

   ![目標と設定ページの「レポートソース」セクション](/help/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. プライマリ目標指標を選択します。

   * [!DNL Adobe Target]を使用して最適化目標を指定するには、**[!UICONTROL コンバージョン]**&#x200B;を選択します。
   * 「**[!UICONTROL Analytics指標]**&#x200B;を使用」を選択し、[!DNL Analytics]から最適化目標として使用する指標を選択します。 デフォルトの[!DNL Analytics]コンバージョン指標または[!DNL Analytics]カスタムイベントを使用できます。

   詳しくは、[サポートされる目標指標](#supported)を参照してください。

1. アクティビティを保存してアクティブ化します。

   [!UICONTROL 自動] 配分は、選択した指標を使用してアクティビティを最適化し、訪問者を目標指標を最大化するエクスペリエンスに誘導します。

   または

   [!UICONTROL 自動] ターゲットは、選択した指標を使用してアクティビティを最適化し、訪問者をパーソナライズされた最高のエクスペリエンスに誘導します。

1. **[!UICONTROL 「レポート]**」タブを使用して、[!DNL Adobe Analytics]指標を選択してアクティビティのレポートを表示します。 Analytics ]**の**[!UICONTROL &#x200B;表示をクリックして詳細を調べ、レポートデータをさらにセグメント化します。

## サポートされる目標指標{#supported}

[!UICONTROL A4] 自動配分と    自動ターゲットレットの場合、最適化の主な目標指標として次の指標タイプを選択します。

* [!DNL Adobe Target] コンバージョン指標と考えることができます
* [!DNL Adobe Analytics] コンバージョン指標と考えることができます
* [!DNL Adobe Analytics] つのカスタムイベント

[!UICONTROL A4] 自動配分と [!UICONTROL 自動ターゲットの場合、2項]   目のイベントに基づく指標を選択する必要があります。2項イベントは発生しないか、発生しません。 2項イベントには、クリック、コンバージョン、注文などが含まれます。 この種のイベントは、ベルヌーイイベント、バイナリイベント、離散的なイベントとも呼ばれます。

[!UICONTROL A4]  For [!UICONTROL  Auto-] Allocateおよび [!UICONTROL Auto-] Targetは、連続指標の最適化をサポートしていません。連続的な指標には、売上高、注文された商品数、セッション期間、セッション中のページ表示数などが含まれます。 これらのサポートされていないタイプの指標は、非二項指標または非ベルヌーイ指標とも呼ばれます。

次の指標タイプは、主要目標指標としてサポートされていません。

* [!DNL Adobe Target] エンゲージメントと売上高の指標
* [!DNL Adobe Analytics] エンゲージメントと売上高の指標

   [!DNL Analytics]エンゲージメント指標または売上高指標を主目標指標として選択できます。これは、[!DNL Target]は[!DNL Analytics]からすべてのエンゲージメントおよび売上高指標を識別および除外できないからです。 [!DNL Analytics]から2項コンバージョン指標またはカスタムイベントのみを選択します。

* [!DNL Adobe Analytics] 計算指標

## 制限事項とメモ

[!UICONTROL 自動配分]と[!UICONTROL 自動ターゲット]の両方のアクティビティには、いくつかの制限と注意事項が適用されます。 その他の制限や注意事項は、1つのアクティビティタイプまたは他のタイプに適用されます。

### 自動配分と自動ターゲット

* レポートソースを[!DNL Analytics]から[!DNL Target]に変更したり、アクティビティがアクティブ化された後に逆に変更することはできません。
* 計算指標は主要目標指標としてサポートされていませんが、多くの場合、カスタムイベントを主要目標指標として選択する代わりに、意図した結果を得ることができます。 例えば、「訪問者ごとのフォームの完了」などの指標を最適化する場合は、「フォームの完了」に対応するカスタムイベントを主要目標指標として選択します。 [!DNL Target] トラフィックの偏りを考慮して、訪問あたりのコンバージョン指標を自動的に標準化するので、計算指標を使用して標準化を実行する必要はありません。
* [!DNL Target] は、 [!UICONTROL 自動配分機能で「同じタッチ」アトリビューションモデルを使用し] ます。ターゲットの分析(A4T)。

### 自動配分

* [!UICONTROL 自動] 配分モデルでは、通常どおり、2時間ごとにトレーニングが行われます。

### 自動ターゲット

* [!UICONTROL 自動ター] ゲットモデルでは、通常どおり、24時間ごとにトレーニングが行われます。ただし、[!DNL Analytics]からのコンバージョンイベントデータは、6 ～ 24時間延長されます。 この遅延は、[!DNL Target]によるトラフィックの分散が、[!DNL Analytics]に記録された最新のイベントを追跡することを意味します。 この遅延は、アクティビティが最初にアクティブ化されてから最初の48時間で最も大きな影響を与えます。 アクティビティのパフォーマンスは、5日が経過した後の[!DNL Analytics]コンバージョンの動作とより密接に反映されます。 短期間のアクティビティでは[!UICONTROL 自動ターゲット]の代わりに[!UICONTROL 自動配分]を使用することを検討してください。この期間中、ほとんどのトラフィックはアクティビティの寿命の最初の5日間に発生します。
* [!DNL Analytics]を[!UICONTROL 自動ターゲット]アクティビティのデータソースとして使用すると、セッションは6時間経過後に終了します。 6時間後に発生したコンバージョンはカウントされません。

詳しくは、*Analyticsツールガイド*&#x200B;の[アトリビューションモデルとルックバックウィンドウ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html)を参照してください。
