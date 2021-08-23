---
keywords: エクスペリエンス；json;AEM;Adobe Experience Manager;Adobe Targetへの書き出し；エクスペリエンスフラグメント；フラグメント；XF
description: Adobe [!DNL Target] アクティビティでAEMエクスペリエンスフラグメントを使用する方法を説明します。 AEMの使いやすさと機能を、 [!DNL Target]の強力なAIおよびML機能と組み合わせます。
title: Adobe Experience Manager(AEM)エクスペリエンスフラグメントの使用方法を教えてください。
feature: エクスペリエンスとオファー
exl-id: 3dd811a4-c7be-443d-a5ad-5b9adcaf1a2c
source-git-commit: 0437d7c83734ee707d4d42996d856f9e19416c3d
workflow-type: tm+mt
source-wordcount: '1147'
ht-degree: 21%

---

# AEM エクスペリエンスフラグメント

[!DNL Adobe Experience Manager](AEM)で作成したエクスペリエンスフラグメントを[!DNL Target]アクティビティで使用して、最適化やパーソナライゼーションを支援する方法について説明します。

>[!NOTE]
>
>この機能を使用するには、[!DNL Adobe Experience Manager] ([!DNL AEM])のお客様である必要があります。 詳しくは、以下の「[要件](/help/c-experiences/c-manage-content/aem-experience-fragments.md#section_AE6F0971E1574B3AA324003599B96E5A)」を参照してください。

## 概要 {#section_95A91830530F493B81C5C9CDB9B783EA}

[!DNL AEM]で作成したエクスペリエンスフラグメントを[!DNL Target]アクティビティで使用すると、[!DNL AEM]の使いやすさと機能を、[!DNL Target]の強力な自動インテリジェンス(AI)機能と機械学習(ML)機能と組み合わせて、エクスペリエンスを大規模にテストおよびパーソナライズできます。

[!DNL AEM] では、パーソナライゼーション戦略に生かせるよう、すべてのコンテンツとアセットが一元化されます。[!DNL AEM] では、コードを記述しなくても、デスクトップ、タブレット、モバイルデバイス向けのコンテンツを 1 か所で簡単に作成できます。すべてのデバイスでページを作成する必要はありません。 [!DNL AEM] は、コンテンツを使用して各エクスペリエンスを自動的に調整します。

[!DNL Target] では、行動、コンテキスト、オフラインの変数を組み込んだルールベースの手法と AI 駆動の機械学習手法を組み合わせ、それを土台にしてパーソナライズされたエクスペリエンスを幅広く提供できます。[!DNL Target]では、[A/Bテスト](/help/c-activities/t-test-ab/test-ab.md)および[多変量分析](/help/c-activities/c-multivariate-testing/multivariate-testing.md)(MVT)アクティビティを簡単に設定して実行し、最適なオファー、コンテンツ、エクスペリエンスを決定できます。

エクスペリエンスフラグメントは、コンテンツ/エクスペリエンスの作成者と管理者を、ビジネス成果の向上に[!DNL Target]を使用する最適化/パーソナライゼーションの専門家と結び付ける大きな一歩となります。

## 要件 {#section_AE6F0971E1574B3AA324003599B96E5A}

[!DNL Target]内でエクスペリエンスフラグメント機能のプロビジョニングをおこなう必要があります。 また、適切なサービスパックまたは[!DNL AEM] 6.4（またはそれ以降）と[!DNL AEM] 6.3を使用する必要があります。 アカウント担当者が、この機能を利用するための条件を満たすお手伝いをいたします。

* [!DNL Adobe Experience Manager] 6.4（以降）
* [!DNL Adobe Experience Manager] 6.3 SP2（以降）
* [!DNL Adobe Target Standard] またはア [!DNL Adobe Target Premium] カウント
* [Adobe Targetカスタマーケア](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)に連絡して統合を有効にし、認証の詳細を伝えてください。

## [!DNL AEM]でのエクスペリエンスフラグメントの作成と設定 {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

[!DNL Target]で[!DNL AEM]エクスペリエンスフラグメントを使用するには、次の手順を実行する必要があります。

### 手順1:[!DNL AEM]と[!DNL Target]を統合する

詳しくは、次を参照してください。

* **Adobe I/O**: [『管理ユーザガイド』のドキュメントで、AdobeI/0を使用したAdobe Targetとの統](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-ims-adobe-io.html) 合につ __ いて説明します。
* **[!DNL AEM]6.3**: [Adobe AnalyticsとAdobeのターゲ](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html) ット設定( _Adobe Experience Manager 6.3_ ドキュメント)
* **[!DNL AEM]6.4**: [Adobe AnalyticsとAdobeのターゲ](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html) ット設定( _Adobe Experience Manager 6.4_ ドキュメント)
* **[!DNL AEM]6.5**: [Adobe AnalyticsとAdobeのターゲ](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=en) ット設定( *Adobe Experience Manager 6.5* ドキュメント)

### 手順 2：エクスペリエンスフラグメントを作成する

エクスペリエンスフラグメントは[!DNL AEM]内に作成されます。 詳しくは、次を参照してください。

* **[!DNL AEM]6.3**: [エクスペ](https://experienceleague.adobe.com/docs/) リエンスフラグメ *ント(Adobe Experience Manager 6.3* のドキュメント)
* **[!DNL AEM]6.4**: [エクスペ](https://experienceleague.adobe.com/docs/) リエンスフラグメ *ント(Adobe Experience Manager 6.4* ドキュメント)
* **[!DNL AEM]6.5**: [エクスペ](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/experience-fragments.html) リエンスフラグメ *ント(Adobe Experience Manager 6.5* のドキュメント)

### 手順3:[!DNL AEM]を設定して、エクスペリエンスフラグメントを[!DNL Target]と共有します

1. [!DNL AEM]内から、目的のエクスペリエンスフラグメントまたはその含まれるフォルダーを選択し、「**[!UICONTROL プロパティ]**」をクリックします。
2. 「**[!UICONTROL クラウドサービス]**」タブをクリックし、**[!UICONTROL クラウドサービスの設定]**&#x200B;ドロップダウンリストから「**[!UICONTROL Adobe Target]**」を選択します。

   >[!NOTE]
   >
   >前の手順は、組織内のユーザーが[!DNL Adobe Target]設定を作成したことを前提としています。

3. 「**[!UICONTROL 保存して閉じる]**」をクリックします。

### 手順 4：エクスペリエンスフラグメントを発行し、 にエクスポートする[!DNL Target]

[!DNL AEM]のバージョンに応じて、次のリンクを参照して手順を確認してください。

* **[!DNL AEM]6.3**: [](https://helpx.adobe.com/experience-manager/6-3/sites/administering/using/experience-fragments-target.html) Adobe Experience Manager 6.3のドキュメントで、エクスペリエ *ンスフラグメ* ントをTargetに書き出す。
* **[!DNL AEM]6.4**: [エクスペリエンスフラグメントを](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html) Adobe Experience Manager 6.4の *ドキュメントでTargetに書き出* す。
* **[!DNL AEM]6.5**: [エクスペリエンスフラグメントの](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/experience-fragments-target.html) Targetへの書き出し( *Adobe Experience Manager 6.5* ドキュメント)

## [!DNL Target]アクティビティでのエクスペリエンスフラグメントの使用 {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

上記のタスクを実行すると、エクスペリエンスフラグメントが[!DNL Target]の[!UICONTROL オファー]ページに表示されます。

>[!NOTE]
>
>[!DNL Target] は現在、読み込むエクスペリエンスフラグメントを 10 分ごとに検索します。読み込まれたエクスペリエンスフラグメントは、10分以内に[!DNL Target]で利用できるはずですが、今後はこの時間が短縮されます。

>[!IMPORTANT]
>
>エクスペリエンスフラグメントは現在、HTMLオファーとして[!DNL Target]に読み込まれます。 エクスペリエンスフラグメントの「プライマリ」バージョンは[!DNL AEM]に残ります。 [!DNL Target]内のエクスペリエンスフラグメントは編集できません。

リスト内のエクスペリエンスフラグメントの上にマウスポインターを置き、[!UICONTROL 表示]アイコン![表示アイコン](assets/icon_info.png)をクリックして、公開オファー配信URLと[!DNL AEM]パスを含むエクスペリエンスフラグメントに関する追加情報を表示できます。

[Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md)(VEC)または[フォームベースのExperience Composer](/help/c-experiences/form-experience-composer.md)を使用して、[!DNL Target]アクティビティでエクスペリエンスフラグメントを使用できます。

>[!NOTE]
>
>[!DNL Target] AI機能とML機能を最大限に活用するには、A/Bテストの作成時に、「[自動配分](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)」または「[自動配分](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)」を選択します。

**VECを使用してエクスペリエンスフラグメントを使用するには：**

1. [!DNL Target]で、[Visual Experience Composer](/help/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)でエクスペリエンスを作成または編集する際に、[!DNL AEM]コンテンツを挿入するページ上の場所をクリックし、目的のオプションを選択して「[!UICONTROL エクスペリエンスフラグメント]を選択」リストを表示します。

   * [!UICONTROL 前に挿入]
   * [!UICONTROL 後ろに挿入]
   * [!UICONTROL エクスペリエンスフラグメントとの置き換え]

   [!UICONTROL エクスペリエンスフラグメント]リストに、[!DNL AEM]で作成され、[!DNL Target]内からネイティブで利用できるようになったコンテンツがすべて表示されます。

   >[!NOTE]
   >
   >「[!UICONTROL エクスペリエンスフラグメントと交換]」オプションは、画像には使用できません。画像にこのオプションを使用する場合は、目的の画像を含むコンテナ要素をクリックします。

   ![](assets/experience_fragment_list.png)

1. 目的のエクスペリエンスフラグメントを選択し、「**[!UICONTROL 完了]**」をクリックします。
1. アクティビティの設定を終了します。

   各タイプのアクティビティを設定する方法について詳しくは、次のトピックを参照してください。

   * **A/B テスト：** [A/B テストの作成](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **自動配分：** [自動配分](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **自動ターゲット：** [自動ターゲット](/help/c-activities/auto-target/auto-target-to-optimize.md)
   * **自動パーソナライゼーションアクティビティ（AP）：**[自動パーソナライゼーションアクティビティの作成](/help/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **エクスペリエンスターゲット設定（XT）：** [エクスペリエンスのターゲット設定アクティビティの作成](/help/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **多変量分析テスト（MVT）：** [多変量分析テストの作成](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md#task_BF870FA60A8245AB8F0B775BE32EA710)
   * **Recommendations：** [Recommendations アクティビティの作成](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

**フォームベースのExperience Composerを使用してエクスペリエンスフラグメントを使用するには：**

1. [!DNL Target]で、[フォームベースのExperience Composer](/help/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)でエクスペリエンスを作成または編集する際に、[!DNL AEM]コンテンツを挿入するページ上の場所を選択し、「**[!UICONTROL エクスペリエンスフラグメントを変更]**」を選択して[!UICONTROL エクスペリエンスフラグメントを選択します。]

   ![](assets/experience_fragment_list.png)

   [!UICONTROL エクスペリエンスフラグメント]リストに、[!DNL AEM]で作成され、[!DNL Target]内からネイティブで利用できるようになったコンテンツがすべて表示されます。

1. 対象のエクスペリエンスフラグメントを選択し、「**[!UICONTROL 保存]**」をクリックします。
1. アクティビティの設定を終了します。

## 注意点 {#considerations}

* [!DNL Target] は現在、読み込むエクスペリエンスフラグメントを 10 分ごとに検索します。読み込まれたエクスペリエンスフラグメントは、10分以内に[!DNL Target]で利用できるはずですが、今後はこの時間が短縮されます。
* エクスペリエンスフラグメントは現在、HTMLオファーとして[!DNL Target]に読み込まれます。 エクスペリエンスフラグメントの「プライマリ」バージョンは[!DNL AEM]に残ります。 [!DNL Target]内のエクスペリエンスフラグメントは編集できません。
* JSONオファーをエクスペリエンスフラグメントとして[!DNL Target]に読み込むことができます。 ただし、これらのオファーはHTMLオファーとしてインポートされます。 JSONオファー（エクスペリエンスフラグメント）は、現在、[!DNL Target] UIでは完全にはサポートされていません。
* エクスペリエンスフラグメントは、AdobeI/Oを使用して作成できません。 前述のように、AEMを使用してエクスペリエンスフラグメントを作成する必要があります。

## トレーニングビデオ：Adobe Target ![チュートリアルバッジ](/help/assets/overview.png)でのAEMエクスペリエンスフラグメントの使用 {#section_C0EDC54063464F41A182492D2045BC64}

次のビデオでは、エクスペリエンスフラグメントの設定方法と使用方法を示します。

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>4:54で説明されている[!DNL AEM]ディープリンク機能は削除されました。

詳しくは、*AEM SitesのビデオとTutorials*&#x200B;ページの[Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html)でのエクスペリエンスフラグメントの使用を参照してください。
