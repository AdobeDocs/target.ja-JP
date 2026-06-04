---
keywords: エクスペリエンス;json;AEM, Adobe Experience Manager;Adobe Target へのエクスポート;エクスペリエンスフラグメント;フラグメント;XF
description: ' [!DNL Adobe Target]  アクティビティで [!DNL Adobe Experience Manager] [!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]を使用する方法について説明します。'
title: ' [!DNL Adobe Experience Manager]  （AEM） [!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]の使用方法を教えてください。'
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
source-wordcount: 1446
ht-degree: 32%

---

# AEM [!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]

[!DNL Target]件のアクティビティで[!DNL Adobe Experience Manager] （AEM）で作成された[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;] （XF）を使用して、最適化とパーソナライゼーションを支援します。

## 注意点

[!DNL Target]でAEM [!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]を使用する場合は、次の点を考慮してください。

* この機能を使用するには、[!DNL Adobe Experience Manager]（AEM）の顧客である必要があります。 詳しくは、次の[要件](#section_AE6F0971E1574B3AA324003599B96E5A)を参照してください。
* [!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]と[!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]は、次のアクティビティタイプで使用できます。

   * [[!UICONTROL A/B テスト]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL 自動配分]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL 自動ターゲット]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Automated Personalization]（AP）](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL エクスペリエンスのターゲット設定]（XT）](/help/main/c-activities/t-experience-target/experience-target.md)

* [!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]と[!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]は、次のアクティビティタイプでは使用できません。

   * [[!UICONTROL 多変量分析テスト] （MVT）](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL レコメンデーション]](/help/main/c-recommendations/recommendations.md)

* [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) （VEC）と[&#x200B; フォームベースのExperience Composer](/help/main/c-experiences/form-experience-composer.md)を使用して、[!DNL Target]のアクティビティで[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]を使用できます。

AEM [!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]および[!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]について詳しくは、[AEM [!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]およびコンテンツフラグメントの概要](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md)を参照してください。

## 要件 {#requirements}

[!DNL Target]内で[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]機能をプロビジョニングする必要があります。 また、[!DNL AEM] as a Cloud Service または [!DNL AEM] 6.4（以降）を使用してください。 アカウント担当者が、この機能を利用するための条件を満たすお手伝いをいたします。

* [!DNL Adobe Experience Manager] as a Cloud Service
* [!DNL Adobe Experience Manager] 6.5
* [!DNL Adobe Experience Manager] 6.4
* [!DNL Adobe Target Standard] または [!DNL Adobe Target Premium] アカウント

[!DNL Adobe Experience Manager] 6.3 および 6.4 は提供終了となり、サポート対象外になりました（拡張サポートを購入した顧客を除く）。

統合の有効化と認証の詳細情報については、[Adobe Target カスタマーケア](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)にお問い合わせください。

## [!DNL AEM]での[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]の作成と設定 {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

[!DNL Target]で[!DNL AEM] [!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]を使用するには、次の手順を実行する必要があります。

### 手順 1：[!DNL AEM] と [!DNL Target] を統合する

詳しくは、次を参照してください。

* **AEM as a Cloud Service**: [Adobe Targetとの連携](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/sites/integrations/integrating-adobe-target){target=_blank} （*Experience Manager as a Cloud Service* ガイド）
* **Adobe Developer**: [Adobe I/0](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-target-ims-adobe-io.html?lang=ja){target=_blank}を使用したAdobe Targetとの統合（*管理ユーザーガイド*）を参照）。
* **[!DNL AEM]6.5**：*Adobe Experience Manager 6.5* ドキュメントの [Adobe Analytics と Adobe Target へのオプトイン](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=ja){target=_blank}。
* **[!DNL AEM]6.4**：*Adobe Experience Manager 6.4* ドキュメントの [Adobe Analytics と Adobe Target へのオプトイン](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html?lang=ja){target=_blank}。

### 手順 2：エクスペリエンスフラグメントを作成する

[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]は[!DNL AEM]に作成されました。 詳しくは、次を参照してください。

* **AEM as a Cloud Service**: *Experience Manager as a Cloud Service* ガイドの[[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/experience-fragments.html?lang=ja){target=_blank}。
* **[!DNL AEM]6.5**: *Adobe Experience Manager 6.5* ドキュメントの[[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/authoring/experience-fragments.html?lang=ja){target=_blank}。
* **[!DNL AEM]6.4**: *Adobe Experience Manager 6.4* ドキュメントの[[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]](https://experienceleague.adobe.com/docs/experience-manager-64/authoring/authoring/experience-fragments.html?lang=ja){target=_blank}。

### 手順3: [!DNL AEM]を設定して[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]を[!DNL Target]と共有する

1. [!DNL AEM]内から、目的の[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]またはその含まれるフォルダーを選択し、**[!UICONTROL プロパティ]**&#x200B;をクリックします。
2. 「**[!UICONTROL Cloud Services]**」タブをクリックし、「**[!UICONTROL Cloud Service Configuration]**」ドロップダウンリストから「**[!UICONTROL Adobe Target]**」を選択します。

   前の手順では、組織内のユーザーが [!DNL Adobe Target] 設定を既に作成していることを前提としています。

3. 「**[!UICONTROL 保存して閉じる]**」をクリックします。

### 手順4: [!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]を公開し、[!DNL Target]に書き出す

[!DNL AEM] のバージョンに応じて、次のリンクを参照して手順を確認してください。

* **AEM as a Cloud Service**: [ エクスペリエンスフラグメント ]を&#x200B;*Experience Manager as a Cloud Service* ガイドの(https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/sites/integrations/experience-fragments-target?lang=en){target=_blank}Adobe Targetに書き出しています。
* **[!DNL AEM]6.5**：*Adobe Experience Manager 6.5* ドキュメントの [Target へのエクスペリエンスフラグメントの書き出し](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/experience-fragments-target.html?lang=ja){target=_blank}。
* **[!DNL AEM]6.4**：*Adobe Experience Manager 6.4* ドキュメントの [Target へのエクスペリエンスフラグメントの書き出し](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html?lang=ja){target=_blank}。

## [!DNL Target]のアクティビティで[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]を使用 {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

上記のタスクを実行すると、[!DNL Target]の[!UICONTROL &#x200B; オファー] ページに[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]が表示されます。

[!DNL Target]は現在、10分ごとに[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]を読み込みます。 インポートされた[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]は[!DNL Target]内に10分以内に利用できるようになりますが、この時間枠は今後短くなります。

[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]は、[!DNL Target]にHTMLまたはJSON オファーとして読み込まれます。 [!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;] 「プライマリ」バージョンは[!DNL AEM]に残ります。 [!DNL Target]では[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]を編集できません。

[!UICONTROL HTML XF]と[!UICONTROL JSON XF]でフィルタリングして検索すると、[!DNL Target]に書き出される[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]の種類を区別できます。

![エクスペリエンスフラグメントタイプでのフィルタリング：Target UI の HTML または JSON](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

リスト内の[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]にカーソルを合わせ、[!UICONTROL 表示] アイコン ![情報アイコン &#x200B;](/help/main/assets/icons/InfoOutline.svg)をクリックすると、[!UICONTROL 名前]、[!UICONTROL 型]、[!UICONTROL &#x200B; オファーID]、[!UICONTROL &#x200B; オファーパス &#x200B;]、最終変更情報など、[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]に関する追加情報を表示できます。 「[!UICONTROL [!UICONTROL 詳細を表示]]」をクリックして、このオファーを参照するアクティビティを表示します。

![エクスペリエンスフラグメント情報ポップアップ](/help/main/c-integrating-target-with-mac/aem/assets/xf-info-popup.png)

[Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) （VEC）と[&#x200B; フォームベースのExperience Composer](/help/main/c-experiences/form-experience-composer.md)を使用して、[!DNL Target]のアクティビティで[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]を使用できます。

>[!TIP]
>
>[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]で人工知能、機械学習、レコメンデーションを使用：
>
>* [!DNL Target] の AI 機能と ML 機能を最大限に活用するには、アクティビティの作成時、[自動配分](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)または[自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md)を選択してください。
>
>* [!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]は、[!DNL Recommendations] アクティビティではサポートされていません。 ただし、レコメンデーションに[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]を使用するには、[!UICONTROL A/B テスト &#x200B;] アクティビティ（[!UICONTROL 自動配分]および[!UICONTROL 自動ターゲット &#x200B;]を含む）または[!UICONTROL &#x200B; エクスペリエンスターゲティング &#x200B;] （XT）アクティビティを作成し、[&#x200B; レコメンデーションをオファー](/help/main/c-recommendations/recommendations-as-an-offer.md)として含めることができます。

**VEC:**&#x200B;を使用して[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]を使用するには

1. [!DNL Target]で、[Visual Experience Composer](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)でエクスペリエンスを作成または編集する際に、[!DNL AEM] コンテンツを挿入するページ上の場所をクリックし、**[!UICONTROL コンテンツの置換]** > **[!UICONTROL エクスペリエンスフラグメント]**&#x200B;をクリックして、[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;] ダイアログボックスを表示します。

   [!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;] ダイアログボックスには、[!DNL AEM]で作成されたコンテンツが表示され、[!DNL Target]内からネイティブに利用できるようになりました。

   >[!NOTE]
   >
   >[!UICONTROL &#x200B; コンテンツを置換] オプションは、画像には使用できません。 画像にこのオプションを使用する場合は、目的の画像を含むコンテナ要素をクリックします。

   ![experience_fragment_list image](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

1. 必要な[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]を選択し、**[!UICONTROL 追加]**&#x200B;をクリックします。
1. アクティビティの設定を終了します。

   各タイプのアクティビティを設定する方法について詳しくは、次のトピックを参照してください。

   * **A/B テスト：** [A/B テストの作成](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **自動配分：** [自動配分](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **自動ターゲット：** [自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * **Automated Personalizationアクティビティ（AP）：**&#x200B;[Automated Personalizationアクティビティの作成](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **エクスペリエンスターゲット設定（XT）：** [エクスペリエンスのターゲット設定アクティビティの作成](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **A/B テストまたは XT アクティビティのRecommendations：** [オファーとしての Recommendations](/help/main/c-recommendations/recommendations-as-an-offer.md)

   [!DNL Target]でJSONとして書き出された[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]は、VECを使用して作成されたアクティビティでは使用できません。VEC ベースのアクティビティでは、HTML [!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]のみがサポートされます。 JSON [!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]を使用する場合は、[&#x200B; フォームベースのエクスペリエンスコンポーザー](/help/main/c-experiences/form-experience-composer.md)を使用して作成したアクティビティでそれらを使用します。

**フォームベースのExperience Composer[!UICONTROL を使用して[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]を利用するには]:**

1. [!DNL Target]で、[&#x200B; フォームベースのExperience Composer](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)でエクスペリエンスを作成または編集する際に、[!DNL AEM] コンテンツを挿入するページ上の場所を選択し、**[!UICONTROL 詳細]** アイコン （![詳細アイコン &#x200B;](/help/main/assets/icons/MoreSmall.svg)）をクリックし、**[!UICONTROL エクスペリエンスフラグメントを変更]**&#x200B;を選択して、[!UICONTROL &#x200B; エクスペリエンスフラグメントを変更] ダイアログボックスを表示します。

   ![experience_fragment_list image](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

   [!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;] ダイアログボックスには、[!DNL AEM]で作成されたコンテンツが表示され、[!DNL Target]内からネイティブに利用できるようになりました。

1. 必要な[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]を選択し、**[!UICONTROL 追加]**&#x200B;をクリックします。
1. アクティビティの設定を終了します。

## 追加情報

* [!DNL Target]は現在、10分ごとに[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]を読み込みます。 インポートされた[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]は[!DNL Target]内に10分以内に利用できるようになりますが、この時間枠は今後短くなります。
* [!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]は、[!DNL Target]にHTMLまたはJSON オファーとして読み込まれます。 [!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;] 「プライマリ」バージョンは[!DNL AEM]に残ります。 [!DNL Target]では[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]を編集できません。
* [!DNL Adobe Developer]を使用して[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]を作成することはできません。 上記のように、AEMを使用して[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]を作成します。
* AEMで[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]を更新した場合、[!DNL Target]が最新の変更を使用できるように、[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]を公開して[!DNL Target]に再度書き出す必要があります。

## [!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]からクライアントライブラリと無関係なHTMLを削除し、[!UICONTROL Target]に書き出しました

AEMによって配信されたページで[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]のオファーを[!DNL Target]と共に使用する場合、ターゲットページには必要なクライアントライブラリが既に含まれています。 また、オファー内の不要な HTML 要素も必要ありません。

HTML ページ全体で[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]がラップされ、問題が発生することがあります。 [!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]がHTMLの小さな部分であり、HTML、HEAD、BODYなどを含むHTMLの完全なページでないことを確認します。

詳しくは、次のブログ記事を参照してください。[AEM 6.5: [!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]からのclientlibの削除をTarget](https://www.linkedin.com/pulse/aem-65-removing-clientlibs-from-experience-fragments-exported-haser/){target=_blank}に書き出しました。

## トレーニングビデオ：[!DNL Adobe Target]でのAEM [!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]の使用

次のビデオでは、[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]を設定して使用する方法を示します。

>[!VIDEO](https://video.tv.adobe.com/v/38085?captions=jpn)

>[!NOTE]
>
>4:54で説明されている[!DNL AEM]のディープリンク機能が削除されました。

詳しくは、*AEM Sitesのビデオとチュートリアル* ページの[Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html?lang=ja)での[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]の使用を参照してください。
