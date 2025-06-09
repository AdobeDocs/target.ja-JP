---
keywords: エクスペリエンス;json;AEM, Adobe Experience Manager;Adobe Target へのエクスポート;エクスペリエンスフラグメント;フラグメント;XF
description: アクティビティでの使用方法  [!DNL Adobe Experience Manager] [!UICONTROL Experience Fragments] 説明  [!DNL Adobe Target]  ます。
title: ' [!DNL Adobe Experience Manager]  （AEM） [!UICONTROL Experience Fragments] の使用方法？'
feature: Integrations
exl-id: 400d0cde-e435-4cac-9bf0-64a6cad98995
source-git-commit: d31c9a6f47ea73342cfb638600f351ade4be7013
workflow-type: tm+mt
source-wordcount: '1082'
ht-degree: 32%

---

# AEM [!UICONTROL Experience Fragments]

[!DNL Adobe Experience Manager] （AEM）で作成した [!UICONTROL Experience Fragments] （XF）を [!DNL Target] アクティビティで使用して、最適化とパーソナライゼーションを支援します。

## 注意点

[!DNL Target] でAEM [!UICONTROL Experience Fragments] を使用する際は、次の点を考慮してください。

* この機能を使用するには、[!DNL Adobe Experience Manager]（AEM）の顧客である必要があります。詳しくは、次の[要件](#section_AE6F0971E1574B3AA324003599B96E5A)を参照してください。
* [!UICONTROL Experience Fragments] と [!UICONTROL Content Fragments] は、次のアクティビティタイプで使用できます。

   * [[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Automated Personalization] （AP）](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL Experience Targeting] （XT）](/help/main/c-activities/t-experience-target/experience-target.md)

* [!UICONTROL Experience Fragments] および [!UICONTROL Content Fragments] は、次のアクティビティタイプでは使用できません。

   * [[!UICONTROL Multivariate Test] （MVT）](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)

* [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) （VEC）と [ フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) を使用して、[!DNL Target] アクティビティで [!UICONTROL Experience Fragments] を使用できます。

AEM [!UICONTROL Experience Fragments] および [!UICONTROL Content Fragments] について詳しくは、[AEM [!UICONTROL Experience Fragments] およびコンテンツフラグメントの概要 ](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md) を参照してください。

## 要件 {#requirements}

[!DNL Target] 内で [!UICONTROL Experience Fragments] の機能をプロビジョニングする必要があります。 また、[!DNL AEM] as a Cloud Service または [!DNL AEM] 6.4（以降）を使用してください。アカウント担当者が、この機能を利用するための条件を満たすお手伝いをいたします。

* [!DNL Adobe Experience Manager] as a Cloud Service
* [!DNL Adobe Experience Manager] 6.5
* [!DNL Adobe Experience Manager] 6.4
* [!DNL Adobe Target Standard] または [!DNL Adobe Target Premium] アカウント

[!DNL Adobe Experience Manager] 6.3 および 6.4 は提供終了となり、サポート対象外になりました（拡張サポートを購入した顧客を除く）。

統合の有効化と認証の詳細情報については、[Adobe Target カスタマーケア](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)にお問い合わせください。

## [!DNL AEM] での [!UICONTROL Experience Fragments] の作成と設定 {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

[!DNL Target] で [!DNL AEM] [!UICONTROL Experience Fragments] を使用するには、次の手順を実行する必要があります。

### 手順 1：[!DNL AEM] と [!DNL Target] を統合する

詳しくは、次を参照してください。

* **AEM as a Cloud Service**: [4}Experience Manager as a Cloud Service](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/sites/integrations/integrating-adobe-target){target=_blank} ガイドの {Adobe Targetとの統合 *。*
* **Adobe Developer**: [ 管理ユーザーガイド ](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-target-ims-adobe-io.html){target=_blank} ドキュメントの *Adobe I/O を使用したAdobe Targetとの統合*。
* **[!DNL AEM]6.5**：*Adobe Experience Manager 6.5* ドキュメントの [Adobe Analytics と Adobe Target へのオプトイン](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=ja){target=_blank}。
* **[!DNL AEM]6.4**：*Adobe Experience Manager 6.4* ドキュメントの [Adobe Analytics と Adobe Target へのオプトイン](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html?lang=ja){target=_blank}。

### 手順 2：エクスペリエンスフラグメントを作成する

[!UICONTROL Experience Fragments] は [!DNL AEM] で作成されます。 詳しくは、次を参照してください。

* **AEM as a Cloud Service**: *Experience Manager as a Cloud Service* ガイドの [[!UICONTROL Experience Fragments]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/experience-fragments.html?lang=ja){target=_blank}。
* **[!DNL AEM]6.5**: *Adobe Experience Manager 6.5* ドキュメントの [[!UICONTROL Experience Fragments]](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/authoring/experience-fragments.html?lang=ja){target=_blank}。
* **[!DNL AEM]6.4**: *Adobe Experience Manager 6.4* ドキュメントの [[!UICONTROL Experience Fragments]](https://experienceleague.adobe.com/docs/experience-manager-64/authoring/authoring/experience-fragments.html?lang=ja){target=_blank}。

### 手順 3:[!UICONTROL Experience Fragment] を [!DNL Target] と共有するように [!DNL AEM] を設定する

1. [!DNL AEM] 内で目的の [!UICONTROL Experience Fragment] またはそれを含むフォルダーを選択し、「**[!UICONTROL Properties]**」をクリックします。
2. 「**[!UICONTROL Cloud Services]**」タブをクリックし、「**[!UICONTROL Cloud Service Configuration]**」ドロップダウンリストから「**[!UICONTROL Adobe Target]**」を選択します。

   前の手順では、組織内のユーザーが [!DNL Adobe Target] 設定を既に作成していることを前提としています。

3. **[!UICONTROL Save & Close]** をクリックします。

### 手順 4:[!UICONTROL Experience Fragment] を公開し、[!DNL Target] に書き出す

[!DNL AEM] のバージョンに応じて、次のリンクを参照して手順を確認してください。

* **AEM as a Cloud Service**: [5}Experience Manager as a Cloud Service](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/sites/integrations/experience-fragments-target?lang=en){target=_blank} ガイドの {Adobe Targetへの [!UICONTROL Experience Fragments] の書き出し *。*
* **[!DNL AEM]6.5**：*Adobe Experience Manager 6.5* ドキュメントの [Target へのエクスペリエンスフラグメントの書き出し](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/experience-fragments-target.html?lang=ja){target=_blank}。
* **[!DNL AEM]6.4**：*Adobe Experience Manager 6.4* ドキュメントの [Target へのエクスペリエンスフラグメントの書き出し](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html?lang=ja){target=_blank}。

## [!DNL Target] アクティビティでの [!UICONTROL Experience Fragments] の使用 {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

上記のタスクを実行すると、[!UICONTROL Experience Fragment] が [!DNL Target] の [!UICONTROL Offers] ページに表示されます。

[!DNL Target] は現在、読み込む [!UICONTROL Experience Fragments] を 10 分ごとに検索します。 読み込んだ [!UICONTROL Experience Fragment] は 10 分以内に [!DNL Target] で使用可能になります。ただし、この時間枠は今後短縮される予定です。

[!UICONTROL Experience Fragment] は、HTMLまたは JSON オファーとして [!DNL Target] に読み込まれます。 [!UICONTROL Experience Fragment] の「プライマリ」バージョンは [!DNL AEM] にあります。 [!DNL Target] で [!UICONTROL Experience Fragment] を編集することはできません。

[!UICONTROL HTML XFs] と [!UICONTROL JSON XFs] でフィルタリングおよび検索すると、[!DNL Target] に書き出される [!UICONTROL Experience Fragment] タイプを区別できます。

![エクスペリエンスフラグメントタイプでのフィルタリング：Target UI の HTML または JSON](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

リスト内の [!UICONTROL Experience Fragment] にポインタを合わせ、「[!UICONTROL View]」アイコン ![ 情報アイコン ](/help/main/assets/icons/InfoOutline.svg) をクリックすると、[!UICONTROL Name]、[!UICONTROL Type]、[!UICONTROL Offer ID]、[!UICONTROL Offer path]、最終変更情報など、[!UICONTROL Experience Fragment] に関する追加情報が表示されます。 [!UICONTROL [!UICONTROL View Full Details]] をクリックして、このオファーを参照するアクティビティを表示します。

![エクスペリエンスフラグメント情報ポップアップ](/help/main/c-integrating-target-with-mac/aem/assets/xf-info-popup.png)

[Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) （VEC）と [ フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) を使用して、[!DNL Target] アクティビティで [!UICONTROL Experience Fragments] を使用できます。

>[!TIP]
>
>次のような場合に、人工知能、機械学習、Recommendations を使用 [!UICONTROL Experience Fragments] ます。
>
>* [!DNL Target] の AI 機能と ML 機能を最大限に活用するには、アクティビティの作成時、[自動配分](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)または[自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md)を選択してください。
>
>* [!UICONTROL Experience Fragments] は [!DNL Recommendations] アクティビティではサポートされていません。 ただし、Recommendations に [!UICONTROL Experience Fragments] を使用するには、[!UICONTROL A/B Test] アクティビティ（[!UICONTROL Auto-Allocate] と [!UICONTROL Auto-Target] を含む）または [!UICONTROL Experience Targeting] アクティビティ（XT）を作成して、[Recommendations をオファーとして含める ](/help/main/c-recommendations/recommendations-as-an-offer.md) ことができます。

**VEC を使用して [!UICONTROL Experience Fragments] を使用するには：**

1. [!DNL Target] の場合、[Visual Experience Composer](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D) でエクスペリエンスを作成または編集する際に、コンテンツを挿入するページ上の場所をクリックし、**[!UICONTROL Replace Content]** > **[!UICONTROL Experience Fragment]** をクリックして [!DNL AEM] エクスペリ [!UICONTROL Experience Fragment] ンスダイアログボックスを表示します。

   [!UICONTROL Experience Fragment] リストには、[!DNL AEM] で作成され、[!DNL Target] 内からネイティブで使用可能になったコンテンツが表示されます。

   >[!NOTE]
   >
   >[!UICONTROL Swap with Experience Fragment] オプションは、画像には使用できません。 画像にこのオプションを使用する場合は、目的の画像を含むコンテナ要素をクリックします。

   ![experience_fragment_list image](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

1. 目的の [!UICONTROL Experience Fragment] を選択し、「**[!UICONTROL Add]**」をクリックします。
1. アクティビティの設定を終了します。

   各タイプのアクティビティを設定する方法について詳しくは、次のトピックを参照してください。

   * **A/B テスト：** [A/B テストの作成](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **自動配分：** [自動配分](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **自動ターゲット：** [自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * **Automated Personalizationアクティビティ（AP）：**[Automated Personalizationアクティビティの作成](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **エクスペリエンスターゲット設定（XT）：** [エクスペリエンスのターゲット設定アクティビティの作成](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **A/B テストまたは XT アクティビティのRecommendations：** [オファーとしての Recommendations](/help/main/c-recommendations/recommendations-as-an-offer.md)

   [!DNL Target] で JSON として書き出された [!UICONTROL Experience Fragments] は、VEC を使用して作成されたアクティビティでは使用できません。VEC ベースのアクティビティでは、HTML [!UICONTROL Experience Fragments] のみがサポートされます。 JSON [!UICONTROL Experience Fragments] を使用する場合は、[ フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) を使用して作成されたアクティビティで使用します。

**[!UICONTROL Form-based Experience Composer] を使用して [!UICONTROL Experience Fragments] を使用するには：**

1. [!DNL Target] の場合、[ フォームベース Experience Composer](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) でエクスペリエンスを作成または編集する際に、[!DNL AEM] コンテンツを挿入するページ上の場所を選択し、**[!UICONTROL More Details]** アイコン（![ 詳細アイコン ](/help/main/assets/icons/MoreSmall.svg)）をクリックして **[!UICONTROL Change Experience Fragment]** を選択し、[!UICONTROL Change Experience Fragment] ダイアログボックスを表示します。

   ![experience_fragment_list image](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

   [!UICONTROL Experience Fragment] リストには、[!DNL AEM] で作成され、[!DNL Target] 内からネイティブで使用可能になったコンテンツが表示されます。

1. 目的の [!UICONTROL Experience Fragment] を選択し、「**[!UICONTROL Add]**」をクリックします。
1. アクティビティの設定を終了します。

## 追加情報

* [!DNL Target] は現在、読み込む [!UICONTROL Experience Fragments] を 10 分ごとに検索します。 読み込んだ [!UICONTROL Experience Fragment] は 10 分以内に [!DNL Target] で使用可能になります。ただし、この時間枠は今後短縮される予定です。
* [!UICONTROL Experience Fragment] は、HTMLまたは JSON オファーとして [!DNL Target] に読み込まれます。 [!UICONTROL Experience Fragment] の「プライマリ」バージョンは [!DNL AEM] にあります。 [!DNL Target] で [!UICONTROL Experience Fragment] を編集することはできません。
* [!DNL Adobe Developer] を使用して [!UICONTROL Experience Fragments] を作成することはできません。 前述のとおり、AEMを使用して [!UICONTROL Experience Fragments] を作成します。
* AEMで [!UICONTROL Experience Fragment] を更新する場合は、[!UICONTROL Experience Fragment] を公開して [!DNL Target] に再度書き出し、最新の変更を使用でき [!DNL Target] ようにする必要があります。

## [!UICONTROL Target] に書き出した [!UICONTROL Experience Fragments] から clientlibs と不要なHTMLを削除しています

AEMで配信されるページで [!DNL Target] を使用して [!UICONTROL Experience Fragment] オファーを使用する場合、ターゲットページには必要なクライアントライブラリが既に含まれています。 また、オファー内の不要な HTML 要素も必要ありません。

HTML ページ全体で [!UICONTROL Experience Fragment] をラップし、問題を引き起こす場合があります。 [!UICONTROL Experience Fragment] がHTMLの小さな断片であり、HTML、HEAD、BODY などを含む完全なHTML ページではないことを確認します。

詳しくは、次のブログ投稿（[AEM 6.5:Target に書き出された [!UICONTROL Experience Fragments] からの clientlibs の削除 ](https://www.linkedin.com/pulse/aem-65-removing-clientlibs-from-experience-fragments-exported-haser){target=_blank} を参照してください。

## トレーニングビデオ：[!DNL Adobe Target] でのAEM [!UICONTROL Experience Fragments] の使用

次のビデオでは、[!UICONTROL Experience Fragments] の設定方法と使用方法を示します。

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>4:54 で取り上げた [!DNL AEM] ディープリンク機能は削除されました。

詳しくは、*AEM Sitesのビデオとチュートリアル ](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html?lang=ja) ページの [Adobe Targetでの [!UICONTROL Experience Fragments] の使用* を参照してください。
