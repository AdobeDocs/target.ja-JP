---
keywords: cja4t;customer journey analytics;customer journey analytics for target;customer journey analytics レポートソース；target のレポートソースとしての customer journey analytics
description: ' [!DNL Adobe Customer Journey Analytics]  for  [!DNL Target] （A4T）を使用して、 [!DNL Customer Journey Analytics] コンバージョン指標およびオーディエンスセグメントに基づいた悪てティビティを作成し、 [!DNL Customer Journey Analytics]  レポートを使用して結果を調べます。'
title: 説明 [!DNL Adobe Customer Journey Analytics] 対象： [!DNL Target] (CJA4T)?
feature: Integrations
hide: true
hidefromtoc: true
source-git-commit: 13c899b656d9f15e7368d981ac25540c46caccb2
workflow-type: tm+mt
source-wordcount: '919'
ht-degree: 14%

---

# [!DNL Adobe Customer Journey Analytics] レポートソースとして [!DNL Adobe Target] (CJA4T)

The [!DNL Customer Journey Analytics for Target] (CJA4T) 統合 [Adobe Customer Journey Analytics (CJA)](https://experienceleague.adobe.com/docs/customer-journey-analytics.html){target=_blank} および [!DNL Target] は、最適化プログラム用の強力な分析および時間節約ツールを提供します。

を使用する主なメリット [!DNL Customer Journey Analytics] のデータ [!DNL Target] は次のとおりです。

* マーケターは動的に適用できます [!DNL Customer Journey Analytics] 成功指標 [!DNL Target] アクティビティレポートをいつでも作成できます。 アクティビティを実行する前にすべての項目を指定する必要がありません。
* 1 つのデータソースで、2 つの異なるシステムでデータを収集する場合に生じる相違を最小限に抑えます。

## 注意点

CJA4T 統合を使用する前に、次の情報を考慮してください。

* [!DNL Customer Journey Analytics] を [!DNL Target] のレポートソースとして使用するには、利用者および企業が [!DNL Customer Journey Analytics] と [!DNL Target] の両方にアクセスできる必要があります。どちらかのソリューションへのアクセス権が必要な場合は、組織の管理者またはアカウント担当者にお問い合わせください。
* 次の手順で、 [!DNL Target] アクティビティと [!DNL Customer Journey Analytics] レポートを作成するには、「[!UICONTROL 承認者]&quot;または&quot;[!UICONTROL 編集者]「 」の役割 [!DNL Target].
   * 次の場合、 [Target Standard](/help/main/c-intro/intro.md#section_ACD5EFF17AAB4E979CBEFA0145CCD905) アカウントについては、 [役割と権限の指定](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) in *ユーザー*.
   * 次の場合、 [Target Premium](/help/main/c-intro/intro.md#premium) アカウントについては、 [役割と権限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#roles-permissions) in *Enterprise ユーザーの権限*.

* 設定に応じて、レポートは、アクティビティごとまたは組織レベルで変更できます。 詳しくは、 [Reporting Cloud ソリューション](/help/main/administrating-target/reporting.md#solution) in *Target でのレポートの設定*.
* どちらか 1 つのレポートソースを選びます。1 つのアクティビティのデータを複数のレポートソースに対して収集することはできません。
* 次の場合、 [!DNL Customer Journey Analytics] レポートソースとして、レポート用のサンドボックスを指定するよう求められます。 設定時には、アクセス権のあるサンドボックスのみが表示されます。
* 任意の既存 [!DNL Target] アクティビティは引き続き使用 [!DNL Target] データ収集の影響を受けず、CJA4T を有効にしても影響を受けません。
* CJA4T は、 [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html){target=_blank} and [!DNL Target] implemented through the [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=ja){target=_blank}. のサポート [!DNL Analytics Data Connector] は将来の予定です。
* タイミングに関するご質問は、 [遅延に関する考慮事項](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html#latency){target=_blank} in *よくある質問* （内） *AdobeCustomer Analytics ガイド*.

## サポートされているアクティビティのタイプ {#supported-activities}

を使用する場合、次のアクティビティタイプがサポートされます [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=ja){target=_blank} or the [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/overview.html){target=_blank} JavaScript ライブラリ：

| アクティビティのタイプ | CJA4T との互換性 |
|--- |--- |
| [手動トラフィック分割を使用した A/B アクティビティ](/help/main/c-activities/t-test-ab/test-ab.md) | ○ |
| [自動配分を使用した A/B アクティビティ](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | × |
| [自動ターゲットを使用した A/B アクティビティ](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | × |
| [エクスペリエンスのターゲット設定（XT）](/help/main/c-activities/t-experience-target/experience-target.md) | ○ |
| [多変量分析テスト（MVT）](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | ○ |
| [Automated Personalization（AP）アクティビティ](/help/main/c-activities/t-automated-personalization/automated-personalization.md) | × |
| [Recommendations アクティビティ](/help/main/c-recommendations/recommendations.md) | ○ |

## を使用するアクティビティの作成 [!DNL Customer Journey Analytics] レポートソースとして

の作成 [!DNL Target] を使用するアクティビティ [!DNL Customer Journey Analytics] レポートソースは、通常の [!DNL Target] アクティビティ。

1. 次から： **[!UICONTROL アクティビティ]** リスト、クリック **[!UICONTROL アクティビティを作成]**&#x200B;を選択してから、( [上のサポートされているアクティビティグラフ](#supported-activities)) をクリックし、アクティビティの設定を開始します。
1. 次に、 **[!UICONTROL 目標と設定]** 3 ステップのアクティビティ作成ワークフローの「 」ページで、「 」を選択します。 **[!DNL Customer Journey Analytics]** を使用します。

   ![Customer Journey Analyticsをレポートソースオプションとして使用する](/help/main/c-integrating-target-with-mac/cja4t/assets/cja-as-reporting-source.png)

   >[!NOTE]
   >
   >レポートソースは、 [!DNL Target] アクティビティが有効になります。

1. サンドボックスを選択.

   このドロップダウンリストには、アクセス権のあるサンドボックスのみが表示されます。 アクセス権を持つ 1 つ以上のサンドボックスがリストにない場合は、サンドボックスへのアクセス権を持っていることを確認してください。 連絡先 [カスタマーケア](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) 問題が解決しない場合は、

   ![サンドボックスオプションを選択](/help/main/c-integrating-target-with-mac/cja4t/assets/sandbox.png)

1. アクティビティの目標を指定します。

   各アクティビティの目標として使用する成功指標を選択します。 次のいずれかを選択できます。 [!DNL Target] コンバージョン指標を使用するか、 [!DNL Customer Journey Analytics] 指標。

   ![「目標Customer Journey Analytics」の「指標」オプションを使用](/help/main/c-integrating-target-with-mac/cja4t/assets/goal-metric.png)

1. 「**[!UICONTROL 保存して閉じる]**」をクリックします。

## を設定します。 [!DNL Customer Journey Analytics] 接続

次の後： [!DNL Target] アクティビティが作成されたので、 [!DNL Customer Journey Analytics]. 既に接続が設定されている場合は、既存の接続を使用し、以下の手順 4 に進んでください。 接続が可能です [!DNL Customer Journey Analytics] をクリックして、レポート用のデータセットからのデータの取り込みを開始します。

1. In [!DNL Customer Journey Analytics]、 **[!UICONTROL 接続]** ページ、クリック **[!UICONTROL 新しい接続を作成]**.

   ![Customer Journey Analyticsで新しい接続リンクを作成](/help/main/c-integrating-target-with-mac/cja4t/assets/create-connection.png)

1. を設定します。 [接続とデータ設定](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/overview.html){target=_blank} 正しい情報を持つ
1. データストリームの設定時に使用したイベントデータセットを追加します。
1. 次を追加： **[!UICONTROL Adobe Target Classification Events]** 参照データセットを選択し、「 **[!UICONTROL 次へ]**.

   ![[Customer Journey Analytics] の [ データセットを追加 ] ダイアログボックス](/help/main/c-integrating-target-with-mac/cja4t/assets/add-datasets.png)

1. イベントデータセットを設定します。

   詳しくは、 [データセットの追加と設定](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en#add-dataset){target=_blank} in *接続の作成* （内） *Adobe Customer Journey Analyticsガイド*.

1. を使用してルックアップデータセットを設定します。 [!UICONTROL キー] フィールドに「key」、「一致するキー」フィールドに次のパスを入力します。

   ```
   _experience.decisioning.propositions.scopeDetails.correlationID
   ```

   ![Adobe Target ClassificationsCustomer Journey Analyticsの [Classifications] ダイアログボックス](/help/main/c-integrating-target-with-mac/cja4t/assets/classifications-events.png)

1. クリック **[!UICONTROL データセットを追加]**&#x200B;を選択し、次に **[!UICONTROL 保存]** 次の画面で、接続を完了します。

## データビューの設定

でのデータビューの設定 [!DNL Customer Journey Analytics]. データビューにより、接続のデータを適切に使用できるようになります。

1. データビューを設定し、上で作成した接続を指していることを確認します。

   詳しくは、 [データビューの作成または編集](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html){target=_blank} （内） *Adobe Customer Journey Analyticsガイド*.

1. 正しく表示するには、 [!DNL Target] のデータ [!DNL Customer Journey Analytics]に値を入力する場合は、ルックアップデータセットから次のフィールドをディメンションとして追加する必要があります。

   * エクスペリエンス名
   * エクスペリエンス ID
   * アクティビティ名
   * アクティビティ ID

   ![Customer Journey Analyticsの「名前」および「ID」オプション](/help/main/c-integrating-target-with-mac/cja4t/assets/names-and-ids.png){width="600" zoomable="yes"}

1. その他のフィールドの設定を完了し、「 **[!UICONTROL 保存して続行]** 完了したら、
