---
keywords: customer journey analytics;target の customer journey analytics;customer journey analytics レポートソース；target のレポートソースとしての customer journey analytics;cja での target レポート；Customer Journey Analyticsでの target レポート
description: 使用方法 [!DNL Target] でのレポート [!DNL Adobe Customer Journey Analytics] アクティビティの作成基準 [!DNL Customer Journey Analytics] コンバージョン指標とオーディエンスセグメントおよび使用 [!DNL Customer Journey Analytics] 結果を調べるレポート。
title: について [!DNL Target] でのレポート [!DNL Adobe Customer Journey Analytics]?
feature: Integrations
badgeBeta: label="ベータ" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#beta newtab=true" tooltip=" [!DNL Adobe Target] のベータ版機能とは"
hide: true
hidefromtoc: true
exl-id: 67b20bf6-ffbe-4220-9455-cb3886bb9227
source-git-commit: 8475365099315f3f8f2a47bfca9dd9f245b16720
workflow-type: tm+mt
source-wordcount: '1014'
ht-degree: 58%

---

# [!DNL Target] でのレポート [!DNL Adobe Customer Journey Analytics]

～間の統合 [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/customer-journey-analytics){target=_blank} および [!DNL Target] は、組織の最適化プログラムに適した強力な分析ツールと時間節約ツールを提供します。

[!DNL Customer Journey Analytics] を [!DNL Target] のレポートソースとして使用する主なメリットは次のとおりです。

* マーケターは、[!DNL Customer Journey Analytics] の成功指標を [!DNL Target] のアクティビティレポートにいつでも動的に適用できます。アクティビティを実行する前にすべての項目を指定する必要はありません。
* マーケターは以下を活用できます [!DNL Customer Journey Analytics] などの機能 [実験パネル](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/panels/experimentation){target=_blank}を使用して、web サイトのパーソナライゼーションをさらに分析できます。
* マーケターは、のレポートソースを 1 つにまとめることができます [[!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/reporting/cja-ajo){target=_blank} および [!DNL Target]. 両方のパーソナライゼーション製品を [!DNL Customer Journey Analytics] に接続すると、web パーソナライゼーションの全体像を把握できます。

## 注意点

を使用する前に、次の情報を考慮してください [!DNL Customer Journey Analytics] および [!DNL Target] 統合：

>[!IMPORTANT]
>
>この統合は、 [[!UICONTROL Adobe Analytics for Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) （A4T）。 実装とサポートされているアクティビティタイプは異なります。 この統合を使用する前に、必ずこの記事を十分に読んでください。 [!DNL Target] アクティビティ。

* [!DNL Customer Journey Analytics] を [!DNL Target] のレポートソースとして使用するには、利用者と企業が、[!DNL Customer Journey Analytics] と [!DNL Target] の両方にアクセスできる必要があります。いずれかのソリューションへのアクセスが必要な場合は、組織の管理者またはアカウント担当者にお問い合わせください。
* 作成対象 [!DNL Target] を使用したアクティビティ [!DNL Customer Journey Analytics] レポートには、「」のいずれかが必要です[!UICONTROL Approver]&#39;&#39;または&#39;&#39;[!UICONTROL Editor]の役割 [!DNL Target].
   * [Target Standard](/help/main/c-intro/intro.md#section_ACD5EFF17AAB4E979CBEFA0145CCD905) アカウントを所有している場合、*ユーザー*&#x200B;の[役割および権限の指定](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions)を参照してください。
   * [Target Premium](/help/main/c-intro/intro.md#premium) アカウントを所有している場合は、*Enterprise ユーザーの権限*&#x200B;で[役割と権限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#roles-permissions)を参照してください。

* [!DNL Customer Journey Analytics] をレポートソースとして [!DNL Target] アクティビティを設定するには、[!DNL Adobe Experience Platform] の役割に属している必要があります。詳しくは、*データアーキテクトおよびエンジニア向けチュートリアル*&#x200B;の&#x200B;*権限の設定*&#x200B;の [ [!DNL Adobe Experience Platform] での役割の追加](https://experienceleague.adobe.com/en/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/configure-permissions#add-a-role-in-adobe-experience-platform-requires-a-system-administrator-or-product-admin){target=_blank}を参照してください。
* 設定に応じて、アクティビティごとまたは組織レベルでレポートを変更できます。詳しくは、*Target でのレポートの設定*&#x200B;で[レポートクラウドソリューション](/help/main/administrating-target/reporting.md#solution)を参照してください。
* どちらか 1 つのレポートソースを選びます。1 つのアクティビティのデータを複数のレポートソースに収集することはできません。
* [!DNL Customer Journey Analytics] をレポートソースとして設定すると、レポート用のサンドボックスを指定するよう求められます。 設定時には、アクセスできるサンドボックスのみが表示されます。
* 任意の既存 [!DNL Target] アクティビティが引き続き使用する [!DNL Target] データ収集およびは、この統合を有効にしても影響を受けません。
* この統合を使用するために推奨される実装方法は次のとおりです [[!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/en/docs/experience-platform){target=_blank} and [!DNL Target] implemented through the [[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep-web-sdk){target=_blank}.

  を現在持っていない場合 [!DNL Adobe Experience Platform Web SDK] 実装済みで、 [[!DNL Adobe Analytics] ソース接続](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics) データをに送信します。 [!DNL Adobe Experience Platform]. この方法を使用する場合は、 [!DNL Analytics] と共にレポートスイート [!DNL Adobe Experience Platform] と共に使用するサンドボックス [!DNL Customer Journey Analytics].

  ![レポート設定ダイアログボックスの「サンドボックス」オプション](/help/main/c-integrating-target-with-mac/cja/assets/aep-sandbox.png)

  >[!NOTE]
  >
  >を使用する場合 [!DNL Adobe Analytics] ソース接続の場合、両方にレポートがあります [!DNL Adobe Analytics] および [!DNL Customer Journey Analytics]. ただし、両方のソリューションでアルゴリズムが異なるので、結果が一致する可能性は低くなります。

* タイミングに関するご質問は、*[!DNL Adobe Customer Analytics]ガイド*&#x200B;の&#x200B;*よくある質問*&#x200B;内の[遅延に関する考慮事項](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-faq#latency){target=_blank}を参照してください。

## サポートされているアクティビティのタイプ {#supported-activities}

[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep-web-sdk){target=_blank} or the [at.js](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/at-js-implementation/overview){target=_blank} JavaScript ライブラリを使用する場合、次のアクティビティタイプがサポートされます。

| アクティビティのタイプ | 対応? |
|--- |--- |
| [手動トラフィック分割を使用した A/B アクティビティ](/help/main/c-activities/t-test-ab/test-ab.md) | ○ |
| [自動配分を使用した A/B アクティビティ](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | × |
| [自動ターゲットを使用した A/B アクティビティ](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | × |
| [エクスペリエンスのターゲット設定（XT）](/help/main/c-activities/t-experience-target/experience-target.md) | ○ |
| [多変量分析テスト（MVT）](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | ○ |
| [Automated Personalization（AP）アクティビティ](/help/main/c-activities/t-automated-personalization/automated-personalization.md) | × |
| [Recommendations アクティビティ](/help/main/c-recommendations/recommendations.md) | ○ |

## [!DNL Customer Journey Analytics] をレポートソースとして使用するアクティビティの作成

[!DNL Customer Journey Analytics] をレポートソースとして使用する [!DNL Target] アクティビティの作成は、通常の [!DNL Target] アクティビティの設定と似ています。

1. から **[!UICONTROL Activities]** リスト、クリック **[!UICONTROL Create Activity]**&#x200B;を選択してから、 [上記のサポートされているアクティビティグラフ](#supported-activities)）を選択して、アクティビティの設定を開始します。
1. 次の場所に移動すると、 **[!UICONTROL Goals & Settings]** 3 部構成のアクティビティ作成ワークフローのページで、次の項目を選択します **[!DNL Customer Journey Analytics]** をレポートソースとして使用します。

   ![レポートソースとしての Customer Journey Analytics オプション](/help/main/c-integrating-target-with-mac/cja/assets/cja-as-reporting-source.png)

   >[!NOTE]
   >
   >[!DNL Target] アクティビティがライブになった後は、レポートソースを変更できません。

1. サンドボックスを選択します。

   このドロップダウンリストには、アクセス権のあるサンドボックスのみが表示されます。 アクセス権のあるサンドボックスが 1 つ以上リストにない場合は、そのサンドボックスへのアクセス権があることを確認します。引き続き問題が発生する場合は、[カスタマーケア](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)にお問い合わせください。

   ![サンドボックスオプションを選択](/help/main/c-integrating-target-with-mac/cja/assets/sandbox.png)

1. アクティビティの目標を指定します。

   各アクティビティの目標として使用する成功指標を選択します。[!DNL Target] コンバージョン指標の 1 つを選択するか、[!DNL Customer Journey Analytics] 指標を使用できます。

   ![目標指標で Customer Journey Analytics 指標オプションを使用](/help/main/c-integrating-target-with-mac/cja/assets/goal-metric.png)

1. **[!UICONTROL Save & Close]** をクリックします。

## [!DNL Customer Journey Analytics] 接続の設定

[!DNL Target] アクティビティを作成したら、[!DNL Customer Journey Analytics] で接続を作成する必要があります。既に接続を設定している場合は、既存の接続を使用して、以下の手順 4 に進みます。この接続により、[!DNL Customer Journey Analytics] でレポート用にデータセットからデータの取得を開始できるようになります。

1. 対象： [!DNL Customer Journey Analytics]、に **[!UICONTROL Connections]** ページ、クリック **[!UICONTROL Create a new connection]**.

   ![で新しい接続リンクを作成 [!DNL Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/assets/create-connection.png)

1. [接続とデータ設定](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/overview){target=_blank}を正しい情報で設定します。
1. データストリームの設定時に使用したイベントデータセットを追加します。
1. を追加 **[!UICONTROL Adobe Target Classification Events]** データセットを検索してから、をクリックします **[!UICONTROL Next]**.

   ![Customer Journey Analytics のデータセットを追加ダイアログボックス](/help/main/c-integrating-target-with-mac/cja/assets/add-datasets.png)

1. イベントデータセットを設定します。

   詳しくは、を参照してください [データセットの追加と設定](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/create-connection#add-dataset){target=_blank} 。対象： *接続の作成* が含まれる *[!DNL Adobe Customer Journey Analytics]ガイド*.

1. でルックアップデータセットを設定します [!UICONTROL Key] フィールドを「キー」として使用し、 [!UICONTROL Matching] 次のパスを持つキーフィールド：

   ```
   _experience.decisioning.propositions.scopeDetails.correlationID
   ```

   ![Customer Journey Analytics の Adobe Target 分類イベントダイアログボックス](/help/main/c-integrating-target-with-mac/cja/assets/classifications-events.png)

1. クリック **[!UICONTROL Add datasets]**&#x200B;を選択し、 **[!UICONTROL Save]** 次の画面で、接続を完了します。

## データビューを設定

[!DNL Customer Journey Analytics] でデータビューを設定します。データビューにより、接続からのデータが適切に使用できるようになります。

1. データビューを設定し、上記で作成した接続をポイントしていることを確認します。

   詳しくは、を参照してください [データビューの作成または編集](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/create-dataview){target=_blank} が含まれる *[!DNL Adobe Customer Journey Analytics]ガイド*.

1. [!DNL Customer Journey Analytics] の [!DNL Target] データを適切に表示するには、ルックアップデータセットから次のフィールドをディメンションとして追加する必要があります。

   * [!UICONTROL Experience Name]
   * [!UICONTROL Experience ID]
   * [!UICONTROL Activity Name]
   * [!UICONTROL Activity ID]

   ![Customer Journey Analytics の「名前」および「ID」オプション](/help/main/c-integrating-target-with-mac/cja/assets/names-and-ids.png){width="600" zoomable="yes"}

1. 使用目的 [!DNL Target] ディメンション [!UICONTROL Experimentation] パネルで、次のコンテキストラベルを設定します。

   * の場合 [!UICONTROL Activity Name]を使用する場合は、「実験的な実験」を使用します。
   * [!UICONTROL Experience Name]に対しては、「実験バリアント」を使用します。

   ![実験パネルのコンテキストラベル](/help/main/c-integrating-target-with-mac/cja/assets/context-labels.png){width="600" zoomable="yes"}

1. 他のフィールドの設定を終了し、 **[!UICONTROL Save and continue]** 完了した場合。
