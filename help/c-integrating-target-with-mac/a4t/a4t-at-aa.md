---
keywords: a4t;A4T;Target のレポートソースとしての Analytics
description: A4Tを自動ターゲットと自動配分のアクティビティと共に使用できますか。
title: 自動配分と自動ターゲットアクティビティのA4Tのサポート
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: 4f0f1df1bcb6baad0e20c4dc1ae7e12751080d91
workflow-type: tm+mt
source-wordcount: '838'
ht-degree: 2%

---


# 自動配分と自動ターゲットアクティビティのA4Tのサポート

[!DNL Adobe Target]-to-[!DNL Adobe Analytics]統合([ターゲット](/help/c-integrating-target-with-mac/a4t/a4t.md)の分析(A4T)は、[!UICONTROL 自動配分]および[!UICONTROL 自動ターゲット]アクティビティをサポートします。

A4T統合では、次のことが可能です。

* [自動配分](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)のマルチアームバンディット機能を使用して、勝者エクスペリエンスにトラフィックを誘導します。
* [自動ターゲット](/help/c-activities/auto-target/auto-target-to-optimize.md)のアンサンブル機械学習アルゴリズムを使用して、[!DNL Adobe Analytics]目標指標と[!DNL Adobe Analytics]の豊富なレポート機能と分析機能を使用しながら、プロファイル、行動、コンテキストに基づいて各訪問者に最適なエクスペリエンスを選択します。

A/Bテストおよびエクスペリエンスのターゲット設定アクティビティで使用する[A4Tを実装したことを確認してください](/help/c-integrating-target-with-mac/a4t/a4timplementation.md)。 `analyticsLogging = client_side`を使用する場合は、`sessionId`値を[!DNL Analytics]に渡す必要もあります。 詳しくは、*Adobe TargetSDK*&#x200B;ガイドの[ターゲット用のAnalytics(A4T)レポート](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting)を参照してください。

開始するには

1. A/Bテストアクティビティの作成時に、**[!UICONTROL ターゲティング]**&#x200B;ページで、**[!UICONTROL トラフィック配分方法]**&#x200B;として次のいずれかのオプションを選択します。

   * [!UICONTROL 最高のエクスペリエンスへの自動配分]
   * [!UICONTROL パーソナライズされたエクスペリエンスの自動ターゲット]

   ![トラフィック配分方法のオプション：手動、自動配分、自動ターゲット](/help/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   詳細と手順については、[自動配分アクティビティの作成](/help/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md)および[自動ターゲットアクティビティの作成](/help/c-activities/auto-target/create-auto-target.md)を参照してください。

1. **[!UICONTROL 目標と設定]**&#x200B;ページで&#x200B;**[!UICONTROL レポートソース]**&#x200B;に対して&#x200B;**[!UICONTROL Adobe Analytics]**&#x200B;を選択し、目的の最適化目標に対応するレポートスイートを選択します。

1. プライマリ目標指標を選択します。

   * **[!UICONTROL コンバージョン]**&#x200B;を選択して[!DNL Adobe Target]を使用し、最適化目標を指定します。
   * 「**[!UICONTROL Analytics指標]**&#x200B;を使用」を選択し、[!DNL Analytics]から最適化目標として使用する指標を選択します。 デフォルトの[!DNL Analytics]コンバージョン指標または[!DNL Analytics]カスタムイベントを使用できます。

1. アクティビティを保存してアクティブ化します。

   [!UICONTROL 自動] 配分は、選択した指標を使用してアクティビティを最適化し、訪問者を目標指標を最大化するエクスペリエンスに誘導します。

   または

   [!UICONTROL 自動ター] ゲット設定では、選択した指標を使用してアクティビティを最適化し、訪問者をパーソナライズされた最良のエクスペリエンスに誘導します。

1. **[!UICONTROL 「レポート]**」タブを使用して、[!DNL Adobe Analytics]指標を選択してアクティビティのレポートを表示します。 Analytics ]**の**[!UICONTROL &#x200B;表示をクリックして詳細を調べ、レポートデータをさらにセグメント化します。

## サポートされる目標指標

[!UICONTROL A4] 自動配分と    自動ターゲットレットの場合、最適化の主な目標指標として次の指標タイプを選択します。

* [!DNL Adobe Target] コンバージョン指標と考えることができます
* [!DNL Adobe Analytics] コンバージョン指標と考えることができます
* [!DNL Adobe Analytics] つのカスタムイベント

[!UICONTROL A4] 自動配分と    自動ターゲットの場合は、2項イベントに基づく指標、つまり、クリック、コンバージョン、注文など、発生しない、または発生しないイベントを選択する必要があります。この種のイベントは、ベルヌーイイベント、バイナリイベント、離散的なイベントとも呼ばれます。

[!UICONTROL A4] 自動配分と [!UICONTROL 自動]   ターゲットでは、売上高、注文された商品数、セッション期間、セッション中のページ表示数などの連続的な指標の最適化はサポートされません。これらのサポートされていないタイプの指標は、非二項指標または非ベルヌーイ指標とも呼ばれます。

次の指標タイプは、主要目標指標としてサポートされていません。

* [!DNL Adobe Target] エンゲージメントと売上高の指標
* [!DNL Adobe Analytics] エンゲージメントと売上高の指標

   [!DNL Analytics]は[!DNL Analytics]からすべてのエンゲージメント指標と売上高指標を識別および除外できないので、[!DNL Target]エンゲージメント指標または売上高指標を主目標指標として選択できる場合があります。 [!DNL Analytics]から2項コンバージョン指標またはカスタムイベントのみを選択する場合は注意してください。

* [!DNL Adobe Analytics] 計算指標

## 制限事項とメモ

[!UICONTROL 自動配分]と[!UICONTROL 自動ターゲット]の両方のアクティビティには、いくつかの制限と注意事項が適用されます。 その他の制限や注意事項は、1つのアクティビティタイプまたは他のタイプに適用されます。

### 自動配分と自動ターゲット

* アクティビティがアクティブ化された後、レポートソースを[!DNL Analytics]から[!DNL Target]に変更したり、その逆を変更したりすることはできません。
* 計算指標は主要目標指標としてサポートされていませんが、多くの場合、カスタムイベントを主要目標指標として選択する代わりに、意図した結果を得ることができます。 例えば、「訪問者ごとのフォームの完了」などの指標を最適化する場合は、「フォームの完了」に対応するカスタムイベントを主要目標指標として選択します。 [!DNL Target] トラフィックの偏りを考慮して、訪問あたりのコンバージョン指標を自動的に標準化するので、計算指標を使用して標準化を実行する必要はありません。
* [!DNL Target] は、 [!UICONTROL 自動配分機能で「同じタッチ」アトリビューションモデルを使用し] ます。ターゲットの分析(A4T)。

### 自動配分

* [!UICONTROL 自動] 配分モデルでは、通常どおり、2時間ごとにトレーニングが行われます。

### 自動ターゲット

* [!UICONTROL 自動ター] ゲットモデルでは、通常どおり、24時間ごとにトレーニングが行われます。ただし、[!DNL Analytics]からのコンバージョンイベントデータは、さらに6 ～ 24時間遅れます。 この遅延は、[!DNL Target]によるトラフィックの分配が[!DNL Analytics]に記録された最新のイベントに従うことを意味します。 これは、アクティビティが最初にアクティブ化されてから最初の48時間で最も大きな効果を持ちます。 アクティビティのパフォーマンスは、5日が経過した後の[!DNL Analytics]コンバージョンの動作とより密接に反映されます。 短期間のアクティビティでは、アクティビティの有効期間の最初の5日間にほとんどのトラフィックが発生するので、[!UICONTROL 自動ターゲット]の代わりに[!UICONTROL 自動配分]を使用することをお勧めします。
* [!DNL Analytics]を[!UICONTROL 自動ターゲット]アクティビティのデータソースとして使用する場合、6時間が経過するとセッションは終了したと見なされます。 6時間後に発生したコンバージョンはカウントされません。

詳しくは、*Analyticsツールガイド*&#x200B;の[アトリビューションモデルとルックバックウィンドウ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html)を参照してください。
