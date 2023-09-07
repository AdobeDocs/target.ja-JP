---
keywords: CJA4T;Customer Journey Analytics;Customer Journey Analytics for Target;Customer Journey Analytics レポートソース;Target のレポートソースとしての Customer Journey Analytics
description: ' [!DNL Adobe Customer Journey Analytics]  for  [!DNL Target] （A4T）を使用して、 [!DNL Customer Journey Analytics] コンバージョン指標およびオーディエンスセグメントに基づいた悪てティビティを作成し、 [!DNL Customer Journey Analytics]  レポートを使用して結果を調べます。'
title: ' [!DNL Adobe Customer Journey Analytics]  for  [!DNL Target] （CJA4T）とは'
feature: Integrations
hide: true
hidefromtoc: true
source-git-commit: 13c899b656d9f15e7368d981ac25540c46caccb2
workflow-type: ht
source-wordcount: '919'
ht-degree: 100%

---

# [!DNL Adobe Target] のレポートソースとしての [!DNL Adobe Customer Journey Analytics]（CJA4T）

[Adobe Customer Journey Analytics（CJA）](https://experienceleague.adobe.com/docs/customer-journey-analytics.html?lang=ja){target=_blank} と [!DNL Target] を統合する [!DNL Customer Journey Analytics for Target]（CJA4T）では、組織の最適化プログラムに適した強力な分析機能と時間節約ツールを利用できます。

[!DNL Target] で [!DNL Customer Journey Analytics] データを使用する主なメリットは次のとおりです。

* マーケターは、[!DNL Customer Journey Analytics] の成功指標を [!DNL Target] のアクティビティレポートにいつでも動的に適用できます。アクティビティを実行する前にすべての項目を指定する必要はありません。
* 単一のデータソースにより、2 つの異なるシステムのデータを収集した場合に生じる偏差が最小限に抑えられます。

## 注意点

CJA4T 統合を使用する前に、次の情報を考慮してください。

* [!DNL Customer Journey Analytics] を [!DNL Target] のレポートソースとして使用するには、利用者と企業が、[!DNL Customer Journey Analytics] と [!DNL Target] の両方にアクセスできる必要があります。いずれかのソリューションへのアクセスが必要な場合は、組織の管理者またはアカウント担当者にお問い合わせください。
* [!DNL Target] アクティビティと [!DNL Customer Journey Analytics] レポートを作成するには、[!DNL Target] で「[!UICONTROL 承認者]」または「[!UICONTROL 編集者]」の役割が必要です。
   * [Target Standard](/help/main/c-intro/intro.md#section_ACD5EFF17AAB4E979CBEFA0145CCD905) アカウントを所有している場合、*ユーザー*&#x200B;の[役割および権限の指定](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions)を参照してください。
   * [Target Premium](/help/main/c-intro/intro.md#premium) アカウントを所有している場合は、*Enterprise ユーザーの権限*&#x200B;で[役割と権限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#roles-permissions)を参照してください。

* 設定に応じて、アクティビティごとまたは組織レベルでレポートを変更できます。詳しくは、*Target でのレポートの設定*&#x200B;で[レポートクラウドソリューション](/help/main/administrating-target/reporting.md#solution)を参照してください。
* どちらか 1 つのレポートソースを選びます。1 つのアクティビティのデータを複数のレポートソースに収集することはできません。
* [!DNL Customer Journey Analytics] をレポートソースとして設定すると、レポート用のサンドボックスを指定するよう求められます。 設定時には、アクセスできるサンドボックスのみが表示されます。
* 既存の [!DNL Target] アクティビティは引き続き [!DNL Target] のデータ収集を使用するので、CJA4T を有効にしても影響を受けません。
* CJA4T は、[Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=ja){target=_blank} and [!DNL Target] implemented through the [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=ja){target=_blank} をお持ちの場合にのみ使用できます。[!DNL Analytics Data Connector] のサポートを今後予定しています。
* タイミングに関するご質問は、*AdobeCustomer Analytics ガイド*&#x200B;の&#x200B;*よくある質問*&#x200B;内の[遅延に関する考慮事項](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=ja#latency){target=_blank}を参照してください。

## サポートされているアクティビティのタイプ {#supported-activities}

[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=ja){target=_blank} or the [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/overview.html?lang=ja){target=_blank} JavaScript ライブラリを使用する場合、次のアクティビティタイプがサポートされます。

| アクティビティのタイプ | CJA4T との互換性 |
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

1. **[!UICONTROL アクティビティ]**&#x200B;リストから「**[!UICONTROL アクティビティを作成]**」をクリックし、アクティビティタイプ（[上記のサポートされているアクティビティのグラフ](#supported-activities)に従って）を選択し、アクティビティの設定を開始します。
1. 3 ステップのアクティビティ作成ワークフローの&#x200B;**[!UICONTROL 目標と設定]**&#x200B;ページに移動したら、レポートソースとして **[!DNL Customer Journey Analytics]** を選択します。

   ![レポートソースとしての Customer Journey Analytics オプション](/help/main/c-integrating-target-with-mac/cja4t/assets/cja-as-reporting-source.png)

   >[!NOTE]
   >
   >[!DNL Target] アクティビティがライブになった後は、レポートソースを変更できません。

1. サンドボックスを選択します。

   このドロップダウンリストには、アクセス権のあるサンドボックスのみが表示されます。アクセス権のあるサンドボックスが 1 つ以上リストにない場合は、そのサンドボックスへのアクセス権があることを確認します。引き続き問題が発生する場合は、[カスタマーケア](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)にお問い合わせください。

   ![サンドボックスオプションを選択](/help/main/c-integrating-target-with-mac/cja4t/assets/sandbox.png)

1. アクティビティの目標を指定します。

   各アクティビティの目標として使用する成功指標を選択します。[!DNL Target] コンバージョン指標の 1 つを選択するか、[!DNL Customer Journey Analytics] 指標を使用できます。

   ![目標指標で Customer Journey Analytics 指標オプションを使用](/help/main/c-integrating-target-with-mac/cja4t/assets/goal-metric.png)

1. 「**[!UICONTROL 保存して閉じる]**」をクリックします。

## [!DNL Customer Journey Analytics] 接続の設定

[!DNL Target] アクティビティを作成したら、[!DNL Customer Journey Analytics] で接続を作成する必要があります。既に接続を設定している場合は、既存の接続を使用して、以下の手順 4 に進みます。この接続により、[!DNL Customer Journey Analytics] でレポート用にデータセットからデータの取得を開始できるようになります。

1. [!DNL Customer Journey Analytics] の&#x200B;**[!UICONTROL 接続]**&#x200B;ページで、「**[!UICONTROL 新しい接続を作成]**」をクリックします。

   ![Customer Journey Analytics で新しい接続リンクを作成](/help/main/c-integrating-target-with-mac/cja4t/assets/create-connection.png)

1. [接続とデータ設定](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/overview.html?lang=ja){target=_blank}を正しい情報で設定します。
1. データストリームの設定時に使用したイベントデータセットを追加します。
1. **[!UICONTROL Adobe Target 分類イベント]**&#x200B;ルックアップデータセットを追加し、「**[!UICONTROL 次へ]**」をクリックします。

   ![Customer Journey Analytics のデータセットを追加ダイアログボックス](/help/main/c-integrating-target-with-mac/cja4t/assets/add-datasets.png)

1. イベントデータセットを設定します。

   詳しくは、*Adobe Customer Journey Analytics ガイド*&#x200B;の&#x200B;*接続の作成*&#x200B;の[データセットの追加と設定](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en#add-dataset?lang=ja){target=_blank}を参照してください。

1. 「[!UICONTROL キー]」フィールドを「キー」としてルックアップデータセットを設定し、マッチングキーフィールドを次のパスで設定します。

   ```
   _experience.decisioning.propositions.scopeDetails.correlationID
   ```

   ![Customer Journey Analytics の Adobe Target 分類イベントダイアログボックス](/help/main/c-integrating-target-with-mac/cja4t/assets/classifications-events.png)

1. 「**[!UICONTROL データセットを追加]**」をクリックし、次の画面で「**[!UICONTROL 保存]**」をクリックして接続を終了します。

## データビューを設定

[!DNL Customer Journey Analytics] でデータビューを設定します。データビューにより、接続からのデータが適切に使用できるようになります。

1. データビューを設定し、上記で作成した接続をポイントしていることを確認します。

   詳しくは、*Adobe Customer Journey Analytics ガイド*&#x200B;の[データビューの作成または編集](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=ja){target=_blank}を参照してください。

1. [!DNL Customer Journey Analytics] の [!DNL Target] データを適切に表示するには、ルックアップデータセットから次のフィールドをディメンションとして追加する必要があります。

   * エクスペリエンス名
   * エクスペリエンス ID
   * アクティビティ名
   * アクティビティ ID

   ![Customer Journey Analytics の「名前」および「ID」オプション](/help/main/c-integrating-target-with-mac/cja4t/assets/names-and-ids.png){width="600" zoomable="yes"}

1. 他のフィールドの設定を終了し、完了したら「**[!UICONTROL 保存して続行]**」をクリックします。
