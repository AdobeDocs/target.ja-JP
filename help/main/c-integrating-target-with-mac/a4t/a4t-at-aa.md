---
keywords: a4t;A4T;Target のレポートソースとしての Analytics
description: 自動配分と自動ターゲットアクティビティをAdobeで作成する方法を説明します [!DNL Target] レポートソースとして Analytics を使用する (A4T)
title: A4T は自動配分と自動ターゲットアクティビティをサポートしますか？
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1243'
ht-degree: 4%

---

# 自動配分と自動ターゲットアクティビティに対する A4T のサポート

この [!DNL Adobe Target]-to-[!DNL Adobe Analytics] 統合：別名 [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) サポート [!UICONTROL 自動配分] および [!UICONTROL 自動ターゲット] アクティビティ。

A4T 統合を使用すると、次のことが可能になります。

* 用途 [自動配分](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)のマルチアームバンディット機能を使用して、トラフィックを勝者エクスペリエンスに導くことができます。
* 用途 [自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md)のアンサンブル機械学習アルゴリズムを使用して、各訪問者に最適なエクスペリエンスを選択できます。 自動ターゲットは、 [!DNL Adobe Analytics] 目標指標と [!DNL Adobe Analytics]「豊富なレポートおよび分析機能」を参照してください。

次の条件を満たしていることを確認します。 [A/B テストおよびエクスペリエンスのターゲット設定アクティビティで使用するために A4T が実装されました。](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md). 次を使用する場合： `analyticsLogging = client_side`を使用する場合、 `sessionId` 値 [!DNL Analytics]. 詳しくは、 [Analytics for Target(A4T) レポート](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting) 内 *Adobe Target SDK* ガイド。

開始するには

1. A/B テストアクティビティの作成時、 **[!UICONTROL ターゲット設定]** ページで、次のいずれかのオプションを **[!UICONTROL トラフィック配分方法]**:

   * [!UICONTROL 最良のエクスペリエンスに自動配分]
   * [!UICONTROL パーソナライズされたエクスペリエンスの自動ターゲット]

   ![トラフィック配分方法のオプション：手動、自動配分、自動ターゲット](/help/main/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   詳細および詳しい手順については、 [自動配分アクティビティの作成](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) および [自動ターゲットアクティビティの作成](/help/main/c-activities/auto-target/create-auto-target.md).

1. 選択 **[!UICONTROL Adobe Analytics]** の **[!UICONTROL レポートソース]** の **[!UICONTROL 目標と設定]** ページを開き、目的の最適化目標に対応するレポートスイートを選択します。

   ![目標と設定ページのレポートソースセクション](/help/main/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. 目標指標をプライマリします。

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

[!UICONTROL A4T] 対象 [!UICONTROL 自動配分] および [!UICONTROL 自動ターゲット] では、2 項イベントに基づく指標を選択する必要があります。 2 項イベントは発生しないか、発生しません。 2 項イベントには、クリック、コンバージョン、注文などが含まれます。 この種のイベントは、ベルヌーイ、バイナリ、個別のイベントとも呼ばれます。

[!UICONTROL A4T] 対象 [!UICONTROL 自動配分] および [!UICONTROL 自動ターゲット] は、連続指標の最適化をサポートしていません。 継続的な指標には、売上高、注文された製品数、セッション期間、セッションでのページビュー数などが含まれます。 サポートされていないタイプの指標は、非二項指標や非ベルヌーイ指標とも呼ばれます。

次の指標タイプは、主な目標指標としてサポートされていません。

* [!DNL Adobe Target] エンゲージメントと売上高の指標
* [!DNL Adobe Analytics] エンゲージメントと売上高の指標

   次の項目を選択できます。 [!DNL Analytics] 主な目標指標としてのエンゲージメントまたは売上高指標： [!DNL Target] すべてのエンゲージメントと売上高の指標を特定および除外できない [!DNL Analytics]. 2 次元のコンバージョン指標またはカスタムイベントのみを選択します： [!DNL Analytics].

* [!DNL Adobe Analytics] 計算指標

## 制限事項と注意事項

いくつかの制限事項と注意事項は、 [!UICONTROL 自動配分] および [!UICONTROL 自動ターゲット] アクティビティ。 その他の制限事項や注意事項は、1 つのアクティビティタイプまたは他のアクティビティタイプに適用されます。

### 自動配分と自動ターゲット {#both}

* を使用する場合 [!DNL Adobe Analytics] レポートソースとして [!UICONTROL 自動配分] または [!UICONTROL 自動ターゲット]を使用する場合、常に [!DNL Analytics].
* レポートソースを次から変更することはできません： [!DNL Analytics] から [!DNL Target] または、アクティビティがアクティブ化された後に反対に実行されます。
* 計算指標は主な目標指標としてサポートされていませんが、多くの場合、カスタムイベントを主な目標指標として選択する代わりに、意図した結果を得ることができます。 例えば、「訪問者ごとのフォームの完了」などの指標を最適化する場合は、「フォームの完了」に対応するカスタムイベントを主な目標指標として選択します。 [!DNL Target] トラフィックの偏在を考慮して、訪問ごとにコンバージョン指標を自動的に正規化するので、計算指標を使用して標準化を実行する必要はありません。
* を使用する場合 [!DNL Adobe Analytics] レポートソースとして [!UICONTROL 自動配分] または [!UICONTROL 自動ターゲット] アクティビティの [!DNL Analytics].
* レポートソースを次から変更することはできません： [!DNL Analytics] から [!DNL Target] または、アクティビティがアクティブ化された後のアクティビティ。
* 計算指標は主な目標指標としてサポートされていませんが、多くの場合、カスタムイベントを主な目標指標として選択する代わりに、意図した結果を得ることができます。 例えば、「訪問者ごとのフォームの完了」などの指標を最適化する場合は、「フォームの完了」に対応するカスタムイベントを主な目標指標として選択します。 [!DNL Target] 訪問者ごとにコンバージョン指標を自動的に標準化し、 [!UICONTROL 自動配分] アクティビティの作成時に使用する必要があるので、計算指標を使用して正規化を実行する必要はありません。

### 自動配分 {#aa}

* **トレーニング頻度**: [!UICONTROL 自動配分] モデルは、通常どおり、1 時間ごとにトレーニングを続けます。
* **アトリビューションモデル**: [!DNL Target] は [!DNL Adobe Analytics] のデフォルト属性モデル[!UICONTROL  自動配分] A4T を使用するアクティビティに関連付けられています。
* **信頼性**:次の条件で使用される信頼性の数式： [!UICONTROL 自動配分] アクティビティが、 [!DNL Adobe Analytics] [!UICONTROL A4T] パネル。 [ここで説明するように](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [!UICONTROL 自動配分] 通常よりも控えめな信頼区間を使用する [!UICONTROL A/B テスト] アクティビティ。 この保守的な信頼水準は、データに対する繰り返しの評価（ピーク）を補います。 その結果、 [!DNL Adobe Analytics] は、 [!UICONTROL 自動配分] アルゴリズム。 しかし、どのエクスペリエンスがよりユニークな訪問者を送信しているかに基づいて、アルゴリズムが最適なエクスペリエンスを決定できます。
* **勝者ステータス**:現在、 [「まだ勝者がありません」と「勝者」バッジ](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) は [!UICONTROL A4T] パネル内 [!DNL Analysis Workspace]. 同じレポートが [!DNL Target]. 勝者の「星」バッジが [!DNL Target] レポート [!UICONTROL 自動配分] A4T を使用するアクティビティは無視する必要があります。 このバッジは、通常の信頼性の計算を反映し、 [!UICONTROL 自動配分].

### 自動ターゲット {#at}

* [!UICONTROL 自動ターゲット] モデルは、通常どおり、24 時間ごとにトレーニングを続けます。 ただし、コンバージョンイベントのデータは [!DNL Analytics] は、6～24 時間延長されます。 この遅延は、 [!DNL Target] ～で記録された最新の出来事を追跡する [!DNL Analytics]. この遅延は、アクティビティが最初にアクティブ化されてから最初の 48 時間で最も大きな影響を与えます。 アクティビティのパフォーマンスがより密接に反映されます [!DNL Analytics] 5 日経過後のコンバージョン動作。 使用を検討 [!UICONTROL 自動配分] の代わりに [!UICONTROL 自動ターゲット] ：アクティビティが存在してから最初の 5 日間にほとんどのトラフィックが発生する、短期間のアクティビティ。
* を使用する場合 [!DNL Analytics] を [!UICONTROL 自動ターゲット] アクティビティ、セッションは 6 時間経過後に終了します。 6 時間後に発生したコンバージョンはカウントされません。

詳しくは、 [アトリビューションモデルとルックバックウィンドウ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) 内 *Analytics ツールガイド*.

## チュートリアル：Analysis Workspace for Auto-Target アクティビティで A4T レポートを設定する方法 {#tutorial}

豊富な分析機能は [!DNL Adobe Analytics] [!UICONTROL Analysis Workspace]( デフォルトの [!UICONTROL Analytics for Target] パネルが必要です。 実験アクティビティ ( 手動の A/B および [!UICONTROL 自動配分]) とパーソナライゼーションアクティビティ ([!UICONTROL 自動ターゲット]) をクリックします。

このチュートリアルでは、分析に推奨される変更について順を追って説明します [!UICONTROL 自動ターゲット] アクティビティ [!UICONTROL Workspace].

詳しくは、*Adobe Target チュートリアル*&#x200B;の [Analysis Workspace での自動ターゲットアクティビティに関する A4T レポートの設定](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=ja)を参照してください。
