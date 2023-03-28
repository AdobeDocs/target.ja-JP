---
keywords: エクスペリエンス;json;AEM, Adobe Experience Manager;Adobe Target へのエクスポート;エクスペリエンスフラグメント;フラグメント;XF
description: 使用方法を学ぶ [!DNL Adobe Experience Manager] [!UICONTROL エクスペリエンスフラグメント] in [!DNL Adobe Target] アクティビティ。
title: 使用方法 [!DNL Adobe Experience Manager] (AEM) [!UICONTROL エクスペリエンスフラグメント]?
feature: Integrations
source-git-commit: 0135831b56c48b0adca49e843c5ddd6574358aa4
workflow-type: tm+mt
source-wordcount: '1346'
ht-degree: 32%

---

# AEM [!UICONTROL エクスペリエンスフラグメント]

用途 [!UICONTROL エクスペリエンスフラグメント] (XF) が [!DNL Adobe Experience Manager] (AEM) [!DNL Target] アクティビティを活用して、最適化やパーソナライゼーションを支援します。

>[!NOTE]
>
>AEMを使用する際は、次の点に注意してください。 [!UICONTROL エクスペリエンスフラグメント] in [!DNL Target]:
> 
>* この機能を使用するには、 [!DNL Adobe Experience Manager] (AEM) 顧客。 詳しくは、 [要件](#section_AE6F0971E1574B3AA324003599B96E5A) 下
>* この機能は、次のアクティビティタイプで使用できます。 [!UICONTROL A/B テスト], [!UICONTROL 自動配分], [!UICONTROL 自動ターゲット], [!UICONTROL Automated Personalization] (AP) および [!UICONTROL エクスペリエンスのターゲット設定] (XT)。 この機能は、 [!UICONTROL 多変量分析テスト] (MVT) および [!UICONTROL Recommendations] アクティビティ。
>
>* 消費可能 [!UICONTROL エクスペリエンスフラグメント] in [!DNL Target] アクティビティ [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) または [フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md).


AEMの詳細を確認するには [!UICONTROL エクスペリエンスフラグメント] コンテンツフラグメントについては、 [AEM [!UICONTROL エクスペリエンスフラグメント] およびコンテンツフラグメントの概要](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## 要件 {#requirements}

をプロビジョニングする必要があります。 [!UICONTROL エクスペリエンスフラグメント] の機能 [!DNL Target]. また、 [!DNL AEM] as a Cloud Serviceまたは [!DNL AEM] 6.4（以降） アカウント担当者が、この機能を利用するための条件を満たすお手伝いをいたします。

* [!DNL Adobe Experience Manager ] as a Cloud Service
* [!DNL Adobe Experience Manager] 6.5.
* [!DNL Adobe Experience Manager] 6.4.
* [!DNL Adobe Target Standard] または [!DNL Adobe Target Premium] アカウント

[!DNL Adobe Experience Manager] 6.3 および 6.4 は提供終了となり、サポート対象外になりました（拡張サポートを購入したお客様を除く）。

統合の有効化と認証の詳細情報については、[Adobe Target カスタマーケア](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)にお問い合わせください。

## 作成と設定 [!UICONTROL エクスペリエンスフラグメント] in [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

を使用するには [!DNL AEM] [!UICONTROL エクスペリエンスフラグメント] in [!DNL Target]を使用する場合は、次の手順を実行する必要があります。

### 手順 1：[!DNL AEM] と [!DNL Target] を統合する

詳しくは、次を参照してください。

* **AEMas a Cloud Service**: [Adobe Targetとの統合](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/integrating-adobe-target.html){target=_blank} 内 *Experience Manageras a Cloud Service* ガイド。
* **Adobe I/O**：[管理ユーザーガイド](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/integration-ims-adobe-io.html?lang=ja)ドキュメントの {target=_blank}Adobe I/O を使用した Adobe Target との統合&#x200B;**。
* **[!DNL AEM]6.5**：[Adobe Experience Manager 6.5](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/opt-in.html?lang=ja) ドキュメントの {target=_blank}Adobe Analytics と Adobe Target へのオプトイン&#x200B;**。
* **[!DNL AEM]6.4**：[Adobe Experience Manager 6.4](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html?lang=ja) ドキュメントの {target=_blank}Adobe Analytics と Adobe Target へのオプトイン&#x200B;**。

### 手順 2:エクスペリエンスフラグメントを作成する

[!UICONTROL エクスペリエンスフラグメント] 次で作成： [!DNL AEM]. 詳しくは、次を参照してください。

* **AEMas a Cloud Service**: [[!UICONTROL エクスペリエンスフラグメント]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/experience-fragments.html?lang=en){target=_blank} 内 *Experience Manageras a Cloud Service* ガイド。
* **[!DNL AEM]6.5**：[Adobe Experience Manager 6.5](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/authoring/experience-fragments.html?lang=ja) ドキュメントの{target=_blank}エクスペリエンスフラグメント&#x200B;**。
* **[!DNL AEM]6.4**：[Adobe Experience Manager 6.4](https://experienceleague.adobe.com/docs/experience-manager-64/authoring/authoring/experience-fragments.html?lang=ja) ドキュメントの{target=_blank}エクスペリエンスフラグメント&#x200B;**。

### 手順 3:設定 [!DNL AEM] エクスペリエンスフラグメントを共有するには [!DNL Target]

1. 内から [!DNL AEM]」をクリックし、目的のエクスペリエンスフラグメントまたはそれを含むフォルダーを選択して、 **[!UICONTROL プロパティ]**.
2. 「**[!UICONTROL クラウドサービス]**」タブをクリックし、**[!UICONTROL クラウドサービスの設定]**&#x200B;ドロップダウンリストから「**[!UICONTROL Adobe Target]**」を選択します。

   前の手順では、組織内のユーザーが [!DNL Adobe Target] 設定を既に作成していることを前提としています。

3. 「**[!UICONTROL 保存して閉じる]**」をクリックします。

### 手順 4:エクスペリエンスフラグメントを公開し、次に書き出します。 [!DNL Target]

[!DNL AEM] のバージョンに応じて、次のリンクを参照して手順を確認してください。

* **AEMas a Cloud Service**: [書き出し [!UICONTROL エクスペリエンスフラグメント] Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/experience-fragments-target.html?lang=en){target=_blank} 内 *Experience Manageras a Cloud Service* ガイド。
* **[!DNL AEM]6.5**：[Adobe Experience Manager 6.5](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/experience-fragments-target.html?lang=en) ドキュメントの {target=_blank}Target へのエクスペリエンスフラグメントの書き出し&#x200B;**。
* **[!DNL AEM]6.4**：[Adobe Experience Manager 6.4](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/experience-fragments-target.html?lang=ja) ドキュメントの {target=_blank}Target へのエクスペリエンスフラグメントの書き出し&#x200B;**。

## 使用 [!UICONTROL エクスペリエンスフラグメント] in [!DNL Target] アクティビティ {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

上記のタスクを実行すると、エクスペリエンスフラグメントが [!UICONTROL オファー] ページ内 [!DNL Target].

[!DNL Target] は現在 [!UICONTROL エクスペリエンスフラグメント] を 10 分ごとにインポートします。 読み込まれたエクスペリエンスフラグメントは、で使用できるはずです。 [!DNL Target] 10 分以内に、しかし、今後はこの時間枠が短くなるはずです。

エクスペリエンスフラグメントは、 [!DNL Target] をHTMLまたは JSON オファーとして設定する。 そのエクスペリエンスフラグメントの「プライマリ」バージョンは、 [!DNL AEM]. [!DNL Target] 内のエクスペリエンスフラグメントは編集できません。

フィルターおよび検索条件は、 [!UICONTROL HTMLXF] および [!UICONTROL JSON XFs] に書き出されるエクスペリエンスフラグメントタイプを区別するのに役立ちます。 [!DNL Target].

![エクスペリエンスフラグメントタイプでフィルター：Target UI でのHTMLまたは JSON](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

リスト内のエクスペリエンスフラグメントにマウスポインターを置いて、 [!UICONTROL 表示] アイコン ![情報アイコン](/help/main/c-integrating-target-with-mac/aem/assets/icon-info.png) をクリックすると、エクスペリエンスフラグメントに関する追加情報 ( [!UICONTROL 名前], [!UICONTROL タイプ], [!UICONTROL オファー ID], [!UICONTROL オファーパス]、および最後の変更情報。 次をクリック： [!UICONTROL オファーの使用状況] タブをクリックして、このオファーを参照するアクティビティを表示します。

![エクスペリエンスフラグメント情報ポップアップ](/help/main/c-integrating-target-with-mac/aem/assets/xf-info-popup.png)

消費可能 [!UICONTROL エクスペリエンスフラグメント] in [!DNL Target] アクティビティ [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) または [フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md).


>[!TIP]
>
>人工知能、機械学習、および推奨事項を [!UICONTROL エクスペリエンスフラグメント]:
>
>* を完全に使用するには [!DNL Target] AI および ML 機能では、 [自動配分](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) または [自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md) をクリックします。
>
>* [!UICONTROL エクスペリエンスフラグメント] は、 [!DNL Recommendations] アクティビティ。 ただし、 [!UICONTROL エクスペリエンスフラグメント] レコメンデーションの場合は、 [!UICONTROL A/B テスト] アクティビティ ( [!UICONTROL 自動配分] および [!UICONTROL 自動ターゲット]) または [!UICONTROL エクスペリエンスのターゲット設定] (XT) アクティビティと [レコメンデーションをオファーとして含める](/help/main/c-recommendations/recommendations-as-an-offer.md).


**VEC でエクスペリエンスフラグメントを使用するには：**

1. [!DNL Target] の [Visual Experience Composer](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D) でエクスペリエンスを作成または編集する際に、[!DNL AEM] コンテンツを挿入するページ上の場所をクリックし、目的のオプションを選択して「[!UICONTROL エクスペリエンスフラグメントを選択]」リストを表示します。

   * [!UICONTROL 前に挿入]
   * [!UICONTROL 後ろに挿入]
   * [!UICONTROL エクスペリエンスフラグメントに置き換え]

   この [!UICONTROL エクスペリエンスフラグメント] リストには、 [!DNL AEM] 現在は、内からネイティブで利用可能です。 [!DNL Target].

   >[!NOTE]
   >
   >「[!UICONTROL エクスペリエンスフラグメントと交換]」オプションは、画像には使用できません。画像にこのオプションを使用する場合は、目的の画像を含むコンテナ要素をクリックします。

   ![experience_fragment_list 画像](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

1. 目的のエクスペリエンスフラグメントを選択し、 **[!UICONTROL 完了]**.
1. アクティビティの設定を終了します。

   各タイプのアクティビティを設定する方法について詳しくは、次のトピックを参照してください。

   * **A/B テスト：** [A/B テストの作成](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
   * **自動配分：** [自動配分](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **自動ターゲット：** [自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * **Automated Personalizationアクティビティ（AP）：**[Automated Personalizationアクティビティの作成](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **エクスペリエンスターゲット設定（XT）：** [エクスペリエンスのターゲット設定アクティビティの作成](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **A/B テストまたは XT アクティビティのRecommendations:** [Recommendations as a offer](/help/main/c-recommendations/recommendations-as-an-offer.md)

   [!UICONTROL エクスペリエンスフラグメント] で JSON として書き出されました [!DNL Target] は、VEC を使用して作成されたアクティビティでは使用できません。唯一のHTML [!UICONTROL エクスペリエンスフラグメント] は、VEC ベースのアクティビティでサポートされています。 JSON を使用する場合 [!UICONTROL エクスペリエンスフラグメント]を使用する場合は、 [フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md).

**フォームベースの Experience Composer でエクスペリエンスフラグメントを使用するには：**

1. [!DNL Target] の[フォームベース Experience Composer](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) でエクスペリエンスを作成または編集する際に、[!DNL AEM] コンテンツを挿入するページ上の場所を選択し、「**[!UICONTROL エクスペリエンスフラグメントを変更]**」を選択して「[!UICONTROL エクスペリエンスフラグメントを選択]」リストを表示します。

   ![experience_fragment_list 画像](/help/main/c-integrating-target-with-mac/aem/assets/experience_fragment_list.png)

   この [!UICONTROL エクスペリエンスフラグメント] リストには、 [!DNL AEM] 現在は、内からネイティブで利用可能です。 [!DNL Target].

1. 目的のエクスペリエンスフラグメントを選択し、 **[!UICONTROL 保存]**.
1. アクティビティの設定を終了します。

## 注意点 {#considerations}

* [!DNL Target] は現在 [!UICONTROL エクスペリエンスフラグメント] を 10 分ごとにインポートします。 読み込まれたエクスペリエンスフラグメントは、で使用できるはずです。 [!DNL Target] 10 分以内に、しかし、今後はこの時間枠が短くなるはずです。
* エクスペリエンスフラグメントは、 [!DNL Target] をHTMLまたは JSON オファーとして設定する。 エクスペリエンスフラグメントの「プライマリ」バージョンは、 [!DNL AEM]. でエクスペリエンスフラグメントを編集することはできません。 [!DNL Target].
* 次を作成することはできません： [!UICONTROL エクスペリエンスフラグメント] using [!DNL Adobe I/O]. 作成 [!UICONTROL エクスペリエンスフラグメント] 上述のように、AEMを使用します。
* AEMでエクスペリエンスフラグメントを更新する場合は、エクスペリエンスフラグメントを公開し、に書き出す必要があります。 [!DNL Target] 再び [!DNL Target] では、最新の変更を使用できます。

## からの ClientLibs と不要なHTMLの削除 [!UICONTROL エクスペリエンスフラグメント] 書き出し先 [!UICONTROL ターゲット]

エクスペリエンスフラグメントオファーを [!DNL Target] AEMが配信するページでは、ターゲットページに必要なすべてのクライアントライブラリが既に含まれています。 また、不要なHTML要素もオファーに含める必要はありません。

HTMLページ全体がエクスペリエンスフラグメントをラップして問題を引き起こす場合があります。 エクスペリエンスフラグメントが小さなHTMLであり、HTML、HEAD、BODY などを含む完全なHTMLページではないことを確認します。

詳しくは、次のブログ投稿を参照してください。 [AEM 6.5:ClientLibs の削除元 [!UICONTROL エクスペリエンスフラグメント] Target にエクスポート済み](https://www.linkedin.com/pulse/aem-65-removing-clientlibs-from-experience-fragments-exported-haser){target=_blank}.

## トレーニングビデオ：AEMの使用 [!UICONTROL エクスペリエンスフラグメント] と [!DNL Adobe Target]

次のビデオでは、の設定方法と使用方法を示します [!UICONTROL エクスペリエンスフラグメント]:

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>4:54 で取り上げた [!DNL AEM] ディープリンク機能は削除されました。

詳しくは、 [使用 [!UICONTROL エクスペリエンスフラグメント] Adobe Target](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html?lang=ja) の *AEM SitesのビデオとTutorials* ページ。