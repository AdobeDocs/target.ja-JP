---
keywords: a4t;A4T;Target のレポートソースとしての Analytics;Target のための Analytics
description: レポートソース（A4T）として [!UICONTROL Auto-Allocate] を使用するアクティビティの作 [!UICONTROL Auto-Target] 方法  [!DNL Target]  よび作  [!DNL Analytics]  方法を説明します。
title: A4T は [!UICONTROL Auto-Allocate] アクティビティと [!UICONTROL Auto-Target] アクティビティをサポートしていますか？
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
source-git-commit: ddced04c730519dae74e70a60bed26462825ad23
workflow-type: tm+mt
source-wordcount: '1276'
ht-degree: 9%

---

# [!UICONTROL Auto-Allocate] アクティビティと [!UICONTROL Auto-Target] アクティビティに対する A4T のサポート

[!DNL Adobe Target]Analytics for Target[!DNL Adobe Analytics] （A4T）と呼ばれる [ 対 ](/help/main/c-integrating-target-with-mac/a4t/a4t.md) の統合では、[!UICONTROL Auto-Allocate] アクティビティと [!UICONTROL Auto-Target] アクティビティをサポートしています。

A4T 統合により、次のことが可能になります。

* [ 自動割り当て ](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) マルチアームバンディット機能を使用して、勝者エクスペリエンスへとトラフィックを促します。
* [ 自動ターゲット ](/help/main/c-activities/auto-target/auto-target-to-optimize.md) アンサンブル機械学習アルゴリズムを使用して、各訪問者に最適なエクスペリエンスを選択します。 [!UICONTROL Auto-Target] は、各ユーザーのプロファイル、行動およびコンテキストに基づいて最適なエクスペリエンスを選択すると同時に、[!DNL Adobe Analytics] しい目標指標や、[!DNL Adobe Analytics] の豊富なレポートおよび分析機能を使用します。

[A/B テストおよびエクスペリエンスのターゲティングアクティビティで使用するために A4T を実装 ](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md) したことを確認します。 `analyticsLogging = client_side` を使用する場合は、`sessionId` 値も [!DNL Analytics] に渡す必要があります。 詳しくは、[Adobe Target開発者ガイド ](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/integration/a4t-reporting.html){target=_blank} の *Analytics for Target （A4T）レポート* を参照してください。

開始するには

1. [[!UICONTROL A/B Test] アクティビティの作成 ](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) 中に、**[!UICONTROL Targeting]** ページで **[!UICONTROL Traffic Allocation]** コントロールをクリックし、右側のパネルで目的のトラフィック配分方法を選択します。

   ![ トラフィック配分方法の設定 ](/help/main/c-activities/assets/auto-target.png)

   次のトラフィック割り当て方法を使用できます。

   * **[!UICONTROL Manual (Default)]**：各エクスペリエンスを表示するエントリの割合を指定します。 この割合は、全エクスペリエンス間で均等に配分することも、エクスペリエンスごとに大きく（または小さく）設定することもできます。全エクスペリエンスの合計が 100％になるようにします。

   * **[!UICONTROL Auto-Allocate to best experience]**：ほとんどのアクティビティのエントリは、パフォーマンスの高いエクスペリエンスに自動的に移動します。 一部の訪問者は、エクスペリエンスの調査を継続し、パフォーマンスの傾向の変化を認識するために、すべてのエクスペリエンスに配分されます。詳しくは、[[!UICONTROL Auto-Allocate] の概要 ](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) を参照してください。

   * **[!UICONTROL Auto-Target for personalized experiences]**:[!DNL Target] は、高度な機械学習を使用して、パフォーマンスの高い複数のマーケターが定義したエクスペリエンスを特定し、個々の顧客プロファイルと類似する訪問者の過去の行動に基づいて最適なエクスペリエンスを訪問者に提供することで、コンテンツをパーソナライズし、コンバージョンを促進します。 詳しくは、[ 自動ターゲットの概要 ](/help/main/c-activities/auto-target/auto-target-to-optimize.md) を参照してください。

   詳細と詳しい手順については、[ 自動配分アクティビティの作成 ](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) および [ 自動ターゲットアクティビティの作成 ](/help/main/c-activities/auto-target/create-auto-target.md) を参照してください。

1. **[!UICONTROL Adobe Analytics]** のページで **[!UICONTROL Reporting Source]** ーザーの **[!UICONTROL Goals & Settings]** を選択し、目的の最適化目標に対応する会社とレポートスイートを選択します。

   ![ 目標と設定ページのSourceのレポートの節 ](/help/main/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. トラッキングサーバーとサンドボックスを指定します。

1. [!UICONTROL Primary Goal] の指標を選択します。

   * [!DNL Adobe Target] を使用して最適化目標を指定するには、「**[!UICONTROL Conversion]**」を選択します。
   * 「**[!UICONTROL Use an Analytics metric]**」を選択し、最適化目標として使用する指標を [!DNL Analytics] から選択します。 標準の [!DNL Analytics] コンバージョン指標または [!DNL Analytics] カスタムイベントを使用できます。

   詳しくは、以下の [ サポートされる目標指標 ](#supported) を参照してください。

1. アクティビティを保存してアクティベートします。

   [!UICONTROL Auto-Allocate] は、選択した指標を使用してアクティビティを最適化し、目標指標を最大化するエクスペリエンスを訪問者に提供します。

   または

   [!UICONTROL Auto-Target] は、選択した指標を使用してアクティビティを最適化し、訪問者をパーソナライズされた最適なエクスペリエンスに導きます。

1. 「**[!UICONTROL Reports]**」タブを使用すると、選択した指標に基づいてアクティビティのレポート [!DNL Adobe Analytics] 表示できます。 「**[!UICONTROL View in Analytics]**」をクリックして、レポートデータを深く掘り下げ、さらにセグメント化します。

## サポートされる目標指標 {#supported}

[!UICONTROL A4T] および [!UICONTROL Auto-Allocate] の [!UICONTROL Auto-Target] では、最適化の主な目標指標として、次の指標タイプのいずれかを選択できます。

* [!DNL Adobe Target] のコンバージョン指標
* [!DNL Adobe Analytics] のコンバージョン指標
* [!DNL Adobe Analytics] カスタムイベント

>[!NOTE]
>
>[!UICONTROL Use an Analytics Metric] を選択したら、「[!UICONTROL Maximize Unique Visitor Conversion Rate]」を選択して使用可能な [!DNL Adobe Analytics] コンバージョン指標を表示し、「[!UICONTROL Maximize Metric Value per Visitor]」を選択してカスタムイベント [!DNL Adobe Analytics] 調べます。

[!DNL Target] では、[!UICONTROL Auto-Allocate] および [!UICONTROL Auto-Target] アクティビティ用の [!UICONTROL A4T] を使用すると、二項イベントに基づいて指標を選択したり、継続イベントに基づいて指標を選択したりできます。

* **二項イベントに基づく指標**：二項イベントは、発生しないか、発生しません。 二項イベントには、クリック、コンバージョン、順序などが含まれます。 これらのタイプのイベントは、ベルヌーイ、バイナリ、または個別のイベントとも呼ばれます。

* **連続イベントに基づく指標**。 連続指標には、売上高、注文された製品の数、セッション期間、セッション中のページビューの数などが含まれます。 これらのタイプのイベントは、非二項式または非ベルヌーイ指標とも呼ばれます。

>[!IMPORTANT]
>
>[!DNL Adobe Target Standard/Premium] 22.15.1 リリース（2023 年 3 月 8 日および 9 日（PT））の時点で、[!DNL Target] は、サポートされていない指標（以下の表に示す）で既存のアクティビティを引き続きサポートします。 ただし、2023 年 9 月 9 日（PT）以降、これらの指標は既存のアクティビティでサポートされなくなり、既存のアクティビティを新しい動作に強制的に移行するため、サポートされていない指標を使用しているすべてのアクティビティは廃止されます。

### [!UICONTROL Auto-Allocate] アクティビティへの影響

| 指標名 | 次でサポートされなくなりました。 |
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

### [!UICONTROL Auto-Target] アクティビティへの影響

| 指標名 | 次でサポートされなくなりました。 |
| --- | --- |
| [!UICONTROL cartremovals] | 指標値の最大化 |
| [!UICONTROL pageviews] | 指標値の最大化 |
| [!UICONTROL visitors] | コンバージョン率、指標値の最大化 |
| [!UICONTROL visits] | 指標値の最大化 |

## 制限事項と注意事項

一部の制限事項や注意事項は、[!UICONTROL Auto-Allocate] アクティビティと [!UICONTROL Auto-Target] アクティビティの両方に適用されます。 その他の制限事項や注意事項は、アクティビティタイプとアクティビティタイプのどちらかに適用されます。

### 自動配分と自動ターゲット {#both}

* [!DNL Adobe Analytics] を [!UICONTROL Auto-Allocate] または [!UICONTROL Auto-Target] のレポートソースとして使用する場合、レポートは常に [!DNL Analytics] で表示する必要があります。
* アクティビティがアクティブ化された後に、レポートソースを [!DNL Analytics] から [!DNL Target] に、またはその逆に変更することはできません。
* 計算指標はメイン目標指標としてはサポートされていませんが、多くの場合、カスタム イベントをメイン目標指標として選択することで、意図した結果を得ることができます。 例えば、「訪問者あたりのフォーム完了」などの指標を最適化する場合は、「フォーム完了」に対応するカスタムイベントをメイン目標指標として選択します。 [!DNL Target] では、トラフィック分布の不均等を考慮して、コンバージョン指標を訪問ごとに自動的に正規化するので、正規化を行うのに計算指標を使用する必要はありません。

### 自動配分 {#aa}

* **トレーニング頻度**：通常どおり、[!UICONTROL Auto-Allocate] モデルは 1 時間ごとにトレーニングを続けます。
* **アトリビューションモデル**:[!DNL Target] は、A4T を使用する [!DNL Adobe Analytics] アクティビティに [!UICONTROL &#x200B; Auto-Allocate] のデフォルトのアトリビューションモデルを使用します。
* **信頼性**:[!UICONTROL Auto-Allocate] のアクティビティで使用される信頼性の数式が、[!DNL Adobe Analytics] の [!UICONTROL A4T] ントロールパネルにデフォルトで表示される数式と異なります。 [ ここで説明しているように ](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)、[!UICONTROL Auto-Allocate] では、通常の [!UICONTROL A/B Test] アクティビティよりも保守的な信頼区間を使用します。 これらの保守的な信頼性レベルは、データでの繰り返しの評価（ピーク）を補います。 その結果、[!DNL Adobe Analytics] のデフォルトレポートには、[!UICONTROL Auto-Allocate] アルゴリズムで使用される間隔と比較して、狭い信頼区間が表示されます。 そうは言っても、どのエクスペリエンスがよりユニークな訪問者が送信されているかに基づいて、アルゴリズムによってどのエクスペリエンスが好まれるかを判断できます。
* **勝者のステータス**：現在、[ 「まだ勝者がありません」および「勝者」バッジ ](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) は [!UICONTROL A4T] の [!DNL Analysis Workspace] パネルでは使用できません。 これらのバッジは、同じレポートを [!DNL Target] で表示した場合にも利用できません。A4T を使用する [!DNL Target] アクティビティの [!UICONTROL Auto-Allocate] レポートで表示される勝者の「星」バッジは無視する必要があります。 このバッジは、[!UICONTROL Auto-Allocate] で使用される計算ではなく、通常の信頼性の計算を反映しています。

### 自動ターゲット {#at}

* 通常 [!UICONTROL Auto-Target] 通り、24 時間ごとにトレーニングを行うモデルもいます。 ただし、[!DNL Analytics] からのコンバージョンイベントデータは、6～24 時間余分に遅延します。 この遅延は、[!DNL Target] で記録された最新のイベントを [!DNL Analytics] が追跡することによるトラフィックの分散を意味します。 この遅延は、アクティビティが最初にアクティブ化されてから最初の 48 時間で最も大きな影響を与えます。 アクティビティのパフォーマンスは、5 日経過した後 [!DNL Analytics] コンバージョン動作をより詳細に反映します。

  ほとんどのトラフィックがアクティビティの [!UICONTROL Auto-Allocate] 生から最初の 5 日以内に発生する短期間のアクティビティでは、[!UICONTROL Auto-Target] の代わりに Workfront を使用することを検討します。

* [!DNL Analytics] アクティビティのデータソースとして [!UICONTROL Auto-Target] を使用する場合、6 時間が経過するとセッションは終了します。 6 時間後に発生したコンバージョンはカウントされません。

詳しくは、[Analytics ツールガイド ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) アトリビューションモデルとルックバックウィンドウ *を参照してください*。

## チュートリアル

[!DNL Adobe Analytics] [!UICONTROL Analysis Workspace] には豊富な分析機能が備わっていますが、アクティビティを正しく解釈するには、デフォルトの [!UICONTROL Analytics for Target] パネルにいくつかの変更を加える必要が [!UICONTROL Auto-Allocate] り [!UICONTROL Auto-Target] す。 実験アクティビティ（手動の A/B と [!UICONTROL Auto-Allocate]）とパーソナライゼーションアクティビティ（[!UICONTROL Auto-Target]）の違いにより、これらの変更が必要になります。

### [!DNL Analysis Workspace] での [!UICONTROL Auto-Allocate] アクティビティ用 A4T レポートの設定

このチュートリアルでは、[!UICONTROL Auto-Allocate] での [!DNL Analysis Workspace] アクティビティ分析に推奨される変更について、順番に説明します。

詳しくは、[Adobe Target チュートリアル ](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html?lang=ja){target=_blank}Analysis Workspaceでの自動配分アクティビティに関する A4T レポートの設定 *を参照してください*。

### [!DNL Analysis Workspace] での [!UICONTROL Auto-Target] アクティビティ用 A4T レポートの設定

このチュートリアルでは、[!UICONTROL Auto-Target] での [!DNL Analysis Workspace] アクティビティ分析に推奨される変更について、順番に説明します。

詳しくは、*Adobe Target チュートリアル*&#x200B;の [Analysis Workspace での自動ターゲットアクティビティに関する A4T レポートの設定](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=ja){target=_blank}を参照してください。


