---
keywords: A4T;A4T;Target のレポートソースとしての Analytics;Target の分析
description: 作成方法を学ぶ [!UICONTROL 自動配分] および [!UICONTROL 自動ターゲット] アクティビティ [!DNL Target] を使用 [!DNL Analytics] を使用します (A4T)。
title: A4T は [!UICONTROL 自動配分] および [!UICONTROL 自動ターゲット] アクティビティ？
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
source-git-commit: 99bd509988a7d1545a6a1fe59aa59f35ef0a7d11
workflow-type: tm+mt
source-wordcount: '1271'
ht-degree: 7%

---

# [!UICONTROL 自動配分]と[!UICONTROL 自動ターゲット]アクティビティに対する A4T のサポート

この [!DNL Adobe Target]-to-[!DNL Adobe Analytics] 統合：別名 [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T)、サポート [!UICONTROL 自動配分] および [!UICONTROL 自動ターゲット] アクティビティ。

A4T 統合を使用すると、次のことが可能になります。

* 以下を使用： [自動配分](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) マルチアームバンディット機能を使用して、トラフィックを勝者エクスペリエンスに導くことができます。
* 以下を使用： [自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md) アンサンブルの機械学習アルゴリズムを使用して、各訪問者に最適なエクスペリエンスを選択します。 [!UICONTROL 自動ターゲット] は、 [!DNL Adobe Analytics] の目標指標と豊富なレポートおよび分析機能 [!DNL Adobe Analytics].

次の条件を満たしていることを確認します。 [A/B テストおよびエクスペリエンスのターゲット設定アクティビティで使用するために A4T が実装されました。](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md). 次を使用する場合、 `analyticsLogging = client_side`を使用する場合、 `sessionId` 値 [!DNL Analytics]. 詳しくは、 [Analytics for Target(A4T) レポート](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/integration/a4t-reporting.html){target=_blank} 内 *Adobe Target Developer Guide*.

開始するには

1. While [作成 [!UICONTROL A/B テスト] アクティビティ](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)、 **[!UICONTROL ターゲット設定]** ページで、次のいずれかのオプションを **[!UICONTROL トラフィック配分方法]**:

   * [!UICONTROL 最良のエクスペリエンスに自動配分]
   * [!UICONTROL パーソナライズされたエクスペリエンスの自動ターゲット]

   ![トラフィック配分方法のオプション：手動、自動配分、自動ターゲット](/help/main/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   詳細および詳しい手順については、 [自動配分アクティビティの作成](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) および [自動ターゲットアクティビティの作成](/help/main/c-activities/auto-target/create-auto-target.md).

1. 選択 **[!UICONTROL Adobe Analytics]** の **[!UICONTROL レポートソース]** の **[!UICONTROL 目標と設定]** ページを開き、目的の最適化目標に対応するレポートスイートを選択します。

   ![目標と設定ページのレポートソースセクション](/help/main/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. を選択します。 [!UICONTROL プライマリ目標] 指標。

   * 使用する [!DNL Adobe Target] 最適化目標を指定するには、 **[!UICONTROL コンバージョン]** .
   * 選択 **[!UICONTROL Analytics 指標の使用]** 次に、次の中から指標を選択します。 [!DNL Analytics] を最適化目標として使用します。 標準搭載の [!DNL Analytics] コンバージョン指標または [!DNL Analytics] カスタムイベント。

   詳しくは、 [サポートされる目標指標](#supported) 詳しくは、以下を参照してください。

1. アクティビティを保存してアクティブ化します。

   [!UICONTROL 自動配分] は、選択した指標を使用してアクティビティを最適化し、目標指標を最大化するエクスペリエンスに訪問者を導きます。

   または

   [!UICONTROL 自動ターゲット] は、選択した指標を使用してアクティビティを最適化し、訪問者をパーソナライズされた最高のエクスペリエンスに導きます。

1. 以下を使用： **[!UICONTROL レポート]** タブで、選択した項目別にアクティビティのレポートを表示できます。 [!DNL Adobe Analytics] 指標。 クリック **[!UICONTROL Analytics で表示]** を参照して、レポートデータの詳細を掘り下げ、セグメント化を進めます。

## サポートされる目標指標 {#supported}

[!UICONTROL A4T] 対象 [!UICONTROL 自動配分] および [!UICONTROL 自動ターゲット] 最適化の主な目標指標として、次のいずれかの指標タイプを選択できます。

* [!DNL Adobe Target] コンバージョン指標と考えることができます
* [!DNL Adobe Analytics] コンバージョン指標と考えることができます
* [!DNL Adobe Analytics] つのカスタムイベント

[!DNL Target] では、[!UICONTROL 自動配分]および[!UICONTROL 自動ターゲット]アクティビティ用の [!UICONTROL A4T] を使用すると、二項イベントに基づいて指標を選択したり、連続イベントに基づいて指標を選択したりできます。

* **二項イベントに基づく指標**:2 項イベントは発生しないか、発生しません。 2 項イベントには、クリック、コンバージョン、注文などが含まれます。 この種のイベントは、ベルヌーイ、バイナリ、個別のイベントとも呼ばれます。

* **連続イベントに基づく指標**. 継続的な指標には、売上高、注文された製品数、セッション期間、セッションでのページビュー数などが含まれます。 この種のイベントは、非二項指標や非ベルヌーイ指標とも呼ばれます。

>[!IMPORTANT]
>
>現在 [!DNL Adobe Target Standard/Premium] 22.15.1リリース（2023 年 3 月 9 日）、 [!DNL Target] は、現在サポートされていない指標（以下の表に示す）を使用して、既存のアクティビティを引き続きサポートします。 ただし、2023 年 9 月 10 日以降、これらの指標は既存のアクティビティではサポートされなくなり、サポートされていない指標を使用するすべてのアクティビティは、既存のアクティビティを新しい動作に強制的に移行するために廃止されます。

### 影響 [!UICONTROL 自動配分] アクティビティ

| Metric name | 現在は次のサポートはありません： |
| --- | --- |
| [!UICONTROL averagedepth] | コンバージョン率、指標値を最大化 |
| [!UICONTROL averagetimespentonsite] | コンバージョン率、指標値を最大化 |
| [!UICONTROL 跳ね返る] | コンバージョン率、指標値を最大化 |
| [!UICONTROL bounces] | コンバージョン率、指標値を最大化 |
| [!UICONTROL エントリ] | コンバージョン率、指標値を最大化 |
| [!UICONTROL 出口] | コンバージョン率、指標値を最大化 |
| [!UICONTROL pageviews] | 指標値を最大化 |
| [!UICONTROL リロード] | 指標値を最大化 |
| [!UICONTROL 訪問者数] | コンバージョン率、指標値を最大化 |
| [!UICONTROL 訪問回数] | 指標値を最大化 |

### 影響 [!UICONTROL 自動ターゲット] アクティビティ

| Metric name | 現在は次のサポートはありません： |
| --- | --- |
| [!UICONTROL cartremovals] | 指標値を最大化 |
| [!UICONTROL pageviews] | 指標値を最大化 |
| [!UICONTROL 訪問者数] | コンバージョン率、指標値を最大化 |
| [!UICONTROL 訪問回数] | 指標値を最大化 |

## 制限事項と注意事項

いくつかの制限事項と注意事項は、 [!UICONTROL 自動配分] および [!UICONTROL 自動ターゲット] アクティビティ。 その他の制限事項や注意事項は、1 つのアクティビティタイプまたは他のアクティビティタイプに適用されます。

### 自動配分と自動ターゲット {#both}

* を使用する場合 [!DNL Adobe Analytics] レポートソースとして [!UICONTROL 自動配分] または [!UICONTROL 自動ターゲット]を使用する場合、常に [!DNL Analytics].
* レポートソースを次から変更することはできません： [!DNL Analytics] から [!DNL Target] または、アクティビティがアクティブ化された後のアクティビティ。
* 計算指標は主な目標指標としてサポートされていませんが、多くの場合、カスタムイベントを主な目標指標として選択する代わりに、意図した結果を得ることができます。 例えば、「訪問者ごとのフォームの完了」などの指標を最適化する場合は、「フォームの完了」に対応するカスタムイベントを主な目標指標として選択します。 [!DNL Target] トラフィックの偏在を考慮して、訪問ごとにコンバージョン指標を自動的に正規化するので、計算指標を使用して標準化を実行する必要はありません。

### 自動配分 {#aa}

* **トレーニング頻度**: [!UICONTROL 自動配分] モデルは、通常どおり、1 時間ごとにトレーニングを続けます。
* **アトリビューションモデル**: [!DNL Target] は [!DNL Adobe Analytics] のデフォルト属性モデル[!UICONTROL  自動配分] A4T を使用するアクティビティに関連付けられています。
* **信頼性**:次の条件で使用される信頼性の数式： [!UICONTROL 自動配分] アクティビティは、デフォルトで [!DNL Adobe Analytics] [!UICONTROL A4T] パネル。 [ここで説明するように](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [!UICONTROL 自動配分] 通常よりも控えめな信頼区間を使用する [!UICONTROL A/B テスト] アクティビティ。 この保守的な信頼水準は、データに対する繰り返しの評価（ピーク）を補います。 その結果、 [!DNL Adobe Analytics] は、 [!UICONTROL 自動配分] アルゴリズム。 しかし、どのエクスペリエンスがよりユニークな訪問者を送信しているかに基づいて、アルゴリズムが最適なエクスペリエンスを決定できます。
* **勝者ステータス**:現在、 [「まだ勝者がありません」と「勝者」バッジ](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) は [!UICONTROL A4T] パネル内 [!DNL Analysis Workspace]. 同じレポートが [!DNL Target]. 勝者の「星」バッジが [!DNL Target] レポート [!UICONTROL 自動配分] A4T を使用するアクティビティは無視する必要があります。 このバッジは、通常の信頼性の計算を反映し、 [!UICONTROL 自動配分].

### 自動ターゲット {#at}

* [!UICONTROL 自動ターゲット] モデルは、通常どおり、24 時間ごとにトレーニングを続けます。 ただし、コンバージョンイベントのデータは [!DNL Analytics] は、6～24 時間延長されます。 この遅延は、 [!DNL Target] ～で記録された最新の出来事を追跡する [!DNL Analytics]. この遅延は、アクティビティが最初にアクティブ化されてから最初の 48 時間で最も大きな影響を与えます。 アクティビティのパフォーマンスがより厳密に反映される [!DNL Analytics] 5 日経過後のコンバージョン動作。

   使用を検討 [!UICONTROL 自動配分] の代わりに [!UICONTROL 自動ターゲット] ：アクティビティが存在してから最初の 5 日間にほとんどのトラフィックが発生する、短期間のアクティビティ。

* を使用する場合 [!DNL Analytics] を [!UICONTROL 自動ターゲット] アクティビティ、セッションは 6 時間経過後に終了します。 6 時間後に発生したコンバージョンはカウントされません。

詳しくは、 [アトリビューションモデルとルックバックウィンドウ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) 内 *Analytics ツールガイド*.

## チュートリアル

豊富な分析機能は [!DNL Adobe Analytics] [!UICONTROL Analysis Workspace]( デフォルトの [!UICONTROL Analytics for Target] 正しく解釈するには、パネルが必要です [!UICONTROL 自動配分] および [!UICONTROL 自動ターゲット] アクティビティ。 実験アクティビティ ( 手動の A/B および [!UICONTROL 自動配分]) とパーソナライゼーションアクティビティ ([!UICONTROL 自動ターゲット]) をクリックします。

### [!DNL Analysis Workspace] での[!UICONTROL 自動配分]アクティビティ用 A4T レポートの設定

このチュートリアルでは、分析に推奨される変更について順を追って説明します [!UICONTROL 自動配分] アクティビティ [!DNL Analysis Workspace].

詳しくは、 [自動配分アクティビティ用にAnalysis Workspaceで A4T レポートを設定する方法](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html?lang=ja){target=_blank} in *Adobe TargetTutorials*.

### [!DNL Analysis Workspace] での [!UICONTROL 自動ターゲット]アクティビティ用 A4T レポートの設定

このチュートリアルでは、分析に推奨される変更について順を追って説明します [!UICONTROL 自動ターゲット] アクティビティ [!DNL Analysis Workspace].

詳しくは、 [Analysis Workspace for Auto-Target アクティビティで A4T レポートを設定する方法](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=ja){target=_blank} in *Adobe TargetTutorials*.


