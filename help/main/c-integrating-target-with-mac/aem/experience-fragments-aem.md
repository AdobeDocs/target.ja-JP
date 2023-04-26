---
keywords: エクスペリエンス;json;AEM, Adobe Experience Manager;Adobe Target へのエクスポート;エクスペリエンスフラグメント;フラグメント;XF
description: ' [!DNL Adobe Target]  アクティビティで [!DNL Adobe Experience Manager] [!UICONTROL エクスペリエンスフラグメント]を使用する方法を説明します。'
title: ' [!DNL Adobe Experience Manager] （AEM）[!UICONTROL エクスペリエンスフラグメント]の使用方法?'
feature: Integrations
exl-id: 400d0cde-e435-4cac-9bf0-64a6cad98995
source-git-commit: 7c81362a82ca6692bb8c183b8e8fc50c6329e2e8
workflow-type: ht
source-wordcount: '1352'
ht-degree: 100%

---

# AEM [!UICONTROL エクスペリエンスフラグメント]

[!DNL Adobe Experience Manager]（AEM）で作成した[!UICONTROL エクスペリエンスフラグメント]（XF）を [!DNL Target] アクティビティで使用して、最適化とパーソナライズ機能を支援します。

## 注意点

[!DNL Target] で AEM [!UICONTROL エクスペリエンスフラグメント]を使用する際は、次の点を考慮してください。

* この機能を使用するには、[!DNL Adobe Experience Manager]（AEM）の顧客である必要があります。詳しくは、次の[要件](#section_AE6F0971E1574B3AA324003599B96E5A)を参照してください。
* [!UICONTROL エクスペリエンスフラグメント]と[!UICONTROL コンテンツフラグメント]は、次のアクティビティタイプで使用できます。

   * [[!UICONTROL A/B テスト]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL 自動配分]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL 自動ターゲット]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Automated Personalization]（AP）](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL エクスペリエンスのターゲット設定]（XT）](/help/main/c-activities/t-experience-target/experience-target.md)

* [!UICONTROL エクスペリエンスフラグメント]と[!UICONTROL コンテンツフラグメント]は、次のアクティビティタイプでは使用できません。

   * [[!UICONTROL 多変量分析テスト] （MVT）](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)

* [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md)（VEC）と[フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) を使用して、[!DNL Target] アクティビティ内で[!UICONTROL エクスペリエンスフラグメント]を使用できます。

AEM [!UICONTROL エクスペリエンスフラグメント]および[!UICONTROL コンテンツフラグメント]について詳しくは、[AEM [!UICONTROL エクスペリエンスフラグメント]およびコンテンツフラグメントの概要](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md)を参照してください。

## 要件 {#requirements}

[!DNL Target] 内で[!UICONTROL エクスペリエンスフラグメント]機能を使用して、プロビジョニングする必要があります。また、[!DNL AEM] as a Cloud Service または [!DNL AEM] 6.4（以降）を使用してください。アカウント担当者が、この機能を利用するための条件を満たすお手伝いをいたします。

* [!DNL Adobe Experience Manager ] as a Cloud Service
* [!DNL Adobe Experience Manager] 6.5
* [!DNL Adobe Experience Manager] 6.4
* [!DNL Adobe Target Standard] または [!DNL Adobe Target Premium] アカウント

[!DNL Adobe Experience Manager] 6.3 および 6.4 は提供終了となり、サポート対象外になりました（拡張サポートを購入した顧客を除く）。

統合の有効化と認証の詳細情報については、[Adobe Target カスタマーケア](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)にお問い合わせください。

## [!DNL AEM] で[!UICONTROL エクスペリエンスフラグメント]の作成および設定 {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

[!DNL AEM] [!UICONTROL エクスペリエンスフラグメント]を [!DNL Target] で使用するには、次の手順を実行する必要があります。

### 手順 1：[!DNL AEM] と [!DNL Target] を統合する

詳しくは、次を参照してください。

* **AEM as a Cloud Service**：*Experience Manager as a Cloud Service* ガイドにある [Adobe Target との統合](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/integrating-adobe-target.html?lang=ja){target=_blank}。
* **Adobe I/O**：[管理ユーザーガイド](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-ims-adobe-io.html?lang=ja)ドキュメントの {target=_blank}Adobe I/O を使用した Adobe Target との統合&#x200B;**。
* **[!DNL AEM]6.5**：[Adobe Experience Manager 6.5](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=ja) ドキュメントの {target=_blank}Adobe Analytics と Adobe Target へのオプトイン&#x200B;**。
* **[!DNL AEM]6.4**：[Adobe Experience Manager 6.4](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html?lang=ja) ドキュメントの {target=_blank}Adobe Analytics と Adobe Target へのオプトイン&#x200B;**。

### 手順 2：エクスペリエンスフラグメントを作成する

[!UICONTROL エクスペリエンスフラグメント]は [!DNL AEM] で作成されます。詳しくは、次を参照してください。

* **AEM as a Cloud Service**：*Experience Manager as a Cloud Service* ガイドにある[[!UICONTROL エクスペリエンスフラグメント]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/experience-fragments.html?lang=ja){target=_blank}。
* **[!DNL AEM]6.5**：[Adobe Experience Manager 6.5](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/authoring/experience-fragments.html?lang=ja) ドキュメントの{target=_blank}エクスペリエンスフラグメント&#x200B;**。
* **[!DNL AEM]6.4**：[Adobe Experience Manager 6.4](https://experienceleague.adobe.com/docs/experience-manager-64/authoring/authoring/experience-fragments.html?lang=ja) ドキュメントの{target=_blank}エクスペリエンスフラグメント&#x200B;**。

### 手順 3：[!UICONTROL エクスペリエンスフラグメント] を [!DNL Target] と共有するように [!DNL AEM] を設定する

1. [!DNL AEM] 内で目的の[!UICONTROL エクスペリエンスフラグメント]またはそれを含むフォルダーを選択し、「**[!UICONTROL プロパティ]**」をクリックします。
2. 「**[!UICONTROL クラウドサービス]**」タブをクリックし、**[!UICONTROL クラウドサービスの設定]**&#x200B;ドロップダウンリストから「**[!UICONTROL Adobe Target]**」を選択します。

   前の手順では、組織内のユーザーが [!DNL Adobe Target] 設定を既に作成していることを前提としています。

3. 「**[!UICONTROL 保存して閉じる]**」をクリックします。

### 手順 4：[!UICONTROL エクスペリエンスフラグメント]を公開し、[!DNL Target] に書き出す

[!DNL AEM] のバージョンに応じて、次のリンクを参照して手順を確認してください。

* **AEM as a Cloud Service**：[*Experience Manager as a Cloud Service* ガイドにある[!UICONTROL エクスペリエンスフラグメント]の Adobe Target への書き出し](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/experience-fragments-target.html?lang=ja){target=_blank}。
* **[!DNL AEM]6.5**：[Adobe Experience Manager 6.5](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/experience-fragments-target.html?lang=ja) ドキュメントの {target=_blank}Target へのエクスペリエンスフラグメントの書き出し&#x200B;**。
* **[!DNL AEM]6.4**：[Adobe Experience Manager 6.4](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html?lang=ja) ドキュメントの {target=_blank}Target へのエクスペリエンスフラグメントの書き出し&#x200B;**。

## [!DNL Target] アクティビティでの[!UICONTROL エクスペリエンスフラグメント]の使用 {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

上記のタスクを実行すると、[!UICONTROL エクスペリエンスフラグメント]が [!DNL Target] の[!UICONTROL オファー]ページに表示されます。

[!DNL Target] は現在、読み込む[!UICONTROL エクスペリエンスフラグメント]を 10 分ごとに検索します。読み込んだ[!UICONTROL エクスペリエンスフラグメント]は 10 分以内に [!DNL Target] で使用可能になります。ただし、この時間枠は今後短縮される予定です。

[!UICONTROL エクスペリエンスフラグメント]は、HTML または JSON オファーとして [!DNL Target] に読み込まれます。[!UICONTROL エクスペリエンスフラグメント]の「プライマリ」バージョンは [!DNL AEM] にあります。[!DNL Target] 内の[!UICONTROL エクスペリエンスフラグメント]は編集できません。

[!UICONTROL HTML XF] と [!UICONTROL JSON XF] でフィルタリングおよび検索すると、[!DNL Target] に書き出される[!UICONTROL エクスペリエンスフラグメント]タイプを区別できます。

![エクスペリエンスフラグメントタイプでのフィルタリング：Target UI の HTML または JSON](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

リスト内の[!UICONTROL エクスペリエンスフラグメント]にポインタを合わせ、[!UICONTROL 表示]アイコン ![情報アイコン](/help/main/c-integrating-target-with-mac/aem/assets/icon-info.png) をクリックすると、[!UICONTROL エクスペリエンスフラグメント]に関する追加情報（[!UICONTROL 名前]、[!UICONTROL タイプ]、[!UICONTROL オファー ID]、[!UICONTROL オファーパス]、最終変更情報など）が表示されます。「[!UICONTROL オファーの使用状況]」タブをクリックして、このオファーを参照するアクティビティを表示します。

![エクスペリエンスフラグメント情報ポップアップ](/help/main/c-integrating-target-with-mac/aem/assets/xf-info-popup.png)

[Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md)（VEC）と[フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) を使用して、[!DNL Target] アクティビティ内で[!UICONTROL エクスペリエンスフラグメント]を使用できます。


>[!TIP]
>
>次のような場合に、[!UICONTROL エクスペリエンスフラグメント]で人工知能（AI）、機械学習（ML）、Recommendations を使用します。
>
>* [!DNL Target] の AI 機能と ML 機能を最大限に活用するには、アクティビティの作成時、[自動配分](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)または[自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md)を選択してください。
>
>* [!UICONTROL エクスペリエンスフラグメント]は、[!DNL Recommendations] アクティビティではサポートされていません。ただし、Recommendations に[!UICONTROL エクスペリエンスフラグメント]を使用するには、[!UICONTROL A/B テスト]アクティビティ（[!UICONTROL 自動配分]と[!UICONTROL 自動ターゲット]を含む）または[!UICONTROL エクスペリエンスのターゲット設定]（XT）アクティビティを作成し、[Recommendations をオファーとして含める](/help/main/c-recommendations/recommendations-as-an-offer.md)ことができます。


**VEC で[!UICONTROL エクスペリエンスフラグメント]を使用するには：**

1. [!DNL Target] の [Visual Experience Composer](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D) でエクスペリエンスを作成または編集する際に、[!DNL AEM] コンテンツを挿入するページ上の場所をクリックし、目的のオプションを選択して「[!UICONTROL エクスペリエンスフラグメントを選択]」リストを表示します。

   * [!UICONTROL 前に挿入]
   * [!UICONTROL 後ろに挿入]
   * [!UICONTROL エクスペリエンスフラグメントに置き換え]

   [!UICONTROL エクスペリエンスフラグメント]リストには、[!DNL AEM] で作成され、[!DNL Target] 内からネイティブで使用可能になったコンテンツが表示されます。

   >[!NOTE]
   >
   >「[!UICONTROL エクスペリエンスフラグメントと交換]」オプションは、画像には使用できません。画像にこのオプションを使用する場合は、目的の画像を含むコンテナ要素をクリックします。

   ![experience_fragment_list image](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

1. 対象の[!UICONTROL エクスペリエンスフラグメント]を選択し、「**[!UICONTROL 完了]**」をクリックします。
1. アクティビティの設定を終了します。

   各タイプのアクティビティを設定する方法について詳しくは、次のトピックを参照してください。

   * **A/B テスト：** [A/B テストの作成](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **自動配分：** [自動配分](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **自動ターゲット：** [自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * **Automated Personalizationアクティビティ（AP）：**[Automated Personalizationアクティビティの作成](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **エクスペリエンスターゲット設定（XT）：** [エクスペリエンスのターゲット設定アクティビティの作成](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **A/B テストまたは XT アクティビティのRecommendations：** [オファーとしての Recommendations](/help/main/c-recommendations/recommendations-as-an-offer.md)

   [!DNL Target] で JSON として書き出された[!UICONTROL エクスペリエンスフラグメント]は、VEC を使用して作成されたアクティビティでは使用できません。VEC ベースのアクティビティでは、HTML [!UICONTROL エクスペリエンスフラグメント]のみがサポートされます。JSON [!UICONTROL エクスペリエンスフラグメント]を使用する場合は、[フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) を使用して作成されたアクティビティで使用します。

**[!UICONTROL フォームベースの Experience Composer] を使用して[!UICONTROL エクスペリエンスフラグメント]を使用するには：**

1. [!DNL Target] の[フォームベース Experience Composer](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) でエクスペリエンスを作成または編集する際に、[!DNL AEM] コンテンツを挿入するページ上の場所を選択し、「**[!UICONTROL エクスペリエンスフラグメントを変更]**」を選択して「[!UICONTROL エクスペリエンスフラグメントを選択]」リストを表示します。

   ![experience_fragment_list image](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

   [!UICONTROL エクスペリエンスフラグメント]リストには、[!DNL AEM] で作成され、[!DNL Target] 内からネイティブで使用可能になったコンテンツが表示されます。

1. 対象の[!UICONTROL エクスペリエンスフラグメント]を選択し、「**[!UICONTROL 保存]**」をクリックします。
1. アクティビティの設定を終了します。

## 追加情報

* [!DNL Target] は現在、読み込む[!UICONTROL エクスペリエンスフラグメント]を 10 分ごとに検索します。読み込んだ[!UICONTROL エクスペリエンスフラグメント]は 10 分以内に [!DNL Target] で使用可能になります。ただし、この時間枠は今後短縮される予定です。
* [!UICONTROL エクスペリエンスフラグメント]は、HTML または JSON オファーとして [!DNL Target] に読み込まれます。[!UICONTROL エクスペリエンスフラグメント]の「プライマリ」バージョンは [!DNL AEM] にあります。[!DNL Target] 内の[!UICONTROL エクスペリエンスフラグメント]は編集できません。
* [!DNL Adobe I/O] を使用して[!UICONTROL エクスペリエンスフラグメント]を作成することはできません。前述のとおり、[!UICONTROL エクスペリエンスフラグメント]は AEM を使用して作成してください。
* AEM で[!UICONTROL エクスペリエンスフラグメント]を更新する場合は、[!UICONTROL エクスペリエンスフラグメント]を公開して [!DNL Target] に再度書き出し、[!DNL Target] が最新の変更を使用できるようにする必要があります。

## [!UICONTROL Target] に書き出した[!UICONTROL エクスペリエンスフラグメント]から ClientLibs と不要な HTML の削除

AEM で配信されるページで [!DNL Target] を使用して[!UICONTROL エクスペリエンスフラグメント]オファーを使用する場合、ターゲットページには必要なすべてのクライアントライブラリが既に含まれています。また、オファー内の不要な HTML 要素も必要ありません。

HTML ページ全体で[!UICONTROL エクスペリエンスフラグメント]をラップし、問題を引き起こす場合があります。[!UICONTROL エクスペリエンスフラグメント]が HTML の小さな断片であり、HTML、HEAD、BODY などを含む完全な HTML ページではないことを確認します。

詳しくは、次ののブログ投稿（[AEM 6.5：Target に書き出された[!UICONTROL エクスペリエンスフラグメント]からの ClientLibs の削除](https://www.linkedin.com/pulse/aem-65-removing-clientlibs-from-experience-fragments-exported-haser){target=_blank}）を参照してください。

## トレーニングビデオ：[!DNL Adobe Target] と AEM [!UICONTROL エクスペリエンスフラグメント]の併用

次のビデオでは、[!UICONTROL エクスペリエンスフラグメント]の設定方法と使用方法を示します。

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>4:54 で取り上げた [!DNL AEM] ディープリンク機能は削除されました。

詳しくは、*AEM Sites のビデオとチュートリアル*&#x200B;ページの [Adobe Target での[!UICONTROL エクスペリエンスフラグメント]の使用](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html?lang=ja)を参照してください。
