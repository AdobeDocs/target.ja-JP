---
keywords: customer journey analytics;target の customer journey analytics;customer journey analytics レポートソース；target のレポートソースとしての customer journey analytics;cja での target レポート；Customer Journey Analyticsでの target レポート
description: インレポートを使用して  [!DNL Target]  コンバージョン指標  [!DNL Adobe Customer Journey Analytics]  オーディエンスセグメントに基づいてアクティビティを作成し  [!DNL Customer Journey Analytics]  レポートを使用して結果を調べます。 [!DNL Customer Journey Analytics]  レポートでは、以下の操作を実行できます。
title: ' [!DNL Adobe Customer Journey Analytics] でのレポ  [!DNL Target]  トとは'
feature: Integrations
exl-id: 67b20bf6-ffbe-4220-9455-cb3886bb9227
source-git-commit: 5e86d3a95dad291f6c876f126568ba685ff32670
workflow-type: tm+mt
source-wordcount: '1038'
ht-degree: 58%

---

# [!DNL Adobe Customer Journey Analytics] での [!DNL Target] レポート

[Adobe Customer Journey Analytics](https://experienceleague.adobe.com/ja/docs/customer-journey-analytics){target=_blank} と [!DNL Target] の統合では、組織の最適化プログラムに適した強力な分析機能と時間節約ツールを利用できます。

[!DNL Customer Journey Analytics] を [!DNL Target] のレポートソースとして使用する主なメリットは次のとおりです。

* マーケターは、[!DNL Customer Journey Analytics] の成功指標を [!DNL Target] のアクティビティレポートにいつでも動的に適用できます。アクティビティを実行する前にすべての項目を指定する必要はありません。
* マーケターは、[実験パネル](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/panels/experimentation){target=_blank}などの [!DNL Customer Journey Analytics] 機能を活用して、web サイトのパーソナライゼーションをさらに分析できます。
* マーケターは、[[!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/reporting/cja-ajo){target=_blank} および [!DNL Target] のレポートを単一のソースで作成できます。両方のパーソナライゼーション製品を [!DNL Customer Journey Analytics] に接続すると、web パーソナライゼーションの全体像を把握できます。

## 注意点

[!DNL Customer Journey Analytics] と [!DNL Target] の統合を使用する前に、次の情報を考慮してください。

>[!IMPORTANT]
>
>この統合は [[!UICONTROL Adobe Analytics for Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) （A4T）とは異なります。 実装とサポートされているアクティビティタイプは異なります。 [!DNL Target] アクティビティでこの統合を使用する前に、この記事を十分に読んでください。

* [!DNL Customer Journey Analytics] を [!DNL Target] のレポートソースとして使用するには、利用者と企業が、[!DNL Customer Journey Analytics] と [!DNL Target] の両方にアクセスできる必要があります。いずれかのソリューションへのアクセスが必要な場合は、組織の管理者またはアカウント担当者にお問い合わせください。
* [!DNL Customer Journey Analytics] レポートを使用して [!DNL Target] アクティビティを作成するには、[!DNL Target] に「[!UICONTROL Approver]」または「[!UICONTROL Editor]」の役割が必要です。
   * [Target Standard](/help/main/c-intro/intro.md#section_ACD5EFF17AAB4E979CBEFA0145CCD905) アカウントを所有している場合、*ユーザー*&#x200B;の[役割および権限の指定](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions)を参照してください。
   * [Target Premium](/help/main/c-intro/intro.md#premium) アカウントを所有している場合は、*Enterprise ユーザーの権限*&#x200B;で[役割と権限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#roles-permissions)を参照してください。

* [!DNL Customer Journey Analytics] をレポートソースとして [!DNL Target] アクティビティを設定するには、[!DNL Adobe Experience Platform] の役割に属している必要があります。詳しくは、*データアーキテクトおよびエンジニア向けチュートリアル*&#x200B;の&#x200B;*権限の設定*&#x200B;の [ [!DNL Adobe Experience Platform] での役割の追加](https://experienceleague.adobe.com/en/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/configure-permissions#add-a-role-in-adobe-experience-platform-requires-a-system-administrator-or-product-admin){target=_blank}を参照してください。
* 設定に応じて、アクティビティごとまたは組織レベルでレポートを変更できます。詳しくは、*Target でのレポートの設定*&#x200B;で[レポートクラウドソリューション](/help/main/administrating-target/reporting.md#solution)を参照してください。
* どちらか 1 つのレポートソースを選びます。1 つのアクティビティのデータを複数のレポートソースに収集することはできません。
* [!DNL Customer Journey Analytics] をレポートソースとして設定すると、レポート用のサンドボックスを指定するよう求められます。 設定時には、アクセスできるサンドボックスのみが表示されます。
* 既存の [!DNL Target] アクティビティは引き続きデータ収集 [!DNL Target] 使用するので、この統合を有効にしても影響を受けません。
* この統合を使用するには、[[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep-web-sdk){target=_blank} を使用して [[!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/en/docs/experience-platform){target=_blank} と [!DNL Target] を実装する方法が推奨されます。

  [!DNL Adobe Experience Platform Web SDK] が現在実装されていない場合は、[[!DNL Adobe Analytics]  ソース接続 ](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics) を作成してデータを [!DNL Adobe Experience Platform] に取り込むこともできます。 この方法を使用する場合は、[!DNL Customer Journey Analytics] で使用する [!DNL Adobe Experience Platform] サンドボックスと共に [!DNL Analytics] レポートスイートを選択する必要があります。

  ![ レポート設定ダイアログボックスの「サンドボックス」オプション ](/help/main/c-integrating-target-with-mac/cja/assets/aep-sandbox.png)

  >[!NOTE]
  >
  >[!DNL Adobe Analytics] ソース接続を使用すると、[!DNL Adobe Analytics] と [!DNL Customer Journey Analytics] の両方にレポートがあります。 ただし、両方のソリューションでアルゴリズムが異なるので、結果が一致する可能性は低くなります。

* タイミングに関するご質問は、*[!DNL Adobe Customer Analytics]ガイド*&#x200B;の&#x200B;*よくある質問*&#x200B;内の[遅延に関する考慮事項](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-faq#latency){target=_blank}を参照してください。

## サポートされているアクティビティのタイプ {#supported-activities}

[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep-web-sdk){target=_blank} または [at.js](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/at-js-implementation/overview){target=_blank} JavaScript ライブラリを使用する場合、次のアクティビティタイプがサポートされます。

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

>[!TIP]
>
>また、[!DNL Target] がアカウントで作成されたすべてのアクティビティ（**[!UICONTROL Administration]**/**[!UICONTROL Reporting]**/**[!UICONTROL Reporting Experience Cloud Solution]**）に対して [!DNL Customer Journey Analytics] のレポートを使用するように指定することもできます。 詳しくは、*でのレポートの設定* の [ レポートクラウドソリューション  [!DNL Target]](/help/main/administrating-target/reporting.md#solution) を参照してください。

1. 「**[!UICONTROL Activities]**」リストから「**[!UICONTROL Create Activity]**」をクリックし、（上記の [ サポートされているアクティビティグラフ ](#supported-activities) に従って）アクティビティタイプを選択して、アクティビティの設定を開始します。
1. 3 部構成のアクティビティ作成ワークフローの **[!UICONTROL Goals & Settings]** ページに移動したら、レポートソースとして「**[!DNL Customer Journey Analytics]**」を選択します。

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

1. [!DNL Customer Journey Analytics] の [**[!UICONTROL Connections]**] ページで [**[!UICONTROL Create a new connection]**] をクリックします。

   ![[!DNL Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/assets/create-connection.png) で新しい接続リンクを作成

1. [接続とデータ設定](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/overview){target=_blank}を正しい情報で設定します。
1. データストリームの設定時に使用したイベントデータセットを追加します。
1. **[!UICONTROL Adobe Target Classification Events]** ルックアップデータセットを追加して、「**[!UICONTROL Next]**」をクリックします。

   ![Customer Journey Analytics のデータセットを追加ダイアログボックス](/help/main/c-integrating-target-with-mac/cja/assets/add-datasets.png)

1. イベントデータセットを設定します。

   詳しくは、*[!DNL Adobe Customer Journey Analytics]ガイドの [ 接続の作成 ](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/create-connection#add-dataset){target=_blank} の* データセットの追加と設定 *を参照してください*。

1. [!UICONTROL Key] フィールドを「キー」として、[!UICONTROL Matching] キーフィールドを次のパスで使用して、ルックアップデータセットを設定します。

   ```
   _experience.decisioning.propositions.scopeDetails.correlationID
   ```

   ![Customer Journey Analytics の Adobe Target 分類イベントダイアログボックス](/help/main/c-integrating-target-with-mac/cja/assets/classifications-events.png)

1. 「**[!UICONTROL Add datasets]**」をクリックし、次の画面で「**[!UICONTROL Save]**」をクリックして接続を完了します。

## データビューを設定

[!DNL Customer Journey Analytics] でデータビューを設定します。データビューにより、接続からのデータが適切に使用できるようになります。

1. データビューを設定し、上記で作成した接続をポイントしていることを確認します。

   詳細については、『 データガイド 』の [ データビューの作成または編集 ](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/create-dataview){target=_blank} を参照し *[!DNL Adobe Customer Journey Analytics]ください*。

1. [!DNL Customer Journey Analytics] の [!DNL Target] データを適切に表示するには、ルックアップデータセットから次のフィールドをディメンションとして追加する必要があります。

   * [!UICONTROL Experience Name]
   * [!UICONTROL Experience ID]
   * [!UICONTROL Activity Name]
   * [!UICONTROL Activity ID]

   ![Customer Journey Analytics の「名前」および「ID」オプション](/help/main/c-integrating-target-with-mac/cja/assets/names-and-ids.png){width="600" zoomable="yes"}

1. [!UICONTROL Experimentation] パネルで [!DNL Target] 寸法を使用するには、以下のコンテキストラベルを設定します。

   * [!UICONTROL Activity Name] しくは、「実験実験」を使用します。
   * [!UICONTROL Experience Name] しくは、「実験バリアント」を使用します。

   ![実験パネルのコンテキストラベル](/help/main/c-integrating-target-with-mac/cja/assets/context-labels.png){width="600" zoomable="yes"}

1. 他のフィールドの設定を完了し、完了したら「**[!UICONTROL Save and continue]**」をクリックします。
