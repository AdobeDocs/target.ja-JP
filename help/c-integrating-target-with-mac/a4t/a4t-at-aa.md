---
keywords: a4t;A4T;Target のレポートソースとしての Analytics
description: Analyticsをレポートソースとして使用するAdobe [!DNL Target] で、自動配分と自動ターゲットアクティビティを作成する方法を説明します(A4T)。
title: A4Tは自動配分と自動ターゲットアクティビティをサポートしますか？
feature: Analytics for Target（A4T）
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
source-git-commit: 103ee22a4bf37569f8a02a91af194ebcdc79f3b4
workflow-type: tm+mt
source-wordcount: '979'
ht-degree: 3%

---

# 自動配分と自動ターゲットアクティビティに対する A4T のサポート

[!DNL Adobe Target]-to-[!DNL Adobe Analytics]統合([Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4t.md)(A4T)と呼ばれる)は、[!UICONTROL 自動配分]および[!UICONTROL 自動ターゲット]アクティビティをサポートします。

A4T統合を使用すると、次のことが可能になります。

* [自動配分](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)のマルチアームバンディット機能を使用して、勝者エクスペリエンスにトラフィックを誘導します。
* [自動ターゲット](/help/c-activities/auto-target/auto-target-to-optimize.md)のアンサンブル機械学習アルゴリズムを使用して、各訪問者に最適なエクスペリエンスを選択します。 自動ターゲットは、[!DNL Adobe Analytics]目標指標と[!DNL Adobe Analytics]の豊富なレポートおよび分析機能を使用しながら、ユーザーのプロファイル、行動およびコンテキストに基づいて最適なエクスペリエンスを選択します。

A/Bテストおよびエクスペリエンスのターゲット設定アクティビティで使用する[A4Tを実装していることを確認してください](/help/c-integrating-target-with-mac/a4t/a4timplementation.md)。 `analyticsLogging = client_side`を使用する場合は、`sessionId`値も[!DNL Analytics]に渡す必要があります。 詳しくは、『*Adobe Target SDK*』ガイドの[Analytics for Target(A4T)レポート](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting)を参照してください。

開始するには

1. A/Bテストアクティビティを作成する際に、**[!UICONTROL ターゲティング]**&#x200B;ページで、「**[!UICONTROL トラフィック配分方法]**」として次のいずれかのオプションを選択します。

   * [!UICONTROL 最良のエクスペリエンスへの自動配分]
   * [!UICONTROL パーソナライズされたエクスペリエンスの自動ターゲット]

   ![トラフィック配分方法のオプション：手動、自動配分、自動ターゲット](/help/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   詳細と手順については、「[自動配分アクティビティの作成](/help/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md)」および「[自動ターゲットアクティビティの作成](/help/c-activities/auto-target/create-auto-target.md)」を参照してください。

1. **[!UICONTROL 目標と設定]**&#x200B;ページで&#x200B;**[!UICONTROL レポートソース]**&#x200B;に対して&#x200B;**[!UICONTROL Adobe Analytics]**&#x200B;を選択し、目的の最適化目標に対応するレポートスイートを選択します。

   ![目標と設定ページのレポートソースセクション](/help/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. 「プライマリ目標」指標を選択します。

   * [!DNL Adobe Target]を使用して最適化目標を指定するには、「 **[!UICONTROL コンバージョン]** 」を選択します。
   * 「**[!UICONTROL Analytics指標]**&#x200B;を使用」を選択し、最適化目標として使用する指標を[!DNL Analytics]から選択します。 標準提供の[!DNL Analytics]コンバージョン指標または[!DNL Analytics]カスタムイベントを使用できます。

   詳しくは、以下の[サポートされる目標指標](#supported)を参照してください。

1. アクティビティを保存してアクティブ化します。

   [!UICONTROL 自動配分で] は、選択した指標を使用してアクティビティを最適化し、目標指標を最大化するエクスペリエンスに訪問者を誘導します。

   または

   [!UICONTROL 自動ターゲッ] トは、選択した指標を使用してアクティビティを最適化し、訪問者をパーソナライズされた最高のエクスペリエンスに誘導します。

1. **[!UICONTROL 「レポート]**」タブを使用して、[!DNL Adobe Analytics]指標を選択して、アクティビティのレポートを表示します。 「**[!UICONTROL Analyticsで表示]**」をクリックして、詳細を調べ、レポートデータをさらにセグメント化します。

## サポートされる目標指標 {#supported}

[!UICONTROL A4] 自動配 [!UICONTROL 分およ] び自動ターゲ  ットの場合は、最適化の主な目標指標として次の指標タイプのいずれかを選択します。

* [!DNL Adobe Target] コンバージョン指標と考えることができます
* [!DNL Adobe Analytics] コンバージョン指標と考えることができます
* [!DNL Adobe Analytics] つのカスタムイベント

[!UICONTROL A4] 自動配 [!UICONTROL 分およ] び自動ターゲ [!UICONTROL ットの場] 合は、2項イベントに基づく指標を選択する必要があります。二項イベントは発生するか、発生しないかのどちらかです。 2項目イベントには、クリック、コンバージョン、注文などが含まれます。 この種のイベントは、ベルヌーイ、バイナリ、個別のイベントとも呼ばれます。

[!UICONTROL A4 ] Tfor Auto-Allocate [!UICONTROL とAuto-Targetは、連続指標の最] 適化  をサポートしていません。連続指標には、売上高、注文された製品数、セッション期間、セッション中のページビュー数などが含まれます。 これらのサポートされないタイプの指標は、非二項指標または非ベルヌーイ指標とも呼ばれます。

次の指標タイプは、主な目標指標としてサポートされません。

* [!DNL Adobe Target] エンゲージメントと売上高の指標
* [!DNL Adobe Analytics] エンゲージメントと売上高の指標

   [!DNL Analytics]では[!DNL Analytics]からすべてのエンゲージメントおよび売上高指標を特定および除外できないので、主な目標指標として[!DNL Target]エンゲージメントまたは売上高指標を選択できます。 [!DNL Analytics]から2項コンバージョン指標またはカスタムイベントのみを選択します。

* [!DNL Adobe Analytics] 計算指標

## 制限事項と注意事項

[!UICONTROL 自動配分]と[!UICONTROL 自動ターゲット]の両方のアクティビティに適用される制限や注意事項があります。 その他の制限事項や注意事項は、1つのアクティビティタイプまたは他のアクティビティタイプに適用されます。

### 自動配分と自動ターゲット

* [!DNL Adobe Analytics]を[!UICONTROL 自動配分]または[!UICONTROL 自動ターゲット]のレポートソースとして使用する場合は、常に[!DNL Analytics]でレポートを表示する必要があります。
* レポートソースは、[!DNL Analytics]から[!DNL Target]に変更することも、アクティビティがアクティブ化された後で逆に変更することもできません。
* 計算指標は主な目標指標としてサポートされていませんが、多くの場合、カスタムイベントを主な目標指標として選択することで、目的の結果を得ることができます。 例えば、「訪問者ごとのフォーム完了」などの指標を最適化する場合は、「フォームの完了」に対応するカスタムイベントを主な目標指標として選択します。 [!DNL Target] は、トラフィックの不均一な配分を考慮して、訪問ごとにコンバージョン指標を自動的に正規化するので、計算指標を使用して正規化を実行する必要はありません。
* [!DNL Target] は、自動配分機能の「同じタッチ」アトリビューションモ [!UICONTROL デルを使] 用します。Analytics for Target(A4T)

### 自動配分

* [!UICONTROL 自動配分] モデルは、通常どおり、2時間ごとにトレーニングを続けます。

### 自動ターゲット

* [!UICONTROL 自動ターゲッ] トモデルは、通常どおり、24時間ごとにトレーニングを継続します。ただし、[!DNL Analytics]からのコンバージョンイベントデータは、追加で6 ～ 24時間遅延します。 この遅延は、[!DNL Target]によるトラフィックの分布が、[!DNL Analytics]に記録された最新のイベントを追跡することを意味します。 この遅延は、アクティビティが最初にアクティブ化されてから最初の48時間で最も大きな影響を与えます。 アクティビティのパフォーマンスは、5日が経過した後のコンバージョン動作をより厳密に反映します。[!DNL Analytics] アクティビティの生後5日以内にほとんどのトラフィックが発生する短期間のアクティビティでは、[!UICONTROL 自動ターゲット]の代わりに[!UICONTROL 自動配分]を使用することを検討します。
* [!DNL Analytics]を[!UICONTROL 自動ターゲット]アクティビティのデータソースとして使用する場合、セッションは6時間経過後に終了します。 6時間後に発生したコンバージョンはカウントされません。

詳しくは、『*Analyticsツールガイド*』の[アトリビューションモデルとルックバックウィンドウ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html)を参照してください。

## チュートリアル：Analysis Workspace for Auto-TargetアクティビティでA4Tレポートを設定する方法 {#tutorial}

[!DNL Adobe Analytics] [!UICONTROL Analysis Workspace]ではリッチな分析機能を利用できますが、自動ターゲットアクティビティを正しく解釈するには、デフォルトの[!UICONTROL Targetの分析]パネルを少し変更する必要があります。 実験アクティビティ（手動のA/Bと[!UICONTROL 自動配分]）とパーソナライゼーションアクティビティ（[!UICONTROL 自動ターゲット]）の違いにより、これらの変更が必要になります。

このチュートリアルでは、[!UICONTROL Workspace]の[!UICONTROL 自動ターゲット]アクティビティを分析するための推奨される変更について説明します。

詳しくは、*Adobe TargetTutorials*&#x200B;の「Analysis Workspace for Auto-Targetアクティビティ](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html)でA4Tレポートを設定する方法」を参照してください。[
