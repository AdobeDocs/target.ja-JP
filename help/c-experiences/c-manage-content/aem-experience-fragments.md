---
keywords: experience;json;aem;adobe experience manager;export to adobe target;experience fragments;fragments;XF
description: Adobe TargetアクティビティのAdobe Experience Manager(AEM)で作成したエクスペリエンスフラグメントを、最適化やパーソナライゼーションを支援するために使用する方法について説明します。
title: Adobe Experience Manager(AEM)Adobe Targetでの体験断片
feature: aem
topic: Standard
uuid: 4dc2b5da-524f-4d6a-8ffc-8c3ac78cb39e
translation-type: tm+mt
source-git-commit: e846109c476f98b4adc09d8b9dd2c2ef039b5ef7
workflow-type: tm+mt
source-wordcount: '1118'
ht-degree: 21%

---


# AEM エクスペリエンスフラグメント{#aem-experience-fragments}

Information about using experience fragments created in [!DNL Adobe Experience Manager] (AEM) in [!DNL Target] activities to aid optimization or personalization.

>[!NOTE]
>
>この機能を使用するには、 [!DNL Adobe Experience Manager] ([!DNL AEM])お客様である必要があります。 詳しくは、以下の「[要件](../../c-experiences/c-manage-content/aem-experience-fragments.md#section_AE6F0971E1574B3AA324003599B96E5A)」を参照してください。

## 概要 {#section_95A91830530F493B81C5C9CDB9B783EA}

Using experience fragments created in [!DNL AEM] in [!DNL Target] activities lets you combine the ease-of-use and power of [!DNL AEM] with powerful Automated Intelligence (AI) and Machine Learning (ML) capabilities in [!DNL Target] to test and personalize experiences at scale.

[!DNL AEM] では、パーソナライゼーション戦略に生かせるよう、すべてのコンテンツとアセットが一元化されます。[!DNL AEM] コードを記述しなくても、デスクトップ、タブレットおよびモバイルデバイス用のコンテンツを1か所で簡単に作成できます。 各デバイス用にページを作成する必要はありません。 [!DNL AEM] コンテンツを使用して各エクスペリエンスを自動的に調整します。

[!DNL Target] では、行動、コンテキスト、オフラインの変数を組み込んだルールベースの手法と AI 駆動の機械学習手法を組み合わせ、それを土台にしてパーソナライズされたエクスペリエンスを幅広く提供できます。With [!DNL Target] you can easily set up and run [A/B Test](/help/c-activities/t-test-ab/test-ab.md) and [Multivariate](/help/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) activities to determine the best offers, content, and experiences.

Experience fragments represent a huge step forward to link the content/experience creators and managers to the optimization and personalization professionals who are driving business outcomes using [!DNL Target].

## 要件 {#section_AE6F0971E1574B3AA324003599B96E5A}

You must be provisioned with the experience fragments functionality within [!DNL Target]. In addition, you must be using [!DNL AEM] 6.3 with the appropriate service pack or [!DNL AEM] 6.4 (or later). アカウント担当者が、この機能を利用するための条件を満たすお手伝いをいたします。

* [!DNL Adobe Experience Manager] 6.4（以降）
* [!DNL Adobe Experience Manager] 6.3 SP2（以降）
* [!DNL Adobe Target Standard] または [!DNL Adobe Target Premium] アカウントです。
* Contact [Adobe Target Customer Care](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) to enable the integration and to provide you with authentication details.

## Creating and configuring experience fragments in [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

In order to use [!DNL AEM] experience fragments in [!DNL Target], you must perform the following steps:

### 手順1:統合 [!DNL AEM] 対象 [!DNL Target]

詳しくは、次を参照してください。

* **[!DNL AEM]6.3**: [Adobe AnalyticsとAdobe Target](https://docs.adobe.com/docs/en/aem/6-3/administer/integration/marketing-cloud/opt-in.html) ( __ Adobe Experience Manager6.3ドキュメント)にオプトインする。
* **[!DNL AEM]6.4**: [Adobe AnalyticsとAdobe Target](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/opt-in.html) ( __ Adobe Experience Manager6.4ドキュメント)にオプトインする。
* **[!DNL AEM]6.5**: [Adobe AnalyticsとAdobe Target](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/opt-in.html) ( ** Adobe Experience Manager6.5ドキュメント)にオプトインする。

### 手順 2：エクスペリエンスフラグメントを作成する

Experience fragments are created in [!DNL AEM]. 詳しくは、次を参照してください。

* **[!DNL AEM]6.3**: [エクスペリエンスフラグメント](https://docs.adobe.com/docs/en/aem/6-3/author/experience-fragments.html) ( *Adobe Experience Manager6.3* ドキュメント)を参照してください。
* **[!DNL AEM]6.4**: [エクスペリエンスフラグメント](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/experience-fragments.html) ( *Adobe Experience Manager6.4* ドキュメント)を参照してください。
* **[!DNL AEM]6.5**: [エクスペリエンスフラグメント](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/experience-fragments.html) ( *Adobe Experience Manager6.5* ドキュメント)を参照してください。

### Step 3: Configure [!DNL AEM] to share the experience fragment with [!DNL Target]

1. From within [!DNL AEM], select the desired experience fragment or its containing folder, then click **[!UICONTROL Properties]**.
2. 「**[!UICONTROL クラウドサービス]**」タブをクリックし、**[!UICONTROL クラウドサービスの設定]**&#x200B;ドロップダウンリストから「**[!UICONTROL Adobe Target]**」を選択します。

   >[!NOTE]
   >
   >The previous step assumes that someone in your organization has created the [!DNL Adobe Target] configuration.

3. 「**[!UICONTROL 保存して閉じる]**」をクリックします。

### 手順 4：エクスペリエンスフラグメントを発行し、 にエクスポートする[!DNL Target]

使用している [!DNL AEM] バージョンに応じて、手順については次のリンクを参照してください。

* **[!DNL AEM]6.3**: [エクスペリエンスフラグメントのターゲット](https://helpx.adobe.com/experience-manager/6-3/sites/administering/using/experience-fragments-target.html) への書き出し( *Adobe Experience Manager6.3* ドキュメント)
* **[!DNL AEM]6.4**: [エクスペリエンスフラグメントのターゲット](https://docs.adobe.com/content/help/en/experience-manager-64/administering/integration/experience-fragments-target.html) への書き出し( *Adobe Experience Manager6.4* ドキュメント)
* **[!DNL AEM]6.5**: [エクスペリエンスフラグメントのターゲット](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/experience-fragments-target.html) への書き出し( *Adobe Experience Manager6.5* ドキュメント)

## Using experience fragments in Target activities {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

After performing the preceding tasks, the experience fragment displays on the [!UICONTROL Offers] page in [!DNL Target].

>[!NOTE]
>
>[!DNL Target] は現在、読み込むエクスペリエンスフラグメントを 10 分ごとに検索します。The imported experience fragment should be available in [!DNL Target] within ten minutes, but this time frame should shorten going forward.

>[!IMPORTANT]
>
>The experience fragment is currently imported into [!DNL Target] as an HTML offer. Note that the experience fragment &quot;primary&quot; version remains in [!DNL AEM]. You cannot edit the experience fragment in [!DNL Target].

リスト内のエクスペリエンスフラグメントの上にマウスポインターを置き、 [!UICONTROL 表示] アイコン ![表示アイコンをクリックして、公開オファー配信URLと](assets/icon_info.png)[!DNL AEM] パスを含む、エクスペリエンスフラグメントに関する追加情報を表示できます。

You can consume experience fragments in [!DNL Target] activities using the [Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) or the [Form-Based Experience Composer](/help/c-experiences/form-experience-composer.md).

>[!NOTE]
>
>To fully utilize the [!DNL Target] AI and ML functionality, you can select [Auto-Allocate](../../c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) or [Auto-Allocate](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) while creating an A/B Test.

**VECを使用してエクスペリエンスフラグメントを使用するには：**

1. で、 [!DNL Target]Visual Experience Composerでエクスペリエンスを作成または編集中に、 [コンテンツを挿入するページ上の場所をクリックし、目的のオプションを選択して「エクスペリエンスフラグメントを](../../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)選択 [!DNL AEM] 」リストを表示します。

   * [!UICONTROL 前に挿入]
   * [!UICONTROL 後ろに挿入]
   * [!UICONTROL エクスペリエンスフラグメントと置き換え]

   The [!UICONTROL Experience Fragment] list displays all of the content created in [!DNL AEM] that is now natively available from within [!DNL Target].

   >[!NOTE]
   >
   >「[!UICONTROL エクスペリエンスフラグメントと交換]」オプションは、画像には使用できません。画像にこのオプションを使用する場合は、目的の画像を含むコンテナ要素をクリックします。

   ![](assets/experience_fragment_list.png)

1. Select the desired experience fragment, then click **[!UICONTROL Done]**.
1. アクティビティの設定を終了します。

   各タイプのアクティビティを設定する方法について詳しくは、次のトピックを参照してください。

   * **A/B テスト：** [A/B テストの作成](../../c-activities/t-test-ab/t-test-create-ab/test-create-ab.md#task_68C8079BF9FF4625A3BD6680D554BB72)
   * **自動配分：** [自動配分](../../c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **自動ターゲット：** [パーソナライズされたエクスペリエンスの自動ターゲット](../../c-activities/auto-target-to-optimize.md#concept_67779E5B7F67427A97D7EA2A6FB919B3)
   * **自動パーソナライゼーションアクティビティ（AP）：**[自動パーソナライゼーションアクティビティの作成](../../c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **エクスペリエンスターゲット設定（XT）：** [エクスペリエンスのターゲット設定アクティビティの作成](../../c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **多変量分析テスト（MVT）：** [多変量分析テストの作成](../../c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md#task_BF870FA60A8245AB8F0B775BE32EA710)
   * **Recommendations：** [Recommendations アクティビティの作成](../../c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

**フォームベースのExperience Composerを使用してエクスペリエンスフラグメントを使用するには：**

1. In [!DNL Target], while creating or editing an experience in the [Form-Based Experience Composer](../../c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), select the location on the page where you want to insert [!DNL AEM] content, then select **[!UICONTROL Change Experience Fragment]** to display the [!UICONTROL Choose an Experience Fragment] list.

   ![](assets/experience_fragment_list.png)

   The [!UICONTROL Experience Fragment] list displays all of the content created in [!DNL AEM] that is now natively available from within [!DNL Target].

1. 対象のエクスペリエンスフラグメントを選択し、「**[!UICONTROL 保存]**」をクリックします。
1. アクティビティの設定を終了します。

## 注意点 {#considerations}

* [!DNL Target] は現在、読み込むエクスペリエンスフラグメントを 10 分ごとに検索します。The imported experience fragment should be available in [!DNL Target] within ten minutes, but this time frame should shorten going forward.
* The experience fragment is currently imported into [!DNL Target] as an HTML offer. Note that the experience fragment &quot;primary&quot; version remains in [!DNL AEM]. You cannot edit the experience fragment in [!DNL Target].
* JSONオファーをエクスペリエンスフラグメントとしてに読み込むことができ [!DNL Target]ます。 ただし、これらのオファーはHTMLオファーとして読み込まれます。 JSONオファー（エクスペリエンスフラグメント）は、現在、 [!DNL Target] UIで完全にはサポートされていません。
* AdobeI/Oを使用してエクスペリエンスフラグメントを作成することはできません。 上で説明したように、AEMを使用してエクスペリエンスフラグメントを作成する必要があります。

## Training video: Using AEM experience fragments with Adobe Target ![Tutorial badge](/help/assets/overview.png) {#section_C0EDC54063464F41A182492D2045BC64}

次のビデオでは、エクスペリエンスフラグメントを設定して使用する方法を示します。

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>4:54で説明されている [!DNL AEM] ディープリンク機能は削除されました。

詳しくは、 [AEM SitesのビデオとTutorials](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html) ページの「Adobe Targetでのエクスペリエンスフラグメントの ** 使用」を参照してください。
