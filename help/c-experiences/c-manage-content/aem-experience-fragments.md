---
keywords: experience;json;aem;adobe experience manager;export to adobe target;experience fragments;fragments;XF
description: Adobe TargetアクティビティのAdobe Experience Manager(AEM)で作成したエクスペリエンスフラグメントを、最適化やパーソナライゼーションを支援するために使用する方法について説明します。
title: Adobe Experience Manager(AEM)Adobe Targetでの体験断片
feature: Experiences and Offers
translation-type: tm+mt
source-git-commit: 8110807a73e4d6d9848a52224db04faba033c98c
workflow-type: tm+mt
source-wordcount: '1111'
ht-degree: 20%

---


# AEM エクスペリエンスフラグメント

[!DNL Adobe Experience Manager] (AEM)で[!DNL Target]アクティビティーに作成したエクスペリエンスフラグメントを使用して、最適化やパーソナライゼーションを支援する方法について説明します。

>[!NOTE]
>
>この機能を使用するには、[!DNL Adobe Experience Manager] ([!DNL AEM])のお客様である必要があります。 詳しくは、以下の「[要件](/help/c-experiences/c-manage-content/aem-experience-fragments.md#section_AE6F0971E1574B3AA324003599B96E5A)」を参照してください。

## 概要 {#section_95A91830530F493B81C5C9CDB9B783EA}

[!DNL AEM]で[!DNL Target]アクティビティに作成されたエクスペリエンスフラグメントを使用すると、[!DNL AEM]の使いやすさと能力を[!DNL Target]の強力な自動インテリジェンス(AI)機能や機械学習(ML)機能と組み合わせて、エクスペリエンスを大規模にテストしパーソナライズできます。

[!DNL AEM] では、パーソナライゼーション戦略に生かせるよう、すべてのコンテンツとアセットが一元化されます。[!DNL AEM] コードを記述しなくても、デスクトップ、タブレットおよびモバイルデバイス用のコンテンツを1か所で簡単に作成できます。各デバイス用にページを作成する必要はありません。 [!DNL AEM] コンテンツを使用して各エクスペリエンスを自動的に調整します。

[!DNL Target] では、行動、コンテキスト、オフラインの変数を組み込んだルールベースの手法と AI 駆動の機械学習手法を組み合わせ、それを土台にしてパーソナライズされたエクスペリエンスを幅広く提供できます。[!DNL Target]を使用すると、[A/Bテスト](/help/c-activities/t-test-ab/test-ab.md)と[多変量分析](/help/c-activities/c-multivariate-testing/multivariate-testing.md)(MVT)アクティビティを簡単に設定して実行し、最適なオファー、コンテンツ、エクスペリエンスを判断できます。

エクスペリエンスフラグメントは、コンテンツ/エクスペリエンスの作成者と管理者を、[!DNL Target]を使用してビジネスの成果をもたらす最適化とパーソナライズの専門家と結び付けるための大きな一歩となります。

## 要件 {#section_AE6F0971E1574B3AA324003599B96E5A}

[!DNL Target]内でエクスペリエンスフラグメント機能を使用してプロビジョニングする必要があります。 また、適切なサービスパックまたは[!DNL AEM] 6.4 （またはそれ以降）と共に[!DNL AEM] 6.3を使用する必要があります。 アカウント担当者が、この機能を利用するための条件を満たすお手伝いをいたします。

* [!DNL Adobe Experience Manager] 6.4（以降）
* [!DNL Adobe Experience Manager] 6.3 SP2（以降）
* [!DNL Adobe Target Standard] または [!DNL Adobe Target Premium] アカウント
* [Adobe Targetカスタマーケア](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)に連絡して、統合を有効にし、認証の詳細を伝えます。

## [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}でのエクスペリエンスフラグメントの作成と設定

[!DNL AEM]エクスペリエンスフラグメントを[!DNL Target]で使用するには、次の手順を実行する必要があります。

### 手順1:[!DNL AEM]と[!DNL Target]を統合

詳しくは、次を参照してください。

* **[!DNL AEM]6.3**: [Adobe AnalyticsとAdobeの](https://docs.adobe.com/docs/en/aem/6-3/administer/integration/marketing-cloud/opt-in.html) Targeting( _Adobe Experience Manager6.3_ ドキュメント)のオプトイン
* **[!DNL AEM]6.4**: [Adobe AnalyticsとAdobeの](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/opt-in.html) Targeting( _Adobe Experience Manager6.4_ ドキュメント)のオプトイン
* **[!DNL AEM]6.5**: [Adobe AnalyticsとAdobeの](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/opt-in.html) Targeting( *Adobe Experience Manager6.5* ドキュメント)にオプトインします。

### 手順 2：エクスペリエンスフラグメントを作成する

エクスペリエンスフラグメントは[!DNL AEM]に作成されます。 詳しくは、次を参照してください。

* **[!DNL AEM]6.3**: [](https://docs.adobe.com/docs/en/aem/6-3/author/experience-fragments.html) Adobe Experience Manager6.3 ** ドキュメントのエクスペリエンスフラグメントを参照してください。
* **[!DNL AEM]6.4**: [](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/experience-fragments.html) Adobe Experience Manager6.4 ** ドキュメントのエクスペリエンスフラグメント。
* **[!DNL AEM]6.5**: [](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/experience-fragments.html) Adobe Experience Manager6.5のドキュメ *ントでエクスペリエンスのフラグメントを参照して* ください。

### 手順3:エクスペリエンスフラグメントを[!DNL Target]と共有するように[!DNL AEM]を設定

1. [!DNL AEM]内から、目的のエクスペリエンスフラグメントまたはそのフォルダーを含むフォルダーを選択し、「**[!UICONTROL プロパティ]**」をクリックします。
2. 「**[!UICONTROL クラウドサービス]**」タブをクリックし、**[!UICONTROL クラウドサービスの設定]**&#x200B;ドロップダウンリストから「**[!UICONTROL Adobe Target]**」を選択します。

   >[!NOTE]
   >
   >前の手順では、組織内の誰かが[!DNL Adobe Target]設定を作成したと想定しています。

3. 「**[!UICONTROL 保存して閉じる]**」をクリックします。

### 手順 4：エクスペリエンスフラグメントを発行し、 にエクスポートする[!DNL Target]

[!DNL AEM]のバージョンに応じて、次のリンクを参照して手順を確認してください。

* **[!DNL AEM]6.3**: [エクスペリエンスフラグメントの](https://helpx.adobe.com/experience-manager/6-3/sites/administering/using/experience-fragments-target.html) ターゲット設定への書き出し( *Adobe Experience Manager6.3* ドキュメント)
* **[!DNL AEM]6.4**: [エクスペリエンスフラグメントの](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html) ターゲット設定への書き出し( *Adobe Experience Manager6.4* ドキュメント)
* **[!DNL AEM]6.5**: [エクスペリエンスフラグメントの](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/experience-fragments-target.html) ターゲット設定への書き出し( *Adobe Experience Manager6.5* ドキュメント)

## ターゲットアクティビティでのエクスペリエンスフラグメントの使用{#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

前述のタスクを実行した後、エクスペリエンスフラグメントは[!DNL Target]の[!UICONTROL オファー]ページに表示されます。

>[!NOTE]
>
>[!DNL Target] は現在、読み込むエクスペリエンスフラグメントを 10 分ごとに検索します。読み込んだエクスペリエンスフラグメントは10分以内に[!DNL Target]で利用可能になりますが、今後はこの時間枠を短縮する必要があります。

>[!IMPORTANT]
>
>エクスペリエンスフラグメントは現在、HTMLオファーとして[!DNL Target]に読み込まれています。 エクスペリエンスフラグメント「プライマリ」バージョンは[!DNL AEM]に残ります。 [!DNL Target]内のエクスペリエンスフラグメントは編集できません。

リストー内のエクスペリエンスフラグメントの上にマウスポインターを置き、[!UICONTROL 表示]アイコン![表示アイコン](assets/icon_info.png)をクリックして、パブリックオファー配信URLと[!DNL AEM]パスを含む、エクスペリエンスフラグメントに関する追加情報を表示できます。

[Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md)(VEC)または[フォームベースのExperience Composer](/help/c-experiences/form-experience-composer.md)を使用して、[!DNL Target]アクティビティでエクスペリエンスフラグメントを使用できます。

>[!NOTE]
>
>[!DNL Target] AIとMLの機能を十分に活用するには、A/Bテストの作成時に「[自動配分](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)」または「[自動配分](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)」を選択します。

**VECを使用してエクスペリエンスフラグメントを使用するには：**

1. [!DNL Target]で、[Visual Experience Composer](/help/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)でエクスペリエンスを作成または編集中に、[!DNL AEM]コンテンツを挿入するページ上の場所をクリックし、[!UICONTROL エクスペリエンスフラグメントを選択]リストを表示するオプションを選択します。

   * [!UICONTROL 前に挿入]
   * [!UICONTROL 後ろに挿入]
   * [!UICONTROL エクスペリエンスフラグメントと置き換え]

   [!UICONTROL エクスペリエンスフラグメント]リストには、[!DNL AEM]で作成された、[!DNL Target]内でネイティブに利用可能になったすべてのコンテンツが表示されます。

   >[!NOTE]
   >
   >「[!UICONTROL エクスペリエンスフラグメントと交換]」オプションは、画像には使用できません。画像にこのオプションを使用する場合は、目的の画像を含むコンテナ要素をクリックします。

   ![](assets/experience_fragment_list.png)

1. 目的のエクスペリエンスフラグメントを選択し、**[!UICONTROL 完了]**&#x200B;をクリックします。
1. アクティビティの設定を終了します。

   各タイプのアクティビティを設定する方法について詳しくは、次のトピックを参照してください。

   * **A/B テスト：** [A/B テストの作成](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **自動配分：** [自動配分](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **自動ターゲット:** [自動ターゲット](/help/c-activities/auto-target/auto-target-to-optimize.md)
   * **自動パーソナライゼーションアクティビティ（AP）：**[自動パーソナライゼーションアクティビティの作成](/help/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **エクスペリエンスターゲット設定（XT）：** [エクスペリエンスのターゲット設定アクティビティの作成](/help/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **多変量分析テスト（MVT）：** [多変量分析テストの作成](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md#task_BF870FA60A8245AB8F0B775BE32EA710)
   * **Recommendations：** [Recommendations アクティビティの作成](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

**フォームベースのExperience Composerを使用してエクスペリエンスフラグメントを使用するには：**

1. [!DNL Target]で、[フォームベースのExperience Composer](/help/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)でエクスペリエンスを作成または編集中に、[!DNL AEM]コンテンツを挿入するページ上の場所を選択し、「**[!UICONTROL エクスペリエンスフラグメントを変更]**」を選択して、[!UICONTROL 「エクスペリエンスフラグメントを選択]」リストを表示します。

   ![](assets/experience_fragment_list.png)

   [!UICONTROL エクスペリエンスフラグメント]リストには、[!DNL AEM]で作成された、[!DNL Target]内でネイティブに利用可能になったすべてのコンテンツが表示されます。

1. 対象のエクスペリエンスフラグメントを選択し、「**[!UICONTROL 保存]**」をクリックします。
1. アクティビティの設定を終了します。

## 注意点 {#considerations}

* [!DNL Target] は現在、読み込むエクスペリエンスフラグメントを 10 分ごとに検索します。読み込んだエクスペリエンスフラグメントは10分以内に[!DNL Target]で利用可能になりますが、今後はこの時間枠を短縮する必要があります。
* エクスペリエンスフラグメントは現在、HTMLオファーとして[!DNL Target]に読み込まれています。 エクスペリエンスフラグメント「プライマリ」バージョンは[!DNL AEM]に残ります。 [!DNL Target]内のエクスペリエンスフラグメントは編集できません。
* JSONオファーをエクスペリエンスフラグメントとして[!DNL Target]に読み込むことができます。 ただし、これらのオファーはHTMLオファーとして読み込まれます。 JSONオファー（エクスペリエンスフラグメント）は、現在、[!DNL Target] UIで完全にはサポートされていません。
* AdobeI/Oを使用してエクスペリエンスフラグメントを作成することはできません。 上で説明したように、AEMを使用してエクスペリエンスフラグメントを作成する必要があります。

## トレーニングビデオ：AEMエクスペリエンスフラグメントとAdobe Target![チュートリアルバッジ](/help/assets/overview.png) {#section_C0EDC54063464F41A182492D2045BC64}の使用

次のビデオでは、エクスペリエンスフラグメントを設定して使用する方法を示します。

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>4:54で説明されている[!DNL AEM]ディープリンク機能は削除されました。

詳しくは、*AEM SitesのビデオとTutorials*&#x200B;ページの[Adobe Targetでのエクスペリエンスフラグメントの使用](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html)を参照してください。
