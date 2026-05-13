---
keywords: エクスペリエンス;json;AEM, Adobe Experience Manager;Adobe Target へのエクスポート;エクスペリエンスフラグメント;フラグメント;XF
description: ' [!DNL Adobe Target]  アクティビティで [!DNL Adobe Experience Manager] [!UICONTROL Experience Fragments]を使用する方法を説明します。'
title: ' [!DNL Adobe Experience Manager]  （AEM） [!UICONTROL Experience Fragments]の使用方法を教えてください。'
feature: Integrations
exl-id: 400d0cde-e435-4cac-9bf0-64a6cad98995
TQID: https://experienceleague.adobe.com/-W1ELJx0ajes6BPEVIiS8q6ebmRLTTgIrxvGMUEWEaM
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: f7c7de77-382f-4f48-8b36-61a170f06d3d
topic_v2:
  - id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1248
ht-degree: 36%

---

# AEM [!UICONTROL Experience Fragments]

[!DNL Target] アクティビティの[!DNL Adobe Experience Manager] （AEM）で作成された[!UICONTROL Experience Fragments] （XF）を使用して、最適化とパーソナライゼーションを支援します。

## 注意点

[!DNL Target]でAEM [!UICONTROL Experience Fragments]を使用する場合は、次の点を考慮してください。

* この機能を使用するには、[!DNL Adobe Experience Manager]（AEM）の顧客である必要があります。 詳しくは、次の[要件](#section_AE6F0971E1574B3AA324003599B96E5A)を参照してください。
* [!UICONTROL Experience Fragments]と[!UICONTROL Content Fragments]は、次のアクティビティタイプで使用できます。

   * [[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Automated Personalization] （AP）](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL Experience Targeting] （XT）](/help/main/c-activities/t-experience-target/experience-target.md)

* [!UICONTROL Experience Fragments]と[!UICONTROL Content Fragments]は、次のアクティビティの種類では利用できません：

   * [[!UICONTROL Multivariate Test] （MVT）](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)

* [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) （VEC）と[&#x200B; フォームベースのExperience Composer](/help/main/c-experiences/form-experience-composer.md)を使用して、[!DNL Target]のアクティビティで[!UICONTROL Experience Fragments]を利用できます。

AEM [!UICONTROL Experience Fragments]と[!UICONTROL Content Fragments]について詳しくは、[AEM [!UICONTROL Experience Fragments]とコンテンツフラグメントの概要](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md)を参照してください。

## 要件 {#requirements}

[!DNL Target]内の[!UICONTROL Experience Fragments]機能をプロビジョニングする必要があります。 また、[!DNL AEM] as a Cloud Service または [!DNL AEM] 6.4（以降）を使用してください。 アカウント担当者が、この機能を利用するための条件を満たすお手伝いをいたします。

* [!DNL Adobe Experience Manager] as a Cloud Service
* [!DNL Adobe Experience Manager] 6.5
* [!DNL Adobe Experience Manager] 6.4
* [!DNL Adobe Target Standard] または [!DNL Adobe Target Premium] アカウント

[!DNL Adobe Experience Manager] 6.3 および 6.4 は提供終了となり、サポート対象外になりました（拡張サポートを購入した顧客を除く）。

統合の有効化と認証の詳細情報については、[Adobe Target カスタマーケア](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)にお問い合わせください。

## [!DNL AEM]での[!UICONTROL Experience Fragments]の作成と設定 {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

[!DNL Target]で[!DNL AEM] [!UICONTROL Experience Fragments]を使用するには、次の手順を実行する必要があります。

### 手順 1：[!DNL AEM] と [!DNL Target] を統合する

詳しくは、次を参照してください。

* **AEM as a Cloud Service**: [Adobe Targetとの連携](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/sites/integrations/integrating-adobe-target){target=_blank} （*Experience Manager as a Cloud Service* ガイド）
* **Adobe Developer**: [Adobe I/0](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-target-ims-adobe-io.html){target=_blank}を使用したAdobe Targetとの統合（*管理ユーザーガイド*）を参照）。
* **[!DNL AEM]6.5**：*Adobe Experience Manager 6.5* ドキュメントの [Adobe Analytics と Adobe Target へのオプトイン](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=ja){target=_blank}。
* **[!DNL AEM]6.4**：*Adobe Experience Manager 6.4* ドキュメントの [Adobe Analytics と Adobe Target へのオプトイン](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html?lang=ja){target=_blank}。

### 手順 2：エクスペリエンスフラグメントを作成する

[!UICONTROL Experience Fragments]は[!DNL AEM]に作成されました。 詳しくは、次を参照してください。

* **AEM as a Cloud Service**: *Experience Manager as a Cloud Service* ガイドの[[!UICONTROL Experience Fragments]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/experience-fragments.html?lang=ja){target=_blank}。
* **[!DNL AEM]6.5**: *Adobe Experience Manager 6.5* ドキュメントの[[!UICONTROL Experience Fragments]](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/authoring/experience-fragments.html?lang=ja){target=_blank}。
* **[!DNL AEM]6.4**: *Adobe Experience Manager 6.4* ドキュメントの[[!UICONTROL Experience Fragments]](https://experienceleague.adobe.com/docs/experience-manager-64/authoring/authoring/experience-fragments.html?lang=ja){target=_blank}。

### 手順3: [!DNL AEM]を設定して[!UICONTROL Experience Fragment]を[!DNL Target]と共有する

1. [!DNL AEM]内から、目的の[!UICONTROL Experience Fragment]またはそのフォルダーを選択し、**[!UICONTROL Properties]**&#x200B;をクリックします。
2. 「**[!UICONTROL Cloud Services]**」タブをクリックし、**[!UICONTROL Cloud Service Configuration]** ドロップダウンリストから「**[!UICONTROL Adobe Target]**」を選択します。

   前の手順では、組織内のユーザーが [!DNL Adobe Target] 設定を既に作成していることを前提としています。

3. **[!UICONTROL Save & Close]** をクリックします。

### 手順4: [!UICONTROL Experience Fragment]を公開して[!DNL Target]に書き出す

[!DNL AEM] のバージョンに応じて、次のリンクを参照して手順を確認してください。

* **AEM as a Cloud Service**: [Experience Manager as a Cloud Service *ガイドの[!UICONTROL Experience Fragments]をAdobe Target](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/sites/integrations/experience-fragments-target?lang=en){target=_blank}に書き出しています。*
* **[!DNL AEM]6.5**：*Adobe Experience Manager 6.5* ドキュメントの [Target へのエクスペリエンスフラグメントの書き出し](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/experience-fragments-target.html?lang=ja){target=_blank}。
* **[!DNL AEM]6.4**：*Adobe Experience Manager 6.4* ドキュメントの [Target へのエクスペリエンスフラグメントの書き出し](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html?lang=ja){target=_blank}。

## [!DNL Target]のアクティビティで[!UICONTROL Experience Fragments]を使用しています {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

上記のタスクを実行すると、[!UICONTROL Experience Fragment]が[!DNL Target]の[!UICONTROL Offers] ページに表示されます。

[!DNL Target]は現在、10分ごとに[!UICONTROL Experience Fragments]を読み込みます。 インポートされた[!UICONTROL Experience Fragment]は10分以内に[!DNL Target]で利用できるようになりますが、この時間枠は今後さらに短縮されます。

[!UICONTROL Experience Fragment]は、[!DNL Target]にHTMLまたはJSON オファーとして読み込まれます。 [!UICONTROL Experience Fragment] 「プライマリ」バージョンは[!DNL AEM]に残ります。 [!UICONTROL Experience Fragment]を[!DNL Target]で編集することはできません。

[!UICONTROL HTML XFs]と[!UICONTROL JSON XFs]でフィルタリングして検索し、[!DNL Target]に書き出された[!UICONTROL Experience Fragment]種類を区別できます。

![エクスペリエンスフラグメントタイプでのフィルタリング：Target UI の HTML または JSON](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

リスト内の[!UICONTROL Experience Fragment]にカーソルを合わせ、[!UICONTROL View] アイコン ![情報アイコン &#x200B;](/help/main/assets/icons/InfoOutline.svg)をクリックして、[!UICONTROL Experience Fragment]に関する追加情報（その[!UICONTROL Name]、[!UICONTROL Type]、[!UICONTROL Offer ID]、[!UICONTROL Offer path]、および最後の変更情報を含む）を表示できます。 このオファーを参照するアクティビティを表示するには、[!UICONTROL [!UICONTROL View Full Details]]をクリックします。

![エクスペリエンスフラグメント情報ポップアップ](/help/main/c-integrating-target-with-mac/aem/assets/xf-info-popup.png)

[Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) （VEC）と[&#x200B; フォームベースのExperience Composer](/help/main/c-experiences/form-experience-composer.md)を使用して、[!DNL Target]のアクティビティで[!UICONTROL Experience Fragments]を利用できます。

>[!TIP]
>
>[!UICONTROL Experience Fragments]で人工知能、機械学習、レコメンデーションを使用：
>
>* [!DNL Target] の AI 機能と ML 機能を最大限に活用するには、アクティビティの作成時、[自動配分](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)または[自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md)を選択してください。
>
>* [!UICONTROL Experience Fragments]は[!DNL Recommendations] アクティビティではサポートされていません。 ただし、レコメンデーションに[!UICONTROL Experience Fragments]を使用するには、[!UICONTROL A/B Test]のアクティビティ（[!UICONTROL Auto-Allocate]と[!UICONTROL Auto-Target]を含む）または[!UICONTROL Experience Targeting] （XT）のアクティビティを作成し、[&#x200B; レコメンデーションをオファー](/help/main/c-recommendations/recommendations-as-an-offer.md)として含めることができます。

**VEC:**&#x200B;を使用して[!UICONTROL Experience Fragments]を使用するには

1. [!DNL Target]で、[Visual Experience Composer](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)でエクスペリエンスを作成または編集する際に、[!DNL AEM] コンテンツを挿入するページ上の場所をクリックし、**[!UICONTROL Replace Content]** > **[!UICONTROL Experience Fragment]**&#x200B;をクリックして[!UICONTROL Experience Fragment] ダイアログボックスを表示します。

   [!UICONTROL Experience Fragment] ダイアログボックスには、[!DNL AEM]で作成されたコンテンツが表示されます。このコンテンツは、[!DNL Target]内からネイティブに利用できるようになりました。

   >[!NOTE]
   >
   >[!UICONTROL Replace Content] オプションは画像では使用できません。 画像にこのオプションを使用する場合は、目的の画像を含むコンテナ要素をクリックします。

   ![experience_fragment_list image](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

1. 目的の[!UICONTROL Experience Fragment]を選択し、**[!UICONTROL Add]**&#x200B;をクリックします。
1. アクティビティの設定を終了します。

   各タイプのアクティビティを設定する方法について詳しくは、次のトピックを参照してください。

   * **A/B テスト：** [A/B テストの作成](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **自動配分：** [自動配分](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **自動ターゲット：** [自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * **Automated Personalizationアクティビティ（AP）：**&#x200B;[Automated Personalizationアクティビティの作成](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **エクスペリエンスターゲット設定（XT）：** [エクスペリエンスのターゲット設定アクティビティの作成](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **A/B テストまたは XT アクティビティのRecommendations：** [オファーとしての Recommendations](/help/main/c-recommendations/recommendations-as-an-offer.md)

   [!DNL Target]でJSONとして書き出された[!UICONTROL Experience Fragments]は、VECを使用して作成されたアクティビティでは使用できません。VEC ベースのアクティビティでは、HTML [!UICONTROL Experience Fragments]のみがサポートされます。 JSON [!UICONTROL Experience Fragments]を使用する場合は、[&#x200B; フォームベースのエクスペリエンスコンポーザー](/help/main/c-experiences/form-experience-composer.md)を使用して作成されたアクティビティでそれらを使用します。

**[!UICONTROL Form-based Experience Composer]を使用して[!UICONTROL Experience Fragments]を利用するには：**

1. [!DNL Target]で、[&#x200B; フォームベースのExperience Composer](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)でエクスペリエンスを作成または編集する際に、[!DNL AEM] コンテンツを挿入するページ上の場所を選択し、**[!UICONTROL More Details]** アイコン（![詳細アイコン &#x200B;](/help/main/assets/icons/MoreSmall.svg)）をクリックし、**[!UICONTROL Change Experience Fragment]**&#x200B;を選択して[!UICONTROL Change Experience Fragment] ダイアログボックスを表示します。

   ![experience_fragment_list image](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

   [!UICONTROL Experience Fragment] ダイアログボックスには、[!DNL AEM]で作成されたコンテンツが表示されます。このコンテンツは、[!DNL Target]内からネイティブに利用できるようになりました。

1. 目的の[!UICONTROL Experience Fragment]を選択し、**[!UICONTROL Add]**&#x200B;をクリックします。
1. アクティビティの設定を終了します。

## 追加情報

* [!DNL Target]は現在、10分ごとに[!UICONTROL Experience Fragments]を読み込みます。 インポートされた[!UICONTROL Experience Fragment]は10分以内に[!DNL Target]で利用できるようになりますが、この時間枠は今後さらに短縮されます。
* [!UICONTROL Experience Fragment]は、[!DNL Target]にHTMLまたはJSON オファーとして読み込まれます。 [!UICONTROL Experience Fragment] 「プライマリ」バージョンは[!DNL AEM]に残ります。 [!UICONTROL Experience Fragment]を[!DNL Target]で編集することはできません。
* [!DNL Adobe Developer]を使用して[!UICONTROL Experience Fragments]を作成することはできません。 上記のように、AEMを使用して[!UICONTROL Experience Fragments]を作成します。
* AEMで[!UICONTROL Experience Fragment]を更新する場合、[!DNL Target]が最新の変更を使用できるように、[!UICONTROL Experience Fragment]を公開して[!DNL Target]に再度書き出す必要があります。

## [!UICONTROL Experience Fragments]からクライアントライブラリと無関係なHTMLを削除して、[!UICONTROL Target]にエクスポートしました

AEMによって配信されたページで[!DNL Target]を含む[!UICONTROL Experience Fragment]件のオファーを使用する場合、ターゲットページには必要なクライアントライブラリが既に含まれています。 また、オファー内の不要な HTML 要素も必要ありません。

HTML ページ全体が[!UICONTROL Experience Fragment]をラップして問題が発生することがあります。 [!UICONTROL Experience Fragment]がHTMLの小さな部分であり、HTML、HEAD、BODYなどを含むHTMLの完全なページでないことを確認します。

詳しくは、次のブログ記事を参照してください。[AEM 6.5: [!UICONTROL Experience Fragments]からTarget](https://www.linkedin.com/pulse/aem-65-removing-clientlibs-from-experience-fragments-exported-haser/){target=_blank}に書き出されたclientlibを削除しています。

## トレーニング ビデオ：[!DNL Adobe Target]でAEM [!UICONTROL Experience Fragments]を使用する

次のビデオでは、[!UICONTROL Experience Fragments]の設定と使用方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>4:54で説明されている[!DNL AEM]のディープリンク機能が削除されました。

詳しくは、*AEM Sitesのビデオとチュートリアル* ページの「[!UICONTROL Experience Fragments]とAdobe Target[&#128279;](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html?lang=ja)の併用」を参照してください。
