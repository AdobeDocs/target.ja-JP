---
keywords: エクスペリエンス;json;AEM, Adobe Experience Manager;Adobe Target へのエクスポート;エクスペリエンスフラグメント;フラグメント;XF
description: 使用方法を学ぶ [!DNL Adobe Experience Manager] のエクスペリエンスフラグメント [!DNL Adobe Target] アクティビティ。
title: 使用方法 [!DNL Adobe Experience Manager] (AEM) エクスペリエンスフラグメント？
feature: Experiences and Offers
exl-id: 3dd811a4-c7be-443d-a5ad-5b9adcaf1a2c
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '1379'
ht-degree: 51%

---

# AEM エクスペリエンスフラグメント

で作成したエクスペリエンスフラグメントを使用する [!DNL Adobe Experience Manager] (AEM) [!DNL Target] アクティビティを活用して、最適化やパーソナライゼーションを支援します。

>[!NOTE]
>
>この機能を使用するには、 [!DNL Adobe Experience Manager] (AEM) 顧客。 詳しくは、 [要件](#section_AE6F0971E1574B3AA324003599B96E5A) 下

で作成したエクスペリエンスフラグメントを使用する [!DNL AEM] in [!DNL Target] 「 」アクティビティでは、使いやすさと優れた機能を組み合わせることができます。 [!DNL AEM] に強力な人工知能 (AI) と機械学習 (ML) 機能を搭載 [!DNL Target] 大規模にエクスペリエンスをテストし、パーソナライズする。

[!DNL AEM] では、パーソナライゼーション戦略に生かせるよう、すべてのコンテンツとアセットが一元化されます。[!DNL AEM] では、コードを記述しなくても、デスクトップ、タブレット、モバイルデバイス向けのコンテンツを 1 か所で簡単に作成できます。デバイスごとにページを作成する必要はありません。 [!DNL AEM] は、コンテンツを使用して各エクスペリエンスを自動的に調整します。

[!DNL Target] では、行動、コンテキスト、オフラインの変数を組み込んだルールベースの手法と AI 駆動の機械学習手法を組み合わせ、それを土台にしてパーソナライズされたエクスペリエンスを幅広く提供できます。を使用 [!DNL Target]を使用すると、簡単にセットアップして [A/B テスト](/help/main/c-activities/t-test-ab/test-ab.md) および [多変量分析](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) アクティビティを使用して最適なオファー、コンテンツ、エクスペリエンスを決定する。

エクスペリエンスフラグメントは、コンテンツ／エクスペリエンスの作成者と管理者を、[!DNL Target] を使用してビジネス成果を高める最適化／パーソナライゼーションの専門家と連携させる大きな一歩になります。

## 要件 {#section_AE6F0971E1574B3AA324003599B96E5A}

[!DNL Target] 内でエクスペリエンスフラグメント機能のプロビジョニングが行われている必要があります。また、 [!DNL AEM] as a Cloud Serviceまたは [!DNL AEM] 6.4（以降） アカウント担当者が、この機能を利用するための条件を満たすお手伝いをいたします。

* [!DNL Adobe Experience Manager ] as a Cloud Service
* [!DNL Adobe Experience Manager] 6.5.
* [!DNL Adobe Experience Manager] 6.4.
* [!DNL Adobe Target Standard] または [!DNL Adobe Target Premium] アカウント

>[!NOTE]
>
>[!DNL Adobe Experience Manager] 6.3 および 6.4 は提供終了となり、サポート対象外になりました（拡張サポートを購入したお客様を除く）。

統合の有効化と認証の詳細情報については、[Adobe Target カスタマーケア](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)にお問い合わせください。

## [!DNL AEM] でのエクスペリエンスフラグメントの作成と設定 {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

[!DNL AEM] エクスペリエンスフラグメントを [!DNL Target] で使用するには、次の手順を実行する必要があります。

### 手順 1：[!DNL AEM] と [!DNL Target] を統合する

詳しくは、次を参照してください。

* **AEMas a Cloud Service**: [Adobe Targetとの統合](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/integrating-adobe-target.html){target=_blank} *Experience Manageras a Cloud Service* ガイド。
* **Adobe I/O**: [AdobeI/0 を使用したAdobe Targetとの統合](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-ims-adobe-io.html?lang=ja){target=_blank} *管理ユーザーガイド* ドキュメント。
* **[!DNL AEM]6.5**: [Adobe AnalyticsとAdobe Targetのオプトイン](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=ja){target=_blank} *Adobe Experience Manager 6.5* ドキュメント。
* **[!DNL AEM]6.4**: [Adobe AnalyticsとAdobe Targetのオプトイン](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html?lang=ja){target=_blank} *Adobe Experience Manager 6.4* ドキュメント。

### 手順 2：エクスペリエンスフラグメントを作成する

エクスペリエンスフラグメントは [!DNL AEM] で作成されます。詳しくは、次を参照してください。

* **AEMas a Cloud Service**: [エクスペリエンスフラグメント](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/experience-fragments.html?lang=en){target=_blank} *Experience Manageras a Cloud Service* ガイド。
* **[!DNL AEM]6.5**: [エクスペリエンスフラグメント](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/authoring/experience-fragments.html?lang=ja){target=_blank} *Adobe Experience Manager 6.5* ドキュメント。
* **[!DNL AEM]6.4**: [エクスペリエンスフラグメント](https://experienceleague.adobe.com/docs/experience-manager-64/authoring/authoring/experience-fragments.html?lang=ja){target=_blank} *Adobe Experience Manager 6.4* ドキュメント。

### 手順 3：エクスペリエンスフラグメントを [!DNL Target] と共有するように [!DNL AEM] を設定する

1. [!DNL AEM] 内で目的のエクスペリエンスフラグメントまたはそれが含まれるフォルダーを選択し、「**[!UICONTROL プロパティ]**」をクリックします。
2. 「**[!UICONTROL クラウドサービス]**」タブをクリックし、**[!UICONTROL クラウドサービスの設定]**&#x200B;ドロップダウンリストから「**[!UICONTROL Adobe Target]**」を選択します。

   >[!NOTE]
   >
   >前の手順では、組織内のユーザーが [!DNL Adobe Target] 設定を既に作成していることを前提としています。

3. 「**[!UICONTROL 保存して閉じる]**」をクリックします。

### 手順 4：エクスペリエンスフラグメントを発行し、 にエクスポートする[!DNL Target]

[!DNL AEM] のバージョンに応じて、次のリンクを参照して手順を確認してください。

* **AEMas a Cloud Service**: [エクスペリエンスフラグメントのAdobe Targetへの書き出し](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/experience-fragments-target.html?lang=en){target=_blank} *Experience Manageras a Cloud Service* ガイド。
* **[!DNL AEM]6.5**: [エクスペリエンスフラグメントの Target への書き出し](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/experience-fragments-target.html?lang=en){target=_blank} *Adobe Experience Manager 6.5* ドキュメント。
* **[!DNL AEM]6.4**: [エクスペリエンスフラグメントの Target への書き出し](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html?lang=ja){target=_blank} *Adobe Experience Manager 6.4* ドキュメント。

## [!DNL Target] アクティビティでのエクスペリエンスフラグメントの使用 {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

上記のタスクを実行すると、エクスペリエンスフラグメントが [!DNL Target] の[!UICONTROL オファー]ページに表示されます。

>[!NOTE]
>
>* [!DNL Target] は現在、読み込むエクスペリエンスフラグメントを 10 分ごとに検索します。インポートされたエクスペリエンスフラグメントは 10 分以内に [!DNL Target] で使用可能になります。ただし、この時間は今後短縮される予定です。
>
>* エクスペリエンスフラグメントが [!DNL Target] をHTMLまたは JSON オファーとして設定する。 そのエクスペリエンスフラグメントの「プライマリ」バージョンは、 [!DNL AEM]. [!DNL Target] 内のエクスペリエンスフラグメントは編集できません。


リスト内のエクスペリエンスフラグメントにカーソルを合わせ、[!UICONTROL 表示]アイコン（![表示アイコン](assets/icon_info.png)）をクリックして、公開オファー配信 URL やその [!DNL AEM] パスなど、エクスペリエンスフラグメントに関する追加情報を表示できます。

[Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md)（VEC）または[フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) を使用して、[!DNL Target] アクティビティでエクスペリエンスフラグメントを使用できます。

>[!NOTE]
>
>を完全に使用するには [!DNL Target] AI および ML 機能では、 [自動配分](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) または [自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md) をクリックします。
>
>エクスペリエンスフラグメントは、 [!DNL Recommendations] アクティビティ。 ただし、レコメンデーションでエクスペリエンスフラグメントを使用するには、 [!UICONTROL A/B テスト] アクティビティ ( [!UICONTROL 自動配分] および [!UICONTROL 自動ターゲット]) または [!UICONTROL エクスペリエンスのターゲット設定] (XT) アクティビティと [レコメンデーションをオファーとして含める](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

**VEC を使用してエクスペリエンスフラグメントを使用するには：**

1. [!DNL Target] の [Visual Experience Composer](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D) でエクスペリエンスを作成または編集する際に、[!DNL AEM] コンテンツを挿入するページ上の場所をクリックし、目的のオプションを選択して「[!UICONTROL エクスペリエンスフラグメントを選択]」リストを表示します。

   * [!UICONTROL 前に挿入]
   * [!UICONTROL 後ろに挿入]
   * [!UICONTROL エクスペリエンスフラグメントに置き換え]

   この [!UICONTROL エクスペリエンスフラグメント] リストには、 [!DNL AEM] 現在は、内からネイティブで利用可能です。 [!DNL Target].

   >[!NOTE]
   >
   >「[!UICONTROL エクスペリエンスフラグメントと交換]」オプションは、画像には使用できません。画像にこのオプションを使用する場合は、目的の画像を含むコンテナ要素をクリックします。

   ![experience_fragment_list 画像](assets/experience_fragment_list.png)

1. 目的のエクスペリエンスフラグメントを選択し、「**[!UICONTROL 完了]**」をクリックします。
1. アクティビティの設定を終了します。

   各タイプのアクティビティを設定する方法について詳しくは、次のトピックを参照してください。

   * **A/B テスト：** [A/B テストの作成](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **自動配分：** [自動配分](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **自動ターゲット：** [自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * **自動パーソナライゼーションアクティビティ（AP）：**[自動パーソナライゼーションアクティビティの作成](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **エクスペリエンスターゲット設定（XT）：** [エクスペリエンスのターゲット設定アクティビティの作成](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **多変量分析テスト（MVT）：** [多変量分析テストの作成](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md#task_BF870FA60A8245AB8F0B775BE32EA710)
   * **Recommendations：** [Recommendations アクティビティの作成](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

>[!NOTE]
>
>で JSON 形式で書き出されたエクスペリエンスフラグメント [!DNL Target] は、VEC を使用して作成されたアクティビティでは使用できません。VEC ベースのアクティビティでは、HTMLエクスペリエンスフラグメントのみがサポートされます。 JSON エクスペリエンスフラグメントを使用する場合は、 [フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md).

**フォームベースの Experience Composer を使用してエクスペリエンスフラグメントを使用するには：**

1. [!DNL Target] の[フォームベース Experience Composer](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) でエクスペリエンスを作成または編集する際に、[!DNL AEM] コンテンツを挿入するページ上の場所を選択し、「**[!UICONTROL エクスペリエンスフラグメントを変更]**」を選択して「[!UICONTROL エクスペリエンスフラグメントを選択]」リストを表示します。

   ![experience_fragment_list 画像](assets/experience_fragment_list.png)

   この [!UICONTROL エクスペリエンスフラグメント] リストには、 [!DNL AEM] 現在は、内からネイティブで利用可能です。 [!DNL Target].

1. 対象のエクスペリエンスフラグメントを選択し、「**[!UICONTROL 保存]**」をクリックします。
1. アクティビティの設定を終了します。

## 注意点 {#considerations}

* [!DNL Target] は現在、読み込むエクスペリエンスフラグメントを 10 分ごとに検索します。インポートされたエクスペリエンスフラグメントは 10 分以内に [!DNL Target] で使用可能になります。ただし、この時間は今後短縮される予定です。
* エクスペリエンスフラグメントが [!DNL Target] をHTMLまたは JSON オファーとして設定する。 エクスペリエンスフラグメントの「プライマリ」バージョンは、 [!DNL AEM]. [!DNL Target] 内のエクスペリエンスフラグメントは編集できません。
* エクスペリエンスフラグメントを作成するには、 [!DNL Adobe I/O]. 前述のように、AEMを使用してエクスペリエンスフラグメントを作成します。
* AEMでエクスペリエンスフラグメントを更新する場合は、エクスペリエンスフラグメントを公開し、に書き出す必要があります。 [!DNL Target] 再び [!DNL Target] では、最新の変更を使用できます。

## Target に書き出したエクスペリエンスフラグメントから ClientLibs と不要な HTML を削除する

エクスペリエンスフラグメントオファーを [!DNL Target] AEMが配信するページでは、ターゲットページに必要なすべてのクライアントライブラリが既に含まれています。 また、不要なHTML要素もオファーに含める必要はありません。

HTMLページ全体がエクスペリエンスフラグメントをラップして問題を引き起こす場合があります。 エクスペリエンスフラグメントが小さなHTMLであり、HTML、HEAD、本文などを含む完全なHTMLページではないことを確認します。

詳しくは、次のブログ投稿を参照してください。 [AEM 6.5:Target に書き出したエクスペリエンスフラグメントからの ClientLibs の削除](https://www.linkedin.com/pulse/aem-65-removing-clientlibs-from-experience-fragments-exported-haser){target=_blank}。

## トレーニングビデオ：でのAEMエクスペリエンスフラグメントの使用 [!DNL Adobe Target]

次のビデオでは、エクスペリエンスフラグメントの設定方法と使用方法を示します。

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>4:54 で取り上げた [!DNL AEM] ディープリンク機能は削除されました。

詳しくは、 [Adobe Targetでのエクスペリエンスフラグメントの使用](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html?lang=ja) の *AEM SitesのビデオとTutorials* ページ。
