---
keywords: エクスペリエンス;json;AEM, Adobe Experience Manager;Adobe Target へのエクスポート;エクスペリエンスフラグメント;フラグメント;XF
description: Adobe  [!DNL Target]  アクティビティで AEM エクスペリエンスフラグメントを使用する方法を説明します。AEM の使いやすさと機能を、 [!DNL Target] の強力な AI 機能および ML 機能と組み合わせます。
title: Adobe Experience Manager（AEM）エクスペリエンスフラグメントの使用方法
feature: Experiences and Offers
exl-id: 3dd811a4-c7be-443d-a5ad-5b9adcaf1a2c
source-git-commit: 0d5d31a421acb595702e6420c74e969124cc3daf
workflow-type: ht
source-wordcount: '1125'
ht-degree: 100%

---

# AEM エクスペリエンスフラグメント

[!DNL Adobe Experience Manager]（AEM）で作成したエクスペリエンスフラグメントを [!DNL Target] アクティビティで使用して最適化やパーソナライズを支援する方法について説明します。

>[!NOTE]
>
>この機能を使用するには、[!DNL Adobe Experience Manager]（[!DNL AEM]）の顧客である必要があります。 詳しくは、以下の「[要件](/help/c-experiences/c-manage-content/aem-experience-fragments.md#section_AE6F0971E1574B3AA324003599B96E5A)」を参照してください。

## 概要 {#section_95A91830530F493B81C5C9CDB9B783EA}

[!DNL AEM] で作成したエクスペリエンスフラグメントを [!DNL Target] アクティビティで使用すると、[!DNL AEM] の使いやすさと機能を、[!DNL Target] の強力な自動インテリジェンス（AI）機能および機械学習（ML）機能と組み合わせて、エクスペリエンスを大規模にテストおよびパーソナライズできます。

[!DNL AEM] では、パーソナライゼーション戦略に生かせるよう、すべてのコンテンツとアセットが一元化されます。[!DNL AEM] では、コードを記述しなくても、デスクトップ、タブレット、モバイルデバイス向けのコンテンツを 1 か所で簡単に作成できます。デバイスごとにページを作成する必要はありません。 [!DNL AEM] は、コンテンツを使用して各エクスペリエンスを自動的に調整します。

[!DNL Target] では、行動、コンテキスト、オフラインの変数を組み込んだルールベースの手法と AI 駆動の機械学習手法を組み合わせ、それを土台にしてパーソナライズされたエクスペリエンスを幅広く提供できます。[!DNL Target] では、[A/B テスト](/help/c-activities/t-test-ab/test-ab.md)および[多変量分析](/help/c-activities/c-multivariate-testing/multivariate-testing.md)（MVT）アクティビティを簡単に設定および実行して、最適なオファー、コンテンツおよびエクスペリエンスを決定できます。

エクスペリエンスフラグメントは、コンテンツ／エクスペリエンスの作成者と管理者を、[!DNL Target] を使用してビジネス成果を高める最適化／パーソナライゼーションの専門家と連携させる大きな一歩になります。

## 要件 {#section_AE6F0971E1574B3AA324003599B96E5A}

[!DNL Target] 内でエクスペリエンスフラグメント機能のプロビジョニングが行われている必要があります。また、適切なサービスパックが適用された [!DNL AEM] 6.3 か、[!DNL AEM] 6.4 以降を使用する必要があります。アカウント担当者が、この機能を利用するための条件を満たすお手伝いをいたします。

* [!DNL Adobe Experience Manager] 6.4（またはそれ以降）
* [!DNL Adobe Experience Manager] 6.3 SP2（またはそれ以降）
* [!DNL Adobe Target Standard] または [!DNL Adobe Target Premium] アカウント
* 統合の有効化と認証の詳細情報については、[Adobe Target カスタマーケア](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)にお問い合わせください。

## [!DNL AEM] でのエクスペリエンスフラグメントの作成と設定 {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

[!DNL AEM] エクスペリエンスフラグメントを [!DNL Target] で使用するには、次の手順を実行する必要があります。

### 手順 1：[!DNL AEM] と [!DNL Target] を統合する

詳しくは、次を参照してください。

* **Adobe I/O**：_管理ユーザーガイド_&#x200B;ドキュメントの [Adobe I/O を使用した Adobe Target との統合](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-ims-adobe-io.html?lang=ja)。
* **[!DNL AEM]6.3**：_Adobe Experience Manager 6.3_ ドキュメントの [Adobe Analytics と Adobe Target へのオプトイン](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html?lang=ja)。
* **[!DNL AEM]6.4**：_Adobe Experience Manager 6.4_ ドキュメントの [Adobe Analytics と Adobe Target へのオプトイン](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html?lang=ja)。
* **[!DNL AEM]6.5**：*Adobe Experience Manager 6.5* ドキュメントの [Adobe Analytics と Adobe Target へのオプトイン](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=ja)。

### 手順 2：エクスペリエンスフラグメントを作成する

エクスペリエンスフラグメントは [!DNL AEM] で作成されます。詳しくは、次を参照してください。

* **[!DNL AEM]6.3**：*Adobe Experience Manager 6.3* ドキュメントの[エクスペリエンスフラグメント](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html?lang=ja)。
* **[!DNL AEM]6.4**：*Adobe Experience Manager 6.4* ドキュメントの[エクスペリエンスフラグメント](https://experienceleague.adobe.com/docs/experience-manager-64/authoring/authoring/experience-fragments.html?lang=ja)。
* **[!DNL AEM]6.5**：*Adobe Experience Manager 6.5* ドキュメントの[エクスペリエンスフラグメント](https://helpx.adobe.com/jp/experience-manager/6-5/sites/authoring/using/experience-fragments.html)。

### 手順 3：エクスペリエンスフラグメントを [!DNL Target] と共有するように [!DNL AEM] を設定する

1. [!DNL AEM] 内で目的のエクスペリエンスフラグメントまたはそれが含まれるフォルダーを選択し、「**[!UICONTROL プロパティ]**」をクリックします。
2. 「**[!UICONTROL クラウドサービス]**」タブをクリックし、**[!UICONTROL クラウドサービスの設定]**&#x200B;ドロップダウンリストから「**[!UICONTROL Adobe Target]**」を選択します。

   >[!NOTE]
   >
   >前の手順では、組織内のユーザーが [!DNL Adobe Target] 設定を既に作成していることを前提としています。

3. 「**[!UICONTROL 保存して閉じる]**」をクリックします。

### 手順 4：エクスペリエンスフラグメントを発行し、 にエクスポートする[!DNL Target]

[!DNL AEM] のバージョンに応じて、次のリンクを参照して手順を確認してください。

* **[!DNL AEM]6.3**：*Adobe Experience Manager 6.3* ドキュメントの [Target へのエクスペリエンスフラグメントの書き出し](https://helpx.adobe.com/jp/experience-manager/6-3/sites/administering/using/experience-fragments-target.html)。
* **[!DNL AEM]6.4**：*Adobe Experience Manager 6.4* ドキュメントの [Target へのエクスペリエンスフラグメントの書き出し](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html?lang=ja)。
* **[!DNL AEM]6.5**：*Adobe Experience Manager 6.5* ドキュメントの [Target へのエクスペリエンスフラグメントの書き出し](https://helpx.adobe.com/jp/experience-manager/6-5/sites/administering/using/experience-fragments-target.html)。

## [!DNL Target] アクティビティでのエクスペリエンスフラグメントの使用 {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

上記のタスクを実行すると、エクスペリエンスフラグメントが [!DNL Target] の[!UICONTROL オファー]ページに表示されます。

>[!NOTE]
>
>[!DNL Target] は現在、読み込むエクスペリエンスフラグメントを 10 分ごとに検索します。インポートされたエクスペリエンスフラグメントは 10 分以内に [!DNL Target] で使用可能になります。ただし、この時間は今後短縮される予定です。

>[!IMPORTANT]
>
>エクスペリエンスフラグメントは現在、HTML オファーとして [!DNL Target] にインポートされます。エクスペリエンスフラグメントの「プライマリ」バージョンは [!DNL AEM] に残ります。[!DNL Target] 内のエクスペリエンスフラグメントは編集できません。

リスト内のエクスペリエンスフラグメントにカーソルを合わせ、[!UICONTROL 表示]アイコン（![表示アイコン](assets/icon_info.png)）をクリックして、公開オファー配信 URL やその [!DNL AEM] パスなど、エクスペリエンスフラグメントに関する追加情報を表示できます。

[Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md)（VEC）または[フォームベースの Experience Composer](/help/c-experiences/form-experience-composer.md) を使用して、[!DNL Target] アクティビティでエクスペリエンスフラグメントを使用できます。

>[!NOTE]
>
>[!DNL Target] の AI および ML 機能を最大限に活用するには、A/B テストの作成時に[自動配分](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)（[自動割り当て](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)）を選択します。

**VEC を使用してエクスペリエンスフラグメントを使用するには：**

1. [!DNL Target] の [Visual Experience Composer](/help/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D) でエクスペリエンスを作成または編集する際に、[!DNL AEM] コンテンツを挿入するページ上の場所をクリックし、目的のオプションを選択して「[!UICONTROL エクスペリエンスフラグメントを選択]」リストを表示します。

   * [!UICONTROL 前に挿入]
   * [!UICONTROL 後ろに挿入]
   * [!UICONTROL エクスペリエンスフラグメントに置き換え]

   「[!UICONTROL エクスペリエンスフラグメント]」リストには、[!DNL AEM] で作成され、[!DNL Target] 内からネイティブで使用可能になったすべてのコンテンツが表示されます。

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

**フォームベースの Experience Composer を使用してエクスペリエンスフラグメントを使用するには：**

1. [!DNL Target] の[フォームベース Experience Composer](/help/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) でエクスペリエンスを作成または編集する際に、[!DNL AEM] コンテンツを挿入するページ上の場所を選択し、「**[!UICONTROL エクスペリエンスフラグメントを変更]**」を選択して「[!UICONTROL エクスペリエンスフラグメントを選択]」リストを表示します。

   ![](assets/experience_fragment_list.png)

   「[!UICONTROL エクスペリエンスフラグメント]」リストには、[!DNL AEM] で作成され、[!DNL Target] 内からネイティブで使用可能になったすべてのコンテンツが表示されます。

1. 対象のエクスペリエンスフラグメントを選択し、「**[!UICONTROL 保存]**」をクリックします。
1. アクティビティの設定を終了します。

## 注意点 {#considerations}

* [!DNL Target] は現在、読み込むエクスペリエンスフラグメントを 10 分ごとに検索します。インポートされたエクスペリエンスフラグメントは 10 分以内に [!DNL Target] で使用可能になります。ただし、この時間は今後短縮される予定です。
* エクスペリエンスフラグメントは現在、HTML オファーとして [!DNL Target] にインポートされます。エクスペリエンスフラグメントの「プライマリ」バージョンは [!DNL AEM] に残ります。[!DNL Target] 内のエクスペリエンスフラグメントは編集できません。
* Adobe IO を使用してエクスペリエンスフラグメントを作成することはできません。前述のとおり、AEM を使用してエクスペリエンスフラグメントを作成する必要があります。

## トレーニングビデオ：Adobe Target での AEM エクスペリエンスフラグメントの使用 ![チュートリアルバッジ](/help/assets/overview.png) {#section_C0EDC54063464F41A182492D2045BC64}

次のビデオでは、エクスペリエンスフラグメントの設定方法と使用方法を示します。

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>4:54 で取り上げた [!DNL AEM] ディープリンク機能は削除されました。

詳しくは、*AEM Sites のビデオとチュートリアル*&#x200B;ページの [Adobe Target でのエクスペリエンスフラグメントの使用](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html?lang=ja)を参照してください。
