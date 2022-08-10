---
keywords: a4t;A4T;Target のレポートソースとしての Analytics
description: 自動配分と自動ターゲットアクティビティをAdobeで作成する方法を説明します [!DNL Target] レポートソースとして Analytics を使用する (A4T)
title: A4T は自動配分と自動ターゲットアクティビティをサポートしますか？
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
source-git-commit: e8fc28ef2497c1dfea523a769c9c817cbd74fea2
workflow-type: tm+mt
source-wordcount: '1695'
ht-degree: 5%

---

# 自動配分と自動ターゲットアクティビティに対する A4T のサポート

この [!DNL Adobe Target]-to-[!DNL Adobe Analytics] 統合：別名 [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) サポート [!UICONTROL 自動配分] および [!UICONTROL 自動ターゲット] アクティビティ。

A4T 統合を使用すると、次のことが可能になります。

* 用途 [自動配分](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)のマルチアームバンディット機能を使用して、トラフィックを勝者エクスペリエンスに導くことができます。
* 用途 [自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md)のアンサンブル機械学習アルゴリズムを使用して、各訪問者に最適なエクスペリエンスを選択できます。 自動ターゲットは、 [!DNL Adobe Analytics] 目標指標と [!DNL Adobe Analytics]「豊富なレポートおよび分析機能」を参照してください。

次の条件を満たしていることを確認します。 [A/B テストおよびエクスペリエンスのターゲット設定アクティビティで使用するために A4T が実装されました。](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md). 次を使用する場合： `analyticsLogging = client_side`を使用する場合、 `sessionId` 値 [!DNL Analytics]. 詳しくは、 [Analytics for Target(A4T) レポート](https://developer.adobe.com/target/implement/server-side/sdk-guides/integration-with-experience-cloud/a4t-reporting/){target=_blank} *Adobe Target SDK* ガイド。

開始するには

1. A/B テストアクティビティの作成時、 **[!UICONTROL ターゲット設定]** ページで、次のいずれかのオプションを **[!UICONTROL トラフィック配分方法]**:

   * [!UICONTROL 最良のエクスペリエンスに自動配分]
   * [!UICONTROL パーソナライズされたエクスペリエンスの自動ターゲット]

   ![トラフィック配分方法のオプション：手動、自動配分、自動ターゲット](/help/main/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   詳細および詳しい手順については、 [自動配分アクティビティの作成](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) および [自動ターゲットアクティビティの作成](/help/main/c-activities/auto-target/create-auto-target.md).

1. 選択 **[!UICONTROL Adobe Analytics]** の **[!UICONTROL レポートソース]** の **[!UICONTROL 目標と設定]** ページを開き、目的の最適化目標に対応するレポートスイートを選択します。

   ![目標と設定ページのレポートソースセクション](/help/main/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. 目標指標をプライマリします。 最初のドロップダウンでは、 [!DNL Adobe Target] ( これは [!DNL Adobe Analytics] を参照 )、または [!DNL Analytics] 指標を目標として追加します。

   * 使用する [!DNL Adobe Target] 最適化目標を指定するには、 **[!UICONTROL コンバージョン]**&#x200B;をクリックしてから、コンバージョンの目標に達したことを示すためにオーディエンスが実行する必要があるアクションを指定します。
   * 代わりにを選択する場合は、 **[!UICONTROL Analytics 指標の使用]**&#x200B;を使用する場合、使用する最適化条件のタイプを選択できます。  詳しくは、 [サポートされる目標指標と最適化条件](#supported) 詳しくは、以下を参照してください。 最適化基準を指定した後、互換性のある指標を [!DNL Analytics] を最適化目標として使用します。 標準搭載の [!DNL Analytics] コンバージョン指標または [!DNL Analytics] カスタムイベント。


1. アクティビティを保存してアクティブ化します。

   [!UICONTROL 自動配分] は、選択した指標を使用してアクティビティを最適化し、目標指標を最大化するエクスペリエンスに訪問者を導きます。

   または

   [!UICONTROL 自動ターゲット] は、選択した指標を使用してアクティビティを最適化し、訪問者をパーソナライズされた最高のエクスペリエンスに導きます。

1. 以下を使用： **[!UICONTROL レポート]** タブでアクティビティのレポートを表示し、 **[!UICONTROL Analytics で表示]** Adobe Analytics Workspace でレポートデータの詳細を掘り下げ、セグメント化をおこないます。 以下のチュートリアルに従って、Workspace でのレポートの設定方法を確認できます。
* 自動配分：参照 [自動配分アクティビティ用にAnalysis Workspaceで A4T レポートを設定する方法](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=ja) in *Adobe TargetTutorials*
* 自動ターゲット：参照 [Analysis Workspace for Auto-Target アクティビティで A4T レポートを設定する方法](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) in *Adobe TargetTutorials*.

## サポートされる目標指標と最適化条件 {#supported}

[!UICONTROL A4T] 対象 [!UICONTROL 自動配分] および [!UICONTROL 自動ターゲット] 最適化の主な目標指標として、次のいずれかの指標タイプを選択できます。

* [!DNL Adobe Target] コンバージョン指標と考えることができます
* [!DNL Adobe Analytics] コンバージョン指標と考えることができます
* [!DNL Adobe Analytics] つのカスタムイベント

しかし、 [!UICONTROL 自動配分] および [!UICONTROL 自動ターゲット] モデルは最適化されます **正規化** アクティビティのタイプに応じた正確な正規化を含む、これらの指標のバージョン。 次の表に、アクティビティの各タイプの最適化条件のオプションを示します。

| アクティビティタイプ | 指標のソース | 最適化基準 | 説明 |
|---------------|---------------|-----------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 自動配分 | Analytics | 個別訪問者コンバージョン率の最大化 | モデルは、ユニーク訪問者コンバージョン率が最も高いエクスペリエンスを見つけようとします。これは、Analytics の指標がゼロ以外の訪問者の数を、そのエクスペリエンスを受け取った訪問者の総数で割った値です。 つまり、この指標は、アクティビティの個別訪問者ごとに 0 または 1 のバイナリとして扱われます。   特定のアクションを実行するユーザーのごく一部のみを考慮する場合、または 1 人のユーザーに対して複数のコンバージョンイベントを使用しても意味がない場合に、このオプションを使用します。 |
| 自動配分 | Analytics | 訪問者あたりの指標値の最大化 | モデルは、訪問者ごとに指標の値が最も大きいエクスペリエンスを検索しようとします。これは、そのエクスペリエンスに触れたすべてのユーザーの指標の合計値を、そのエクスペリエンスを受け取った訪問者の合計数で割った値として定義されます。 つまり、指標は、アクティビティの個別訪問者ごとに任意の値を取ることができます。 例えば、訪問者が複数回コンバージョンした場合、各コンバージョンがカウントされます。  合計売上高などの継続的な指標を最大化したい場合や、1 人のユーザーに対して複数のコンバージョンイベントが複数の意味を持つ場合（複数の注文が 1 つ以上の価値を持つなど）は、このオプションを使用します。 |
| 自動配分 | Target  | （設定不可） | この指標はバイナリとして扱われ、個別訪問者のコンバージョン率が最大化されます。 |
| 自動ターゲット | Analytics | 個別訪問コンバージョン率の最大化 | 自動配分や手動の A/B テストとは異なり、自動ターゲットのパーソナライズされた特性は、訪問者に表示されるエクスペリエンスが新しい訪問のたびに変更される可能性があることを意味します。 次に、適切な率が訪問で正規化されたコンバージョン率となります。この率は、ゼロ以外の指標が記録される訪問の割合として定義されます。 これは、自動ターゲットで最適化されたコンバージョン率です。   自動配分と同様に、コンバージョンが発生する訪問の割合（1 回の訪問で発生する複数のコンバージョンイベントが重要でない場合など）を考慮する場合に、このオプションを選択する必要があります。 |
| 自動ターゲット | Analytics | 訪問あたりの指標値の最大化 | 最適化する指標が連続的な場合（売上高など）、または 1 回の訪問で複数のコンバージョンイベントが存在する場合（複数の注文など）に、訪問あたりの指標値を最大化するように選択できます。 最適化される「率」は、指標の合計値を訪問回数で割った値です。 |
| 自動ターゲット | Target  | （設定不可） | 指標はバイナリとして扱われ、個別訪問コンバージョン率は最大化されます。 |



最適化基準に応じて、 [!DNL Adobe Analytics] 指標はサポートされません。

* [!DNL Adobe Analytics] 計算指標はサポートされていません。
* [!DNL Adobe Analytics] 指標は常にセグメント化可能である必要があり、訪問者/訪問あたりの値が最適化されている場合、指標は正の極性になっている必要があります（つまり、正の値は負の値よりも優れています）
* [!DNL Adobe Analytics] 使用される指標 [!DNL Auto-Target] アクティビティは、DataWarehouseエクスポートで使用できる必要があります。

## 制限事項と注意事項

いくつかの制限事項と注意事項は、 [!UICONTROL 自動配分] および [!UICONTROL 自動ターゲット] アクティビティ。 その他の制限事項や注意事項は、1 つのアクティビティタイプまたは他のアクティビティタイプに適用されます。

### 自動配分と自動ターゲット {#both}

* を使用する場合 [!DNL Adobe Analytics] レポートソースとして [!UICONTROL 自動配分] または [!UICONTROL 自動ターゲット]を使用する場合、常に [!DNL Analytics].
* レポートソースを次から変更することはできません： [!DNL Analytics] から [!DNL Target] または、アクティビティがアクティブ化された後に反対に実行されます。
* 計算指標は主な目標指標としてサポートされていませんが、多くの場合、カスタムイベントを主な目標指標として選択する代わりに、意図した結果を得ることができます。 例えば、「訪問者ごとのフォームの完了」などの指標を最適化する場合は、「フォームの完了」に対応するカスタムイベントを主な目標指標として選択します。 詳しくは、 [サポートされる目標指標と最適化条件](#supported)（アクティビティのタイプと最適化条件に応じて） [!DNL Target] はコンバージョン指標を自動的に正規化するので、計算指標を使用して正規化を実行する必要はありません。


### 自動配分 {#aa}

* **トレーニング頻度**: [!UICONTROL 自動配分] モデルは、通常どおり、1 時間ごとにトレーニングを続けます。
* **アトリビューションモデル**: [!DNL Target] は [!DNL Adobe Analytics] のデフォルト属性モデル[!UICONTROL  自動配分] A4T を使用するアクティビティに関連付けられています。
* **信頼性**:次の条件で使用される信頼性の数式： [!UICONTROL 自動配分] アクティビティが、 [!DNL Adobe Analytics] [!UICONTROL A4T] パネル。 [ここで説明するように](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [!UICONTROL 自動配分] 通常よりも控えめな信頼区間を使用する [!UICONTROL A/B テスト] アクティビティ。 この保守的な信頼水準は、データに対する繰り返しの評価（ピーク）を補います。 その結果、 [!DNL Adobe Analytics] は、 [!UICONTROL 自動配分] アルゴリズム。 しかし、どのエクスペリエンスがよりユニークな訪問者を送信しているかに基づいて、アルゴリズムが最適なエクスペリエンスを決定できます。
* **勝者ステータス**:現在、 [「まだ勝者がありません」と「勝者」バッジ](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) は [!UICONTROL A4T] パネル内 [!DNL Analysis Workspace]. 同じレポートが [!DNL Target]. 勝者の「星」バッジが [!DNL Target] レポート [!UICONTROL 自動配分] A4T を使用するアクティビティは無視する必要があります。 このバッジは、通常の信頼性の計算を反映し、 [!UICONTROL 自動配分].

### 自動ターゲット {#at}

* **トレーニング頻度**: [!UICONTROL 自動ターゲット] モデルは、通常どおり、24 時間ごとにトレーニングを続けます。 ただし、コンバージョンイベントのデータは [!DNL Analytics] は、6～24 時間延長されます。 この遅延は、 [!DNL Target] ～で記録された最新の出来事を追跡する [!DNL Analytics]. この遅延は、アクティビティが最初にアクティブ化されてから最初の 48 時間で最も大きな影響を与えます。 アクティビティのパフォーマンスがより密接に反映されます [!DNL Analytics] 5 日経過後のコンバージョン動作。 使用を検討 [!UICONTROL 自動配分] の代わりに [!UICONTROL 自動ターゲット] ：アクティビティが存在してから最初の 5 日間にほとんどのトラフィックが発生する、短期間のアクティビティ。
* を使用する場合 [!DNL Analytics] を [!UICONTROL 自動ターゲット] アクティビティ、セッションは 6 時間経過後に終了します。 6 時間後に発生したコンバージョンはカウントされません。

詳しくは、 [アトリビューションモデルとルックバックウィンドウ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) 内 *Analytics ツールガイド*.

## 自動ターゲットおよび自動配分アクティビティ用にAnalysis Workspaceで A4T レポートを設定する方法 {#tutorial}

豊富な分析機能は [!DNL Adobe Analytics] [!UICONTROL Analysis Workspace]( デフォルトの [!UICONTROL Analytics for Target] パネルが、自動配分および自動ターゲットアクティビティを正しく解釈するために必要です。

これらの変更は、 [サポートされる目標指標と最適化条件](#supported)、および実験アクティビティの違い ( 手動の A/B および [!UICONTROL 自動配分]) とパーソナライゼーションアクティビティ ([!UICONTROL 自動ターゲット]) をクリックします。

これらのチュートリアルでは、分析に推奨される変更について順を追って説明します [!UICONTROL A4T] [!UICONTROL 自動配分] および [!UICONTROL 自動ターゲット] アクティビティ [!UICONTROL Workspace].

詳しくは、  
* [自動配分アクティビティ用にAnalysis Workspaceで A4T レポートを設定する方法](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) in *Adobe TargetTutorials*.
* [Analysis Workspace for Auto-Target アクティビティで A4T レポートを設定する方法](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) in *Adobe TargetTutorials*.
