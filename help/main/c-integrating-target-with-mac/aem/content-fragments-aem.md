---
keywords: エクスペリエンス;json;AEM;Adobe Experience Manager;Adobe Target への書き出し;コンテンツフラグメント;フラグメント;CF;cf;ヘッドレス;パーソナライゼーション;実験
description: アクティビティでの使用方法  [!DNL Adobe Experience Manager] [!UICONTROL Content Fragments] 説明  [!DNL Adobe Target]  ます。
title: ' [!DNL Adobe Experience Manager]  （AEM） [!UICONTROL Content Fragments] の使用方法？'
feature: Integrations
exl-id: 2057d9fe-c0f9-41d5-82e1-529db9ef7ca5
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 21%

---

# AEM [!UICONTROL Content Fragments]

[!DNL Adobe Experience Manager] （AEM）で作成した [!UICONTROL Content Fragments] （CF）を [!DNL Target] アクティビティで使用して、ヘッドレスパーソナライゼーションと実験を支援します。

## 注意点

[!DNL Target] でAEM [!UICONTROL Content Fragments] を使用する際は、次の点を考慮してください。

* この機能を使用するには、[!DNL Adobe Experience Manager as a Cloud Service] の顧客である必要があります。詳しくは、次の[要件](#section_AE6F0971E1574B3AA324003599B96E5A)を参照してください。
* [!UICONTROL Experience Fragments] と [!UICONTROL Content Fragments] は、次のアクティビティタイプで使用できます。

   * [[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Automated Personalization] （AP）](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL Experience Targeting] （XT）](/help/main/c-activities/t-experience-target/experience-target.md)

* [!UICONTROL Experience Fragments] および [!UICONTROL Content Fragments] は、次のアクティビティタイプでは使用できません。

   * [[!UICONTROL Multivariate Test] （MVT）](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)

* [ フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) のみを使用して、[!DNL Target] アクティビティで [!UICONTROL Content Fragments] を使用できます。 [!UICONTROL Visual Experience Composer] （VEC *を使用して [!DNL Target] アクティビティで [!UICONTROL Content Fragments] を使用する* 使用できません）。

AEM [!UICONTROL Content Fragments] と [!UICONTROL Experience Fragments] について詳しくは、[AEM [!UICONTROL Experience Fragments] と [!UICONTROL Content Fragments] の概要 ](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md) を参照してください。

## 要件 {#requirements}

[[!DNL AEM]  を as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html?lang=ja){target=_blank} 使用している必要があります。アカウント担当者が、この機能を利用するための条件を満たすお手伝いをいたします。

統合の有効化と認証の詳細情報については、[Adobe Target カスタマーケア](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)にお問い合わせください。

## [!DNL AEM] での [!UICONTROL Content Fragments] の設定と使用 {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

[!UICONTROL Content Fragments] をエクスポートして [!DNL Target] アクティビティで使用するには、AEMでいくつかの準備手順を実行する必要があります。 詳しくは、[Experience Manager as a Cloud Service ドキュメント](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/content-fragments-target.html?lang=ja)の {target=_blank}Adobe Target へのコンテンツフラグメントの書き出し&#x200B;**&#x200B;を参照してください。

[!UICONTROL Content Fragments] のデザイン、作成、キュレーション、公開について詳しくは、[Experience Managerのas a Cloud Serviceに関するドキュメントの [[!UICONTROL Content Fragments]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/content-fragments.html?lang=ja){target=_blank} および [ コンテンツフラグメントの操作 ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragments.html?lang=ja){target=_blank} を参照してくだ ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/home.html?lang=ja){target=_blank} い。

## [!DNL Target] アクティビティでの [!UICONTROL Content Fragments] の使用 {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

上記のタスクを実行すると、[!UICONTROL Content Fragment] が [!DNL Target] の [!UICONTROL Offers] ページに表示されます。

[!DNL Target] は現在、読み込む [!UICONTROL Content Fragments] を 10 分ごとに検索します。 読み込んだ [!UICONTROL Content Fragment] は 10 分以内に [!DNL Target] で使用可能になります。ただし、この時間枠は今後短縮される予定です。

[!UICONTROL Content Fragment] は、JSON オファーとして [!DNL Target] に読み込まれます。 [!UICONTROL Content Fragment] の「プライマリ」バージョンは [!DNL AEM] にあります。 [!DNL Target] で [!UICONTROL Content Fragment] を編集することはできません。

[!UICONTROL HTML XFs]、[!UICONTROL JSON XFs]、[!UICONTROL Content Fragments] でフィルタリングおよび検索すると、[!DNL Target] に書き出される様々なオファータイプを区別できます。

![コンテンツフラグメントタイプでのフィルタリング：Target UI の HTML または JSON](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

リスト内の [!UICONTROL Content Fragment] にポインタを合わせ、「[!UICONTROL View]」アイコン ![ 情報アイコン ](/help/main/c-integrating-target-with-mac/aem/assets/icon-info.png) をクリックすると、[!UICONTROL AEM path] や [!UICONTROL AEM deep link] など、[!UICONTROL Content Fragment] に関する追加情報が表示されます。 「[!UICONTROL Offer Usage]」タブをクリックして、このオファーを参照するアクティビティを表示します。

![コンテンツフラグメント情報ポップアップ](/help/main/c-integrating-target-with-mac/aem/assets/cf-info-popup.png)

[ フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) のみを使用して、[!DNL Target] アクティビティで [!UICONTROL Content Fragments] を使用できます。 [Visual Experience Composer *VEC* を使用して [!DNL Target] アクティビティで [!UICONTROL Content Fragments] を使用することはできません ](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md)。 [!UICONTROL Content Fragments] は [!DNL Target] で JSON として書き出され、VEC を使用して作成されたアクティビティでは使用できません。

>[!TIP]
>
>次のような場合に、人工知能、機械学習、Recommendations を使用 [!UICONTROL Content Fragments] ます。
>
>* [!DNL Target] の AI 機能と ML 機能を最大限に活用するには、[!UICONTROL A/B Test] アクティビティの作成時、[ 自動配分 ](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) または [ 自動ターゲット ](/help/main/c-activities/auto-target/auto-target-to-optimize.md) を選択してください。
>
>* [!UICONTROL Content Fragments] は [!DNL Recommendations] アクティビティではサポートされていません。 ただし、Recommendations に [!UICONTROL Content Fragments] を使用するには、[!UICONTROL A/B Test] アクティビティ（[!UICONTROL Auto-Allocate] と [!UICONTROL Auto-Target] を含む）または [!UICONTROL Experience Targeting] アクティビティ（XT）を作成して、[Recommendations をオファーとして含める ](/help/main/c-recommendations/recommendations-as-an-offer.md) ことができます。

**[!UICONTROL Form-based Experience Composer] を使用して [!UICONTROL Content Fragments] を使用するには：**

1. [!DNL Target] の場合は、[ フォームベース Experience Composer](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) でエクスペリエンスを作成または編集する際に、[!DNL AEM] のコンテンツを挿入するページ上の場所を選択し、「**[!UICONTROL Change Content Fragment]**」を選択して [!UICONTROL Choose a Content Fragment] リストを表示します。

   ![content_fragment_list image](/help/main/c-integrating-target-with-mac/aem/assets/choose-content-fragment.png)

   [!UICONTROL Content Fragment] リストには、[!DNL AEM] で作成され、[!DNL Target] 内からネイティブで使用可能になったコンテンツが表示されます。

1. 目的の [!UICONTROL Content Fragment] を選択し、「**[!UICONTROL Save]**」をクリックします。
1. アクティビティの設定を終了します。

## 追加情報

* [!DNL Target] は現在、読み込む [!UICONTROL Content Fragments] を 10 分ごとに検索します。 読み込んだ [!UICONTROL Content Fragment] は 10 分以内に [!DNL Target] で使用可能になります。ただし、この時間枠は今後短縮される予定です。
* [!UICONTROL Content Fragment] は、JSON オファーとして [!DNL Target] に読み込まれます。 [!UICONTROL Content Fragment] の「プライマリ」バージョンは [!DNL AEM] にあります。 [!DNL Target] で [!UICONTROL Content Fragment] を編集することはできません。
* [!DNL Adobe I/O] を使用して [!UICONTROL Content Fragments] を作成することはできません。 前述のとおり、AEMを使用して [!UICONTROL Content Fragments] を作成します。
* AEMで [!UICONTROL Content Fragment] を更新する場合は、[!UICONTROL Content Fragment] を公開して [!DNL Target] に再度書き出し、最新の変更を使用でき [!DNL Target] ようにする必要があります。
