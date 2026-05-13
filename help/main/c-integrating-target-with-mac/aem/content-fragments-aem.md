---
keywords: エクスペリエンス;json;AEM;Adobe Experience Manager;Adobe Target への書き出し;コンテンツフラグメント;フラグメント;CF;cf;ヘッドレス;パーソナライゼーション;実験
description: ' [!DNL Adobe Target]  アクティビティで [!DNL Adobe Experience Manager] [!UICONTROL Content Fragments]を使用する方法を説明します。'
title: ' [!DNL Adobe Experience Manager]  （AEM） [!UICONTROL Content Fragments]の使用方法を教えてください。'
feature: Integrations
exl-id: 2057d9fe-c0f9-41d5-82e1-529db9ef7ca5
TQID: https://experienceleague.adobe.com/tb500kFSZoR3czs10Gs3EIOWEX2ybnd7tSWwDmWSMWQ
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: f7c7de77-382f-4f48-8b36-61a170f06d3d
topic_v2:
  - id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8c
  - id: bcc5edb5-84c3-4940-9f84-ed88b6c16274
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 626
ht-degree: 22%

---

# AEM [!UICONTROL Content Fragments]

[!DNL Target]件のアクティビティの[!DNL Adobe Experience Manager] （AEM）で作成された[!UICONTROL Content Fragments] （CF）を使用して、ヘッドレスのパーソナライゼーションと実験を支援します。

## 注意点

[!DNL Target]でAEM [!UICONTROL Content Fragments]を使用する場合は、次の点を考慮してください。

* この機能を使用するには、[!DNL Adobe Experience Manager as a Cloud Service] の顧客である必要があります。 詳しくは、次の[要件](#section_AE6F0971E1574B3AA324003599B96E5A)を参照してください。
* [!UICONTROL Experience Fragments]と[!UICONTROL Content Fragments]は、次のアクティビティタイプで使用できます。

   * [[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Automated Personalization] （AP）](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL Experience Targeting] （XT）](/help/main/c-activities/t-experience-target/experience-target.md)

* [!UICONTROL Experience Fragments]と[!UICONTROL Content Fragments]は、次のアクティビティの種類では利用できません：

   * [[!UICONTROL Multivariate Test] （MVT）](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)

* [&#x200B; フォームベースのExperience Composer](/help/main/c-experiences/form-experience-composer.md)のみを使用して、[!DNL Target]のアクティビティで[!UICONTROL Content Fragments]を使用できます。 *では、[!UICONTROL Visual Experience Composer] （VEC）を使用して[!DNL Target] アクティビティで[!UICONTROL Content Fragments]を使用できません。*

AEM [!UICONTROL Content Fragments]と[!UICONTROL Experience Fragments]について詳しくは、[AEM [!UICONTROL Experience Fragments]と[!UICONTROL Content Fragments]の概要](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md)を参照してください。

## 要件 {#requirements}

[[!DNL AEM] as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html?lang=ja){target=_blank}を使用している必要があります。 アカウント担当者が、この機能を利用するための条件を満たすお手伝いをいたします。

統合の有効化と認証の詳細情報については、[Adobe Target カスタマーケア](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)にお問い合わせください。

## [!DNL AEM]での[!UICONTROL Content Fragments]の設定と操作 {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

[!UICONTROL Content Fragments]を書き出して[!DNL Target]のアクティビティで使用するには、AEMでいくつかの事前手順を実行する必要があります。 詳しくは、*Experience Manager as a Cloud Service ドキュメント*&#x200B;の「[&#x200B; コンテンツフラグメントをAdobe Targetに書き出す](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/content-fragments-target.html?lang=ja){target=_blank}」を参照してください。

[!UICONTROL Content Fragments]のデザイン、作成、キュレーション、公開について詳しくは、[Experience Manager as a Cloud Service ドキュメント &#x200B;](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/home.html?lang=ja){target=_blank}の[[!UICONTROL Content Fragments]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/content-fragments.html?lang=ja){target=_blank}および[&#x200B; コンテンツフラグメントの操作](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragments.html?lang=ja){target=_blank}を参照してください。

## [!DNL Target]のアクティビティで[!UICONTROL Content Fragments]を使用しています {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

上記のタスクを実行すると、[!UICONTROL Content Fragment]が[!DNL Target]の[!UICONTROL Offers] ページに表示されます。

[!DNL Target]は現在、10分ごとに[!UICONTROL Content Fragments]を読み込みます。 インポートされた[!UICONTROL Content Fragment]は10分以内に[!DNL Target]で利用できるようになりますが、この時間枠は今後さらに短縮されます。

[!UICONTROL Content Fragment]は[!DNL Target]にJSON オファーとして読み込まれます。 [!UICONTROL Content Fragment] 「プライマリ」バージョンは[!DNL AEM]に残ります。 [!UICONTROL Content Fragment]を[!DNL Target]で編集することはできません。

[!UICONTROL HTML XFs]、[!UICONTROL JSON XFs]および[!UICONTROL Content Fragments]でフィルタリングして検索し、[!DNL Target]に書き出されるさまざまなオファータイプを区別するのに役立ちます。

![コンテンツフラグメントタイプでのフィルタリング：Target UI の HTML または JSON](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

リスト内の[!UICONTROL Experience Fragment]にカーソルを合わせ、[!UICONTROL View] アイコン ![情報アイコン &#x200B;](/help/main/assets/icons/InfoOutline.svg)をクリックして、[!UICONTROL Content Fragment]に関する追加情報（その[!UICONTROL Name]、[!UICONTROL Type]、[!UICONTROL Offer ID]、[!UICONTROL Offer path]、および最後の変更情報を含む）を表示できます。 このオファーを参照するアクティビティを表示するには、[!UICONTROL [!UICONTROL View Full Details]]をクリックします。

[&#x200B; フォームベースのExperience Composer](/help/main/c-experiences/form-experience-composer.md)のみを使用して、[!DNL Target]のアクティビティで[!UICONTROL Content Fragments]を使用できます。 *Visual Experience Composer[&#128279;](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) （VEC）を使用して、[!DNL Target]のアクティビティで[!UICONTROL Content Fragments]を*&#x200B;利用できません。 [!UICONTROL Content Fragments]は[!DNL Target]でJSONとして書き出され、VECを使用して作成されたアクティビティでは使用できません。

>[!TIP]
>
>[!UICONTROL Content Fragments]で人工知能、機械学習、レコメンデーションを使用：
>
>* [!DNL Target]のAIおよびML機能を完全に使用するには、[!UICONTROL A/B Test] アクティビティの作成中に[自動割り当て](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)または[自動ターゲット &#x200B;](/help/main/c-activities/auto-target/auto-target-to-optimize.md)を選択できます。
>
>* [!UICONTROL Content Fragments]は[!DNL Recommendations] アクティビティではサポートされていません。 ただし、レコメンデーションに[!UICONTROL Content Fragments]を使用するには、[!UICONTROL A/B Test]のアクティビティ（[!UICONTROL Auto-Allocate]と[!UICONTROL Auto-Target]を含む）または[!UICONTROL Experience Targeting] （XT）のアクティビティを作成し、[&#x200B; レコメンデーションをオファー](/help/main/c-recommendations/recommendations-as-an-offer.md)として含めることができます。

**[!UICONTROL Form-based Experience Composer]を使用して[!UICONTROL Content Fragments]を利用するには：**

1. [!DNL Target]で、[&#x200B; フォームベースのExperience Composer](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)でエクスペリエンスを作成または編集する際に、[!DNL AEM] コンテンツを挿入するページ上の場所を選択し、**[!UICONTROL Change Content Fragment]**&#x200B;を選択して[!UICONTROL Choose a Content Fragment] リストを表示します。

   ![content_fragment_list image](/help/main/c-integrating-target-with-mac/aem/assets/choose-content-fragment.png)

   [!UICONTROL Content Fragment] リストには、[!DNL AEM]で作成されたコンテンツが表示されます。このコンテンツは、[!DNL Target]内からネイティブに利用できるようになりました。

1. 目的の[!UICONTROL Content Fragment]を選択し、**[!UICONTROL Save]**&#x200B;をクリックします。
1. アクティビティの設定を終了します。

## 追加情報

* [!DNL Target]は現在、10分ごとに[!UICONTROL Content Fragments]を読み込みます。 インポートされた[!UICONTROL Content Fragment]は10分以内に[!DNL Target]で利用できるようになりますが、この時間枠は今後さらに短縮されます。
* [!UICONTROL Content Fragment]は[!DNL Target]にJSON オファーとして読み込まれます。 [!UICONTROL Content Fragment] 「プライマリ」バージョンは[!DNL AEM]に残ります。 [!UICONTROL Content Fragment]を[!DNL Target]で編集することはできません。
* [!DNL Adobe I/O]を使用して[!UICONTROL Content Fragments]を作成することはできません。 上記のように、AEMを使用して[!UICONTROL Content Fragments]を作成します。
* AEMで[!UICONTROL Content Fragment]を更新する場合、[!DNL Target]が最新の変更を使用できるように、[!UICONTROL Content Fragment]を公開して[!DNL Target]に再度書き出す必要があります。
