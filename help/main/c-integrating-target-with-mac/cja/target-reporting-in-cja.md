---
keywords: customer journey analytics;customer journey analytics for target;customer journey analytics レポートソース；customer journey analytics as the レポートソース for target;cjaのtarget レポート；Customer Journey Analyticsのtarget レポート
description: ' [!DNL Adobe Customer Journey Analytics] の [!DNL Target]  レポートを使用して、 [!DNL Customer Journey Analytics]  コンバージョン指標とオーディエンスセグメントに基づくアクティビティを作成し、 [!DNL Customer Journey Analytics]  レポートを使用して結果を検証します。'
title: ' [!DNL Adobe Customer Journey Analytics]の [!DNL Target]  レポートとは'
feature: Integrations
exl-id: 67b20bf6-ffbe-4220-9455-cb3886bb9227
TQID: https://experienceleague.adobe.com/bEwtqdwOsXyDbBUdxZKMl3I3LLTgxdxURvXjrfco-WI
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
  - id: f7c7de77-382f-4f48-8b36-61a170f06d3d
subfeature_v2:
  - id: df62f171-ac37-440f-8f0f-f41a72ebdd34
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bcc5edb5-84c3-4940-9f84-ed88b6c16274
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 16fb7a1902ea76cab56a93fa141a32a3c6bc4467
workflow-type: tm+mt
source-wordcount: 1488
ht-degree: 37%

---

# [!DNL Adobe Customer Journey Analytics]の[!DNL Target]件のレポート

[Adobe Customer Journey Analytics](https://experienceleague.adobe.com/ja/docs/customer-journey-analytics){target=_blank} と [!DNL Target] を統合すれば、最適化プログラムに適した強力な分析機能と時間節約ツールを利用できます。

[!DNL Customer Journey Analytics] を [!DNL Target] のレポートソースとして使用する主なメリットは次のとおりです。

* マーケターは、[!DNL Customer Journey Analytics] の成功指標を [!DNL Target] のアクティビティレポートにいつでも動的に適用できます。 アクティビティを実行する前にすべての項目を指定する必要はありません。
* マーケターは、[実験パネル](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/panels/experimentation){target=_blank}などの [!DNL Customer Journey Analytics] 機能を活用して、web サイトのパーソナライゼーションをさらに分析できます。
* マーケターは、[!DNL Adobe Journey Optimizer]と[!DNL Target]に対するレポートの唯一のソースを持つことができます。 両方のパーソナライゼーション製品を [!DNL Customer Journey Analytics] に接続すると、web パーソナライゼーションの全体像を把握できます。

## 注意点

[!DNL Customer Journey Analytics]と[!DNL Target]の統合を使用する前に、次の情報を検討してください。

>[!IMPORTANT]
>
>この統合は、Target[&#128279;](/help/main/c-integrating-target-with-mac/a4t/a4t.md) （A4T）のAdobe Analyticsと同じではありません。 実装とサポートされるアクティビティタイプは異なります。 この統合を[!DNL Target] アクティビティに使用する前に、この記事を十分に読んでください。

* [!DNL Customer Journey Analytics] を [!DNL Target] のレポートソースとして使用するには、利用者と企業が、[!DNL Customer Journey Analytics] と [!DNL Target] の両方にアクセスできる必要があります。 いずれかのソリューションへのアクセスが必要な場合は、組織の管理者またはアカウント担当者にお問い合わせください。
* [!DNL Customer Journey Analytics]件のレポートを使用して[!DNL Target]件のアクティビティを作成するには、[!DNL Target]で「[!UICONTROL 承認者]」または「[!UICONTROL 編集者]」の役割を持っている必要があります。
   * [Target Standard](/help/main/c-intro/intro.md#section_ACD5EFF17AAB4E979CBEFA0145CCD905) アカウントを所有している場合、*ユーザー*&#x200B;の[役割および権限の指定](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions)を参照してください。
   * [Target Premium](/help/main/c-intro/intro.md#premium) アカウントを所有している場合は、*Enterprise ユーザーの権限*&#x200B;で[役割と権限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#roles-permissions)を参照してください。

* [!DNL Customer Journey Analytics]をレポートソースとして使用して[!DNL Target] アクティビティを設定するには、[!DNL Adobe Experience Platform]の役割に参加してください。 詳しくは、*データアーキテクトおよびエンジニアチュートリアルの*&#x200B;権限の設定&#x200B;*の[役割の追加 [!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/ja/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/configure-permissions#add-a-role-in-adobe-experience-platform-requires-a-system-administrator-or-product-admin){target=_blank}を参照してください。*
* 設定に応じて、アクティビティごとまたは組織レベルでレポートを変更できます。 詳しくは、*Target でのレポートの設定*&#x200B;で[レポートクラウドソリューション](/help/main/administrating-target/reporting.md#solution)を参照してください。
* どちらか 1 つのレポートソースを選びます。 1 つのアクティビティのデータを複数のレポートソースに収集することはできません。
* [!DNL Customer Journey Analytics] をレポートソースとして設定すると、レポート用のサンドボックスを指定するよう求められます。 設定時には、アクセスできるサンドボックスのみが表示されます。
* 既存の[!DNL Target] アクティビティは引き続き[!DNL Target] データ収集を使用し、この統合を有効にしても影響を受けません。
* この統合を使用するには、優先される実装方法は、[[!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/ja/docs/experience-platform){target=_blank}および[!DNL Target]を[[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/ja/docs/target-dev/developer/client-side/aep/aep-web-sdk-overview){target=_blank}を通じて実装することです。

  現在[!DNL Adobe Experience Platform Web SDK]を実装していない場合は、[[!DNL Adobe Analytics]  ソース接続](https://experienceleague.adobe.com/ja/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics)を作成して、データを[!DNL Adobe Experience Platform]に取り込むこともできます。 この方法を使用する場合は、[!DNL Customer Journey Analytics]で使用する[!DNL Adobe Experience Platform] サンドボックスと一緒に[!DNL Analytics] レポートスイートを選択する必要があります。

  レポート設定ダイアログボックスの![&#x200B; サンドボックスオプション &#x200B;](/help/main/c-integrating-target-with-mac/cja/assets/aep-sandbox.png)

  >[!NOTE]
  >
  >[!DNL Adobe Analytics] ソース接続を使用している場合、[!DNL Adobe Analytics]と[!DNL Customer Journey Analytics]の両方にレポートがあります。 しかし、両者のアルゴリズムが異なるため、結果が一致する可能性は低くなります。

* タイミングに関するご質問は、*[!DNL Adobe Customer Analytics]ガイド*&#x200B;の&#x200B;*よくある質問*&#x200B;の[遅延に関する考慮事項](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-faq#latency){target=_blank}を参照してください。

## サポートされているアクティビティのタイプ {#supported-activities}

[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/ja/docs/target-dev/developer/client-side/aep/aep-web-sdk-overview){target=_blank}または[at.js](https://experienceleague.adobe.com/ja/docs/target-dev/developer/client-side/at-js-implementation/overview){target=_blank} JavaScript ライブラリを使用する場合、次のアクティビティタイプがサポートされます。

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
>また、[!DNL Target]がアカウントで作成されたすべてのアクティビティに[!DNL Customer Journey Analytics]のレポートを使用するように指定することもできます（**[!UICONTROL 管理]** > **[!UICONTROL レポート]** > **[!UICONTROL レポート Experience Cloud ソリューション]**）。 詳しくは、[&#x200B; レポートの&#x200B;*Reporting Cloud Solution*&#x200B;を参照してください。 [!DNL Target]](/help/main/administrating-target/reporting.md#solution)でレポートを設定します。

1. **[!UICONTROL アクティビティ]** リストから、**[!UICONTROL アクティビティを作成]**&#x200B;をクリックし、アクティビティタイプ（[&#x200B; サポートされているアクティビティチャート &#x200B;](#supported-activities)に従う）を選択して、アクティビティの設定を開始します。
1. 3部構成のアクティビティ作成ワークフローの&#x200B;**[!UICONTROL 目標と設定]** ページにアクセスしたら、レポートソースとして&#x200B;**[!DNL Customer Journey Analytics]**&#x200B;を選択します。

   ![レポートソースとしての Customer Journey Analytics オプション](/help/main/c-integrating-target-with-mac/cja/assets/cja-as-reporting-source.png)

   >[!NOTE]
   >
   >[!DNL Target] アクティビティがライブになった後は、レポートソースを変更できません。

1. サンドボックスを選択します。

   このドロップダウンリストには、アクセスできるサンドボックスのみが表示されます。 アクセス権のあるサンドボックスが 1 つ以上リストにない場合は、そのサンドボックスへのアクセス権があることを確認します。 引き続き問題が発生する場合は、[カスタマーケア](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)にお問い合わせください。

   ![サンドボックスオプションを選択](/help/main/c-integrating-target-with-mac/cja/assets/sandbox.png)

1. アクティビティの目標を指定します。

   各アクティビティの目標として使用する成功指標を選択します。 [!DNL Target] コンバージョン指標の 1 つを選択するか、[!DNL Customer Journey Analytics] 指標を使用できます。

   ![目標指標で Customer Journey Analytics 指標オプションを使用](/help/main/c-integrating-target-with-mac/cja/assets/goal-metric.png)

1. 「**[!UICONTROL 保存して閉じる]**」をクリックします。

## [!DNL Customer Journey Analytics] 接続の設定

[!DNL Target] アクティビティを作成したら、[!DNL Customer Journey Analytics] で接続を作成する必要があります。 既に接続を設定している場合は、既存の接続を使用して、以下の手順 4 に進みます。 この接続により、[!DNL Customer Journey Analytics] でレポート用にデータセットからデータの取得を開始できるようになります。

1. [!DNL Customer Journey Analytics]で、**[!UICONTROL 接続]** ページで、**[!UICONTROL 新しい接続を作成]**&#x200B;をクリックします。

   ![新しい接続リンクを[!DNL Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/assets/create-connection.png)に作成

1. 正しい情報を使用して[接続とデータ設定](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-connections/overview){target=_blank}を構成します。
1. データストリームの設定時に使用したイベントデータセットを追加します。
1. **[!UICONTROL Adobe Target Classification Events]**&#x200B;参照データセットを追加し、**[!UICONTROL Next]**&#x200B;をクリックします。

   ![Customer Journey Analytics のデータセットを追加ダイアログボックス](/help/main/c-integrating-target-with-mac/cja/assets/add-datasets.png)

1. イベントデータセットを設定します。

   詳細については、*[!DNL Adobe Customer Journey Analytics]ガイド*&#x200B;の「*接続の作成*」の「[&#x200B; データセットの追加と設定](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-connections/create-connection#add-dataset){target=_blank}」を参照してください。

1. [!UICONTROL Key] フィールドを「key」とし、[!UICONTROL Matching] キーフィールドを次のパスに設定して、ルックアップデータセットを設定します。

   ```
   _experience.decisioning.propositions.scopeDetails.correlationID
   ```

   ![Customer Journey Analytics の Adobe Target 分類イベントダイアログボックス](/help/main/c-integrating-target-with-mac/cja/assets/classifications-events.png)

1. 「**[!UICONTROL データセットを追加]**」をクリックし、次の画面の「**[!UICONTROL 保存]**」をクリックして接続を終了します。

## データビューを設定

[!DNL Customer Journey Analytics] でデータビューを設定します。 データビューにより、接続からのデータが適切に使用できるようになります。

1. データビューを設定し、上記で作成した接続をポイントしていることを確認します。

   詳しくは、*[!DNL Adobe Customer Journey Analytics]ガイド*&#x200B;の「[&#x200B; データビューの作成または編集](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-dataviews/create-dataview){target=_blank}」を参照してください。

1. [!DNL Customer Journey Analytics] の [!DNL Target] データを適切に表示するには、ルックアップデータセットから次のフィールドをディメンションとして追加する必要があります。

   * [!UICONTROL &#x200B; エクスペリエンス名]
   * [!UICONTROL &#x200B; エクスペリエンス ID]
   * [!UICONTROL &#x200B; アクティビティ名]
   * [!UICONTROL &#x200B; アクティビティ ID]

   ![Customer Journey Analytics の「名前」および「ID」オプション](/help/main/c-integrating-target-with-mac/cja/assets/names-and-ids.png){width="600" zoomable="yes"}

1. [!UICONTROL 実験] パネルで[!DNL Target] ディメンションを使用するには、次のコンテキストラベルを設定します。

   * [!UICONTROL &#x200B; アクティビティ名]には、「実験の実験」を使用します。
   * [!UICONTROL 体験名]、「実験のバリアント」を使用してください。

   ![実験パネルのコンテキストラベル](/help/main/c-integrating-target-with-mac/cja/assets/context-labels.png){width="600" zoomable="yes"}

1. 他のフィールドの設定を完了し、**[!UICONTROL 保存して続行]**&#x200B;をクリックします。

## [!DNL Customer Journey Analytics]でのアクティビティレポートの作成と表示

設定が完了したら、[!DNL Adobe Experience Cloud]または[!DNL Target]のアクティビティの「[!UICONTROL &#x200B; レポート &#x200B;]」タブを介して[!DNL Customer Journey Analytics]。

「レポート」タブには、「**[!UICONTROL Customer Journey Analyticsで表示]**」リンクがあります。 現在、このリンクをクリックすると、[!DNL Customer Journey Analytics] ホーム ランディングページに移動します。

![CJA レポート リンク &#x200B;](/help/main/c-integrating-target-with-mac/cja/assets/report-link.png)

>[!NOTE]
>
>この統合は、Target （A4T）のAdobe Analyticsと同じではありません。
>
>* [!DNL Target]/[!DNL Customer Journey Analytics]統合には、A4Tのような事前定義済みのレポートは含まれていません。 アクティビティレポートは[!DNL Customer Journey Analytics]に組み込む必要があります。
>
>* アクティビティの目標指標として[!UICONTROL CJA指標]を使用する場合、このオプションを使用すると、特定の成功指標を定義する必要がある場合に柔軟に対応できます。 [!UICONTROL 実験] パネルの設定時に、成功指標が選択されます。 上昇率と信頼度は、選択したCJA指標から計算されます。

1. [!DNL Customer Journey Analytics]で、実験パネルを作成し、**[!UICONTROL 実験]** ドロップダウンメニューからアクティビティを選択します。

   詳しくは、*[!DNL Customer Journey Analytics]* ガイドの&#x200B;*実験パネル*&#x200B;の下の[実験パネル &#x200B;](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/panels/experimentation?lang=en#use){target=_blank}を参照してください。

   Customer Journey Analyticsの![実験パネル &#x200B;](/help/main/c-integrating-target-with-mac/cja/assets/experimentation-panel.png)

   >[!IMPORTANT]
   >
   >アクティビティが[!UICONTROL 実験] ドロップダウンリストに表示されない場合は、正しいデータビューが選択されており、[!DNL Target] ディメンションに必要なコンテキストラベルが含まれていることを確認します（[&#x200B; データビューの設定](https://experienceleague.adobe.com/ja/docs/target/using/integrate/cja/target-reporting-in-cja#set-up-data-views){target=_blank}の手順3を参照）。

1. 「**[!UICONTROL 作成]**」をクリックします。

   [!UICONTROL 実験] パネルは、実験のパフォーマンスをより深く理解するのに役立つ豊富なデータとビジュアライゼーションのセットを返します。 詳しくは、*[!DNL Customer Journey Analytics]* ガイドの&#x200B;*実験パネル*&#x200B;の[[!UICONTROL &#x200B; パネル出力]](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/panels/experimentation#panel-output){target=_blank}を参照してください。

   ![実験](/help/main/c-integrating-target-with-mac/cja/assets/experimentation.png)