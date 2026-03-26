---
keywords: customer journey analytics;customer journey analytics for target;customer journey analytics レポートソース；customer journey analytics as the レポートソース for target;cjaのtarget レポート；Customer Journey Analyticsのtarget レポート
description: ' [!DNL Target] の [!DNL Adobe Customer Journey Analytics]  レポートを使用して、 [!DNL Customer Journey Analytics]  コンバージョン指標とオーディエンスセグメントに基づくアクティビティを作成し、 [!DNL Customer Journey Analytics]  レポートを使用して結果を検証します。'
title: ' [!DNL Target] の [!DNL Adobe Customer Journey Analytics] レポートとは'
feature: Integrations
exl-id: 67b20bf6-ffbe-4220-9455-cb3886bb9227
source-git-commit: 23e5513879ec15922af78ca6696f94ed4d0ae9b5
workflow-type: tm+mt
source-wordcount: '1232'
ht-degree: 43%

---

# [!DNL Target]の[!DNL Adobe Customer Journey Analytics]件のレポート

[Adobe Customer Journey Analytics](https://experienceleague.adobe.com/ja/docs/customer-journey-analytics){target=_blank} と [!DNL Target] を統合すれば、最適化プログラムに適した強力な分析機能と時間節約ツールを利用できます。

[!DNL Customer Journey Analytics] を [!DNL Target] のレポートソースとして使用する主なメリットは次のとおりです。

* マーケターは、[!DNL Customer Journey Analytics] の成功指標を [!DNL Target] のアクティビティレポートにいつでも動的に適用できます。アクティビティを実行する前にすべての項目を指定する必要はありません。
* マーケターは、[実験パネル](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/panels/experimentation){target=_blank}などの [!DNL Customer Journey Analytics] 機能を活用して、web サイトのパーソナライゼーションをさらに分析できます。
* マーケターは、[!DNL Adobe Journey Optimizer]と[!DNL Target]に対するレポートの唯一のソースを持つことができます。 両方のパーソナライゼーション製品を [!DNL Customer Journey Analytics] に接続すると、web パーソナライゼーションの全体像を把握できます。

## 注意点

[!DNL Customer Journey Analytics]と[!DNL Target]の統合を使用する前に、次の情報を検討してください。

>[!IMPORTANT]
>
>この統合は[[!UICONTROL Adobe Analytics for Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) （A4T）と同じではありません。 実装とサポートされるアクティビティタイプは異なります。 この統合を[!DNL Target] アクティビティに使用する前に、この記事を十分に読んでください。

* [!DNL Customer Journey Analytics] を [!DNL Target] のレポートソースとして使用するには、利用者と企業が、[!DNL Customer Journey Analytics] と [!DNL Target] の両方にアクセスできる必要があります。いずれかのソリューションへのアクセスが必要な場合は、組織の管理者またはアカウント担当者にお問い合わせください。
* [!DNL Target]件のレポートを使用して[!DNL Customer Journey Analytics]件のアクティビティを作成するには、[!UICONTROL Approver]で「[!UICONTROL Editor]」または「[!DNL Target]」の役割を持っている必要があります。
   * [Target Standard](/help/main/c-intro/intro.md#section_ACD5EFF17AAB4E979CBEFA0145CCD905) アカウントを所有している場合、*ユーザー*&#x200B;の[役割および権限の指定](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions)を参照してください。
   * [Target Premium](/help/main/c-intro/intro.md#premium) アカウントを所有している場合は、*Enterprise ユーザーの権限*&#x200B;で[役割と権限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#roles-permissions)を参照してください。

* [!DNL Adobe Experience Platform]をレポートソースとして使用して[!DNL Target] アクティビティを設定するには、[!DNL Customer Journey Analytics]の役割に参加してください。 詳しくは、[ データアーキテクトおよびエンジニアチュートリアルの [!DNL Adobe Experience Platform]権限の設定](https://experienceleague.adobe.com/en/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/configure-permissions#add-a-role-in-adobe-experience-platform-requires-a-system-administrator-or-product-admin){target=_blank}の&#x200B;*役割の追加**を参照してください。*
* 設定に応じて、アクティビティごとまたは組織レベルでレポートを変更できます。詳しくは、*Target でのレポートの設定*&#x200B;で[レポートクラウドソリューション](/help/main/administrating-target/reporting.md#solution)を参照してください。
* どちらか 1 つのレポートソースを選びます。1 つのアクティビティのデータを複数のレポートソースに収集することはできません。
* [!DNL Customer Journey Analytics] をレポートソースとして設定すると、レポート用のサンドボックスを指定するよう求められます。 設定時には、アクセスできるサンドボックスのみが表示されます。
* 既存の[!DNL Target] アクティビティは引き続き[!DNL Target] データ収集を使用し、この統合を有効にしても影響を受けません。
* この統合を使用するには、優先される実装方法は、[[!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/en/docs/experience-platform){target=_blank}および[!DNL Target]を[[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep/aep-web-sdk-overview){target=_blank}を通じて実装することです。

  現在[!DNL Adobe Experience Platform Web SDK]を実装していない場合は、[[!DNL Adobe Analytics]  ソース接続](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics)を作成して、データを[!DNL Adobe Experience Platform]に取り込むこともできます。 この方法を使用する場合は、[!DNL Analytics]で使用する[!DNL Adobe Experience Platform] サンドボックスと一緒に[!DNL Customer Journey Analytics] レポートスイートを選択する必要があります。

  レポート設定ダイアログボックスの![ サンドボックスオプション ](/help/main/c-integrating-target-with-mac/cja/assets/aep-sandbox.png)

  >[!NOTE]
  >
  >[!DNL Adobe Analytics] ソース接続を使用している場合、[!DNL Adobe Analytics]と[!DNL Customer Journey Analytics]の両方にレポートがあります。 しかし、両者のアルゴリズムが異なるため、結果が一致する可能性は低くなります。

* タイミングに関するご質問は、[ ガイド ](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-faq#latency){target=_blank}の&#x200B;*よくある質問*&#x200B;の&#x200B;*[!DNL Adobe Customer Analytics]遅延に関する考慮事項*&#x200B;を参照してください。

## サポートされているアクティビティのタイプ {#supported-activities}

[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep/aep-web-sdk-overview){target=_blank}または[at.js](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/at-js-implementation/overview){target=_blank} JavaScript ライブラリを使用する場合、次のアクティビティタイプがサポートされます。

| アクティビティのタイプ | 対応? |
|--- |--- |
| [手動トラフィック分割を使用した A/B アクティビティ](/help/main/c-activities/t-test-ab/test-ab.md) | ○ |
| [自動配分を使用した A/B アクティビティ](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | × |
| [自動ターゲットを使用した A/B アクティビティ](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | × |
| [エクスペリエンスのターゲット設定（XT）](/help/main/c-activities/t-experience-target/experience-target.md) | ○ |
| [多変量分析テスト（MVT）](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | ○ |
| [Automated Personalization（AP）アクティビティ](/help/main/c-activities/t-automated-personalization/automated-personalization.md) | × |
| [レコメンデーションアクティビティ](/help/main/c-recommendations/recommendations.md) | ○ |

## [!DNL Customer Journey Analytics] をレポートソースとして使用するアクティビティの作成

[!DNL Customer Journey Analytics] をレポートソースとして使用する [!DNL Target] アクティビティの作成は、通常の [!DNL Target] アクティビティの設定と似ています。

>[!TIP]
>
>また、[!DNL Target]がアカウントで作成されたすべてのアクティビティに[!DNL Customer Journey Analytics]のレポートを使用するように指定することもできます（**[!UICONTROL Administration]** > **[!UICONTROL Reporting]** > **[!UICONTROL Reporting Experience Cloud Solution]**）。 詳しくは、*レポートの* Reporting Cloud Solution[を参照してください。 [!DNL Target]](/help/main/administrating-target/reporting.md#solution)でレポートを設定します。

1. **[!UICONTROL Activities]** リストから「**[!UICONTROL Create Activity]**」をクリックし、アクティビティの種類（[ サポートされているアクティビティ チャート ](#supported-activities)に従う）を選択して、アクティビティの設定を開始します。
1. 3部構成のアクティビティ作成ワークフローの&#x200B;**[!UICONTROL Goals & Settings]** ページにアクセスしたら、レポートソースとして「**[!DNL Customer Journey Analytics]**」を選択します。

   ![レポートソースとしての Customer Journey Analytics オプション](/help/main/c-integrating-target-with-mac/cja/assets/cja-as-reporting-source.png)

   >[!NOTE]
   >
   >[!DNL Target] アクティビティがライブになった後は、レポートソースを変更できません。

1. サンドボックスを選択します。

   このドロップダウンリストには、アクセスできるサンドボックスのみが表示されます。 アクセス権のあるサンドボックスが 1 つ以上リストにない場合は、そのサンドボックスへのアクセス権があることを確認します。引き続き問題が発生する場合は、[カスタマーケア](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)にお問い合わせください。

   ![サンドボックスオプションを選択](/help/main/c-integrating-target-with-mac/cja/assets/sandbox.png)

1. アクティビティの目標を指定します。

   各アクティビティの目標として使用する成功指標を選択します。[!DNL Target] コンバージョン指標の 1 つを選択するか、[!DNL Customer Journey Analytics] 指標を使用できます。

   ![目標指標で Customer Journey Analytics 指標オプションを使用](/help/main/c-integrating-target-with-mac/cja/assets/goal-metric.png)

1. **[!UICONTROL Save & Close]** をクリックします。

## [!DNL Customer Journey Analytics] 接続の設定

[!DNL Target] アクティビティを作成したら、[!DNL Customer Journey Analytics] で接続を作成する必要があります。既に接続を設定している場合は、既存の接続を使用して、以下の手順 4 に進みます。この接続により、[!DNL Customer Journey Analytics] でレポート用にデータセットからデータの取得を開始できるようになります。

1. [!DNL Customer Journey Analytics]で、**[!UICONTROL Connections]** ページの「**[!UICONTROL Create a new connection]**」をクリックします。

   ![新しい接続リンクを[!DNL Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/assets/create-connection.png)に作成

1. 正しい情報を使用して[接続とデータ設定](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/overview){target=_blank}を構成します。
1. データストリームの設定時に使用したイベントデータセットを追加します。
1. **[!UICONTROL Adobe Target Classification Events]**&#x200B;検索データセットを追加し、**[!UICONTROL Next]**&#x200B;をクリックします。

   ![Customer Journey Analytics のデータセットを追加ダイアログボックス](/help/main/c-integrating-target-with-mac/cja/assets/add-datasets.png)

1. イベントデータセットを設定します。

   詳細については、[ ガイド ](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/create-connection#add-dataset){target=_blank}の「*接続の作成*」の「*[!DNL Adobe Customer Journey Analytics]データセットの追加と設定*」を参照してください。

1. [!UICONTROL Key] フィールドを「key」とし、[!UICONTROL Matching] キーフィールドを次のパスに設定して、ルックアップデータセットを設定します。

   ```
   _experience.decisioning.propositions.scopeDetails.correlationID
   ```

   ![Customer Journey Analytics の Adobe Target 分類イベントダイアログボックス](/help/main/c-integrating-target-with-mac/cja/assets/classifications-events.png)

1. **[!UICONTROL Add datasets]**&#x200B;をクリックし、次の画面の&#x200B;**[!UICONTROL Save]**&#x200B;をクリックして接続を終了します。

## データビューを設定

[!DNL Customer Journey Analytics] でデータビューを設定します。データビューにより、接続からのデータが適切に使用できるようになります。

1. データビューを設定し、上記で作成した接続をポイントしていることを確認します。

   詳しくは、[ ガイド ](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/create-dataview){target=_blank}の「*[!DNL Adobe Customer Journey Analytics]データビューの作成または編集*」を参照してください。

1. [!DNL Customer Journey Analytics] の [!DNL Target] データを適切に表示するには、ルックアップデータセットから次のフィールドをディメンションとして追加する必要があります。

   * [!UICONTROL Experience Name]
   * [!UICONTROL Experience ID]
   * [!UICONTROL Activity Name]
   * [!UICONTROL Activity ID]

   ![Customer Journey Analytics の「名前」および「ID」オプション](/help/main/c-integrating-target-with-mac/cja/assets/names-and-ids.png){width="600" zoomable="yes"}

1. [!DNL Target] パネルで[!UICONTROL Experimentation] ディメンションを使用するには、次のコンテキストラベルを設定します。

   * [!UICONTROL Activity Name]には、「実験の実験」を使用します。
   * [!UICONTROL Experience Name]、「実験のバリアント」を使用してください。

   ![実験パネルのコンテキストラベル](/help/main/c-integrating-target-with-mac/cja/assets/context-labels.png){width="600" zoomable="yes"}

1. 他のフィールドの設定を完了し、完了したら「**[!UICONTROL Save and continue]**」をクリックします。

## [!DNL Customer Journey Analytics]でのアクティビティレポートの作成と表示

設定を完了した後、[!DNL Customer Journey Analytics]または[!DNL Adobe Experience Cloud]のアクティビティの[!UICONTROL Reports] タブを介して[!DNL Target]。

「レポート」タブには&#x200B;**[!UICONTROL View in Customer Journey Analytics]** リンクがあります。 現在、このリンクをクリックすると、[!DNL Customer Journey Analytics] ホーム ランディングページに移動します。

![CJA レポート リンク ](/help/main/c-integrating-target-with-mac/cja/assets/report-link.png)

>[!NOTE]
>
>この統合は[!UICONTROL Adobe Analytics for Target] （A4T）と同じではありません。
>
>* [!DNL Target]/[!DNL Customer Journey Analytics]統合には、A4Tのような事前定義済みのレポートは含まれていません。 アクティビティレポートは[!DNL Customer Journey Analytics]に組み込む必要があります。
>
>* アクティビティの目標指標として[!UICONTROL Use a CJA Metric]が選択されている場合、このオプションは、特定の成功指標を定義する必要がある場合に柔軟性を提供します。 [!UICONTROL Experimentation] パネルの設定時に、成功指標が選択されます。 上昇率と信頼度は、選択したCJA指標から計算されます。

1. [!DNL Customer Journey Analytics]で、実験パネルを作成し、**[!UICONTROL Experiment]** ドロップダウンメニューからアクティビティを選択します。

   詳しくは、[ ガイドの](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/panels/experimentation?lang=en#use){target=_blank}実験パネル *の下の*&#x200B;実験パネル *[!DNL Customer Journey Analytics]*&#x200B;を参照してください。

   Customer Journey Analyticsの![実験パネル ](/help/main/c-integrating-target-with-mac/cja/assets/experimentation-panel.png)

   >[!IMPORTANT]
   >
   >アクティビティが[!UICONTROL Experiment] ドロップダウンリストに表示されない場合は、正しいデータビューが選択されていること、および[!DNL Target] ディメンションに必要なコンテキストラベルが含まれていることを確認します（[ データビューの設定](https://experienceleague.adobe.com/en/docs/target/using/integrate/cja/target-reporting-in-cja#set-up-data-views){target=_blank}の手順3を参照）。

1. **[!UICONTROL Build]** をクリックします。

   [!UICONTROL Experimentation] パネルは、実験のパフォーマンスをより深く理解するために、豊富なデータとビジュアライゼーションのセットを返します。 詳しくは、[[!UICONTROL Panel output] ガイドの](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/panels/experimentation#panel-output){target=_blank}実験パネル *の**[!DNL Customer Journey Analytics]*&#x200B;を参照してください。

   ![実験](/help/main/c-integrating-target-with-mac/cja/assets/experimentation.png)