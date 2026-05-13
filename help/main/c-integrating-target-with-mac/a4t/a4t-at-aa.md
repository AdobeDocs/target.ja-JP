---
keywords: a4t;A4T;TargetのレポートソースとしてのAnalytics;TargetのAnalytics
description: ' [!DNL Analytics] をレポートソース （A4T）として使用する [!DNL Target] で[!UICONTROL Auto-Allocate]および[!UICONTROL Auto-Target] アクティビティを作成する方法について説明します。'
title: A4Tは[!UICONTROL Auto-Allocate]と[!UICONTROL Auto-Target]のアクティビティをサポートしていますか？
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
TQID: https://experienceleague.adobe.com/VVbjMp7jYDyslZ8ubn8ntPufLK8nKGI9k3ZGh1DLWWs
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: c93393a4-e558-47e1-992e-c91ed4d480ceid: f7c7de77-382f-4f48-8b36-61a170f06d3d
subfeature_v2: id: df62f171-ac37-440f-8f0f-f41a72ebdd34
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bcc5edb5-84c3-4940-9f84-ed88b6c16274id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: e0eb8757-182f-49f3-94a4-1587d16f5094id: eb30f47f-d87a-400f-8f78-63ce7979ff56id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1352
ht-degree: 11%

---

# [!UICONTROL Auto-Allocate]および[!UICONTROL Auto-Target] アクティビティに対するA4T サポート

[!DNL Adobe Target]から[!DNL Adobe Analytics]への統合は、[Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) （A4T）と呼ばれ、[!UICONTROL Auto-Allocate]と[!UICONTROL Auto-Target]のアクティビティをサポートしています。

A4T統合では、次のことが可能になります。

* [自動割り当て](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) マルチアームドバンディット機能を使用して、トラフィックを勝者エクスペリエンスに誘導します。
* [自動ターゲット ](/help/main/c-activities/auto-target/auto-target-to-optimize.md) アンサンブルマシンラーニングアルゴリズムを使用して、各訪問者に最適なエクスペリエンスを選択します。 [!UICONTROL Auto-Target]は、各ユーザーのプロファイル、行動、コンテキストに基づいて最適なエクスペリエンスを選択します。また、[!DNL Adobe Analytics]の目標指標と[!DNL Adobe Analytics]の豊富なレポートおよび分析機能を使用します。

A/B テストおよびエクスペリエンスのターゲット設定アクティビティで使用する[A4Tが実装されていることを確認してください](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md)。 `analyticsLogging = client_side`を使用する場合は、`sessionId`の値を[!DNL Analytics]にも渡す必要があります。 詳しくは、*Adobe Target開発者ガイド*&#x200B;の「[Analytics for Target （A4T） レポート ](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/integration/a4t-reporting.html){target=_blank}」を参照してください。

開始するには

1. [ アクティビティ [!UICONTROL A/B Test]を作成している間、**[!UICONTROL Targeting]** ページで&#x200B;**[!UICONTROL Traffic Allocation]** コントロールをクリックし、右側のペインで目的のトラフィック割り当て方法を選択します。](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)

   ![ トラフィック配分メソッドの設定](/help/main/c-activities/assets/auto-target.png)

   次のトラフィック割り当て方法を使用できます。

   * **[!UICONTROL Manual (Default)]**：各エクスペリエンスを表示する参加者の割合を指定します。 この割合は、全エクスペリエンス間で均等に配分することも、エクスペリエンスごとに大きく（または小さく）設定することもできます。 全エクスペリエンスの合計が 100％になるようにします。

   * **[!UICONTROL Auto-Allocate to best experience]**：ほとんどのアクティビティ参加者は、パフォーマンスの高いエクスペリエンスに自動的に送信されます。 一部の訪問者は、エクスペリエンスの調査を継続し、パフォーマンスの傾向の変化を認識するために、すべてのエクスペリエンスに配分されます。 詳しくは、[[!UICONTROL Auto-Allocate]の概要](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)を参照してください。

   * **[!UICONTROL Auto-Target for personalized experiences]**: [!DNL Target]は、高度な機械学習を使用して、コンテンツをパーソナライズし、コンバージョンを促進します。複数のパフォーマンスの高い、マーケターが定義したエクスペリエンスを特定し、個々の顧客プロファイルと類似する訪問者の過去の行動に基づいて、訪問者に最もカスタマイズされたエクスペリエンスを提供します。 詳しくは、[自動ターゲットの概要](/help/main/c-activities/auto-target/auto-target-to-optimize.md)を参照してください。

   詳細と手順の説明については、[自動配分アクティビティの作成](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md)および[自動ターゲットアクティビティの作成](/help/main/c-activities/auto-target/create-auto-target.md)を参照してください。

1. **[!UICONTROL Goals & Settings]** ページの&#x200B;**[!UICONTROL Reporting Source]**&#x200B;の&#x200B;**[!UICONTROL Adobe Analytics]**&#x200B;を選択し、目的の最適化目標に対応する会社とレポートスイートを選択します。

   ![目標と設定ページのSource セクションを報告](/help/main/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. トラッキングサーバーとサンドボックスを指定します。

1. [!UICONTROL Primary Goal]指標を選択してください。

   * [!DNL Adobe Target]を使用して最適化目標を指定するには、**[!UICONTROL Conversion]**&#x200B;を選択します。
   * **[!UICONTROL Use an Analytics metric]**&#x200B;を選択し、[!DNL Analytics]から指標を選択して、最適化目標として使用します。 標準の[!DNL Analytics] コンバージョン指標または[!DNL Analytics] カスタムイベントを使用できます。

   詳しくは、以下の「[ サポートされている目標指標](#supported)」を参照してください。

1. アクティビティを保存してアクティブ化します。

   [!UICONTROL Auto-Allocate]は、選択した指標を使用してアクティビティを最適化し、訪問者を目標指標を最大化するエクスペリエンスに誘導します。

   または

   [!UICONTROL Auto-Target]は、選択した指標を使用してアクティビティを最適化し、訪問者をパーソナライズされた最高の体験に誘導します。

1. **[!UICONTROL Reports]** タブを使用して、[!DNL Adobe Analytics]指標を選択したアクティビティのレポートを表示します。 **[!UICONTROL View in Analytics]**&#x200B;をクリックして、レポート データをさらに深く掘り下げてセグメント化します。

## サポートされている目標指標 {#supported}

[!UICONTROL Auto-Allocate]および[!UICONTROL Auto-Target]の[!UICONTROL A4T]では、最適化の主な目標指標として、次のいずれかの指標タイプを選択できます。

* [!DNL Adobe Target] コンバージョン指標
* [!DNL Adobe Analytics] コンバージョン指標
* [!DNL Adobe Analytics]個のカスタムイベント

>[!NOTE]
>
>[!UICONTROL Use an Analytics Metric]を選択した後、[!UICONTROL Maximize Unique Visitor Conversion Rate]を選択して利用可能な[!DNL Adobe Analytics]のコンバージョン指標を表示し、[!UICONTROL Maximize Metric Value per Visitor]を選択して[!DNL Adobe Analytics]のカスタムイベントを探索します。

[!DNL Target] では、[!UICONTROL Auto-Allocate] および [!UICONTROL Auto-Target] アクティビティ用の [!UICONTROL A4T] を使用すると、二項イベントに基づいて指標を選択したり、継続イベントに基づいて指標を選択したりできます。

* **二項イベントに基づく指標**：二項イベントは発生するか、発生しません。 二項イベントには、クリック、コンバージョン、注文などが含まれます。 これらの種類のイベントは、ベルヌーイ、バイナリ、または個別のイベントとも呼ばれることもあります。

* **連続イベントに基づく指標**。 継続的な指標には、売上、注文商品数、セッション時間、セッションでのページビュー数などが含まれます。 これらの種類のイベントは、非二項式または非ベルヌーイ指標とも呼ばれることもあります。

>[!IMPORTANT]
>
>[!DNL Adobe Target Standard/Premium] 22.15.1 リリース（2023年3月8日および9日）の時点で、[!DNL Target]は、現在サポートされていない指標（次の表に示す）で既存のアクティビティを引き続きサポートします。 ただし、2023年9月9日以降、これらの指標は既存のアクティビティではサポートされなくなり、サポートされていない指標を使用するすべてのアクティビティは廃止され、既存のアクティビティを新しい動作に強制的に移行する必要があります。

### [!UICONTROL Auto-Allocate]件のアクティビティへの影響

| 指標名 | でサポートされなくなりました： |
| --- | --- |
| [!UICONTROL averagepagedepth] | コンバージョン率、指標値の最大化 |
| [!UICONTROL averagetimespentonsite] | コンバージョン率、指標値の最大化 |
| [!UICONTROL bouncerate] | コンバージョン率、指標値の最大化 |
| [!UICONTROL bounces] | コンバージョン率、指標値の最大化 |
| [!UICONTROL entries] | コンバージョン率、指標値の最大化 |
| [!UICONTROL exits] | コンバージョン率、指標値の最大化 |
| [!UICONTROL pageviews] | 指標値の最大化 |
| [!UICONTROL reloads] | 指標値の最大化 |
| [!UICONTROL visitors] | コンバージョン率、指標値の最大化 |
| [!UICONTROL visits] | 指標値の最大化 |

### [!UICONTROL Auto-Target]件のアクティビティへの影響

| 指標名 | でサポートされなくなりました： |
| --- | --- |
| [!UICONTROL cartremovals] | 指標値の最大化 |
| [!UICONTROL pageviews] | 指標値の最大化 |
| [!UICONTROL visitors] | コンバージョン率、指標値の最大化 |
| [!UICONTROL visits] | 指標値の最大化 |

## 制限事項とメモ

一部の制限とメモは、[!UICONTROL Auto-Allocate]と[!UICONTROL Auto-Target]の両方のアクティビティに適用されます。 その他の制限事項や注意は、どちらかのアクティビティタイプに適用されます。

### 自動配分と自動ターゲット {#both}

* [!DNL Adobe Analytics]を[!UICONTROL Auto-Allocate]または[!UICONTROL Auto-Target]のレポートソースとして使用する場合は、常に[!DNL Analytics]でレポートを表示する必要があります。
* アクティビティがアクティブ化された後、レポートソースを[!DNL Analytics]から[!DNL Target]へ、またはその逆に変更することはできません。
* 計算指標は主要な目標指標としてサポートされていませんが、主な目標指標としてカスタムイベントを選択することで、意図した結果を達成できることがよくあります。 例えば、「訪問者あたりのフォーム完了数」などの指標を最適化する場合は、主要な目標指標として「フォーム完了数」に対応するカスタムイベントを選択します。 [!DNL Target]は、訪問単位でコンバージョン指標を自動的に正規化し、トラフィック配分の不均等を考慮します。そのため、計算指標を使用して正規化を実行する必要はありません。

### 自動配分 {#aa}

* **トレーニング頻度**: [!UICONTROL Auto-Allocate]のモデルは、通常どおり1時間ごとにトレーニングを続けます。
* **アトリビューションモデル**: [!DNL Target]は、A4Tを使用する[!UICONTROL  Auto-Allocate] アクティビティに[!DNL Adobe Analytics]のデフォルトのアトリビューションモデルを使用します。
* **信頼性**: [!UICONTROL Auto-Allocate] アクティビティで使用される信頼式が、[!DNL Adobe Analytics] [!UICONTROL A4T] パネルにデフォルトで表示される式と異なります。 [ここで説明しているように、](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)、[!UICONTROL Auto-Allocate]は、通常の[!UICONTROL A/B Test] アクティビティよりも保守的な信頼区間を使用します。 これらの保守的な信頼性レベルは、データの繰り返し評価（ピーク）を補償します。 その結果、[!DNL Adobe Analytics]のデフォルト レポートでは、[!UICONTROL Auto-Allocate] アルゴリズムで使用されている間隔と比較して、信頼区間が狭くなっています。 しかし、どのエクスペリエンスがよりユニークな訪問者を送るかにもとづいて、アルゴリズムがどのエクスペリエンスを好むかを判断することができます。
* **勝者ステータス**：現在、[ 「まだ勝者なし」および「勝者」バッジ ](/help/main/c-activities/automated-traffic-allocation/determine-winner.md)は、[!DNL Analysis Workspace]の[!UICONTROL A4T] パネルでは使用できません。 これらのバッジは、同じレポートを [!DNL Target] で表示した場合にも利用できません。 A4Tを使用する[!UICONTROL Auto-Allocate] アクティビティの[!DNL Target] レポートに表示される勝者「星」バッジは無視する必要があります。 このバッジは、通常の信頼計算を反映しており、[!UICONTROL Auto-Allocate]が使用する計算を反映していません。

### 自動ターゲット {#at}

* [!UICONTROL Auto-Target]個のモデルは、通常どおり24時間ごとにトレーニングを続けます。 ただし、[!DNL Analytics]からのコンバージョンイベントデータは、さらに6～24時間遅れます。 この遅延は、[!DNL Target]によるトラフィックの配分が、[!DNL Analytics]で記録された最新のイベントを追跡することを意味します。 この遅延は、アクティビティが最初にアクティブ化されてから最初の48時間で最も大きな影響を及ぼします。 アクティビティのパフォーマンスは、5日間が経過した後の[!DNL Analytics]のコンバージョン行動をより密接に反映します。

  アクティビティの有効期間の最初の5日以内に最も多くのトラフィックが発生する短期間のアクティビティには、[!UICONTROL Auto-Target]ではなく[!UICONTROL Auto-Allocate]を使用することを検討してください。

* [!DNL Analytics]を[!UICONTROL Auto-Target] アクティビティのデータソースとして使用する場合、セッションは6時間後に終了します。 6時間後に発生したコンバージョンはカウントされません。

詳しくは、*分析ツールガイド*&#x200B;の「[ アトリビューションモデルとルックバックウィンドウ ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html)」を参照してください。

## チュートリアル

[!DNL Adobe Analytics] [!UICONTROL Analysis Workspace]で豊富な分析機能を利用できますが、[!UICONTROL Auto-Allocate]と[!UICONTROL Auto-Target]のアクティビティを正しく解釈するには、デフォルトの[!UICONTROL Analytics for Target] パネルを少し変更する必要があります。 これらの変更は、実験アクティビティ （手動A/Bと[!UICONTROL Auto-Allocate]）とパーソナライゼーションアクティビティ （[!UICONTROL Auto-Target]）の違いにより必要です。

### [!DNL Analysis Workspace] での [!UICONTROL Auto-Allocate] アクティビティ用 A4T レポートの設定

このチュートリアルでは、[!DNL Analysis Workspace]の[!UICONTROL Auto-Allocate] アクティビティを分析するために推奨される変更について説明します。

詳しくは、*Adobe Target チュートリアル*&#x200B;の「[自動割り当てアクティビティ用にAnalysis WorkspaceでA4T レポートを設定する方法](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html?lang=ja){target=_blank}」を参照してください。

### [!DNL Analysis Workspace] での [!UICONTROL Auto-Target] アクティビティ用 A4T レポートの設定

このチュートリアルでは、[!DNL Analysis Workspace]の[!UICONTROL Auto-Target] アクティビティを分析するために推奨される変更について説明します。

詳しくは、*Adobe Target チュートリアル*&#x200B;の [Analysis Workspace での自動ターゲットアクティビティに関する A4T レポートの設定](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=ja){target=_blank}を参照してください。


