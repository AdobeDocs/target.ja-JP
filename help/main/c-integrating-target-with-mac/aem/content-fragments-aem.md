---
keywords: エクスペリエンス;json;AEM;Adobe Experience Manager;Adobe Target への書き出し;コンテンツフラグメント;フラグメント;CF;cf;ヘッドレス;パーソナライゼーション;実験
description: ' [!DNL Adobe Target]  アクティビティで [!DNL Adobe Experience Manager] [!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]を使用する方法について説明します。'
title: ' [!DNL Adobe Experience Manager]  （AEM） [!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]の使用方法を教えてください。'
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
source-wordcount: 775
ht-degree: 20%

---

# AEM [!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]

[!DNL Target]件のアクティビティで[!DNL Adobe Experience Manager] （AEM）で作成された[!UICONTROL &#x200B; コンテンツフラグメント &#x200B;] （CF）を使用して、ヘッドレスのパーソナライゼーションと実験を支援します。

## 注意点

[!DNL Target]でAEM [!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]を使用する場合は、次の点を考慮してください。

* この機能を使用するには、[!DNL Adobe Experience Manager as a Cloud Service] の顧客である必要があります。 詳しくは、次の[要件](#section_AE6F0971E1574B3AA324003599B96E5A)を参照してください。
* [!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]と[!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]は、次のアクティビティタイプで使用できます。

   * [[!UICONTROL A/B テスト]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL 自動配分]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL 自動ターゲット]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Automated Personalization]（AP）](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL エクスペリエンスのターゲット設定]（XT）](/help/main/c-activities/t-experience-target/experience-target.md)

* [!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]と[!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]は、次のアクティビティタイプでは使用できません。

   * [[!UICONTROL 多変量分析テスト] （MVT）](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL レコメンデーション]](/help/main/c-recommendations/recommendations.md)

* [&#x200B; フォームベースのExperience Composer](/help/main/c-experiences/form-experience-composer.md)のみを使用して、[!DNL Target]のアクティビティで[!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]を使用できます。 [!UICONTROL Visual Experience Composer] （VEC）を使用して、[!DNL Target] アクティビティで&#x200B;*コンテンツフラグメント*&#x200B;が[!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]を使用できません。

AEM [!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]および[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]について詳しくは、[AEM [!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]および[!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]の概要](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md)を参照してください。

## 要件 {#requirements}

[[!DNL AEM] as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html?lang=ja){target=_blank}を使用している必要があります。 アカウント担当者が、この機能を利用するための条件を満たすお手伝いをいたします。

統合の有効化と認証の詳細情報については、[Adobe Target カスタマーケア](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)にお問い合わせください。

## [!DNL AEM]の[!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]の設定と操作 {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

[!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]を書き出して[!DNL Target]のアクティビティで使用するには、AEMでいくつかの事前手順を実行する必要があります。 詳しくは、*Experience Manager as a Cloud Service ドキュメント*&#x200B;の「[&#x200B; コンテンツフラグメントをAdobe Targetに書き出す](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/content-fragments-target.html?lang=ja){target=_blank}」を参照してください。

[!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]のデザイン、作成、キュレーション、公開について詳しくは、[Experience Manager as a Cloud Service ドキュメント &#x200B;](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/home.html?lang=ja){target=_blank}の[[!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/content-fragments.html?lang=ja){target=_blank}および[&#x200B; コンテンツフラグメントの操作](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragments.html?lang=ja){target=_blank}を参照してください。

## [!DNL Target]のアクティビティで[!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]を使用 {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

上記のタスクを実行すると、[!DNL Target]の[!UICONTROL &#x200B; オファー] ページに[!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]が表示されます。

[!DNL Target]は現在、10分ごとに[!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]を読み込みます。 インポートされた[!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]は、[!DNL Target]で10分以内に利用できるようになりますが、この時間枠は今後も短縮されるべきです。

[!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]は、[!DNL Target]にJSON オファーとして読み込まれます。 [!UICONTROL &#x200B; コンテンツフラグメント &#x200B;] 「プライマリ」バージョンは[!DNL AEM]に残ります。 [!DNL Target]の[!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]は編集できません。

[!UICONTROL HTML XF]、[!UICONTROL JSON XF]、[!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]でフィルタリングおよび検索を行うことで、[!DNL Target]に書き出されるさまざまなオファータイプを区別できます。

![コンテンツフラグメントタイプでのフィルタリング：Target UI の HTML または JSON](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

リスト内の[!UICONTROL &#x200B; エクスペリエンスフラグメント &#x200B;]にカーソルを合わせ、[!UICONTROL 表示] アイコン ![情報アイコン &#x200B;](/help/main/assets/icons/InfoOutline.svg)をクリックすると、[!UICONTROL 名前]、[!UICONTROL 型]、[!UICONTROL &#x200B; オファーID]、[!UICONTROL &#x200B; オファーパス &#x200B;]、最終変更情報など、[!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]に関する追加情報を表示できます。 「[!UICONTROL [!UICONTROL 詳細を表示]]」をクリックして、このオファーを参照するアクティビティを表示します。

[&#x200B; フォームベースのExperience Composer](/help/main/c-experiences/form-experience-composer.md)のみを使用して、[!DNL Target]のアクティビティで[!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]を使用できます。 [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) （VEC）を使用して、[!DNL Target] アクティビティで&#x200B;*コンテンツフラグメント*&#x200B;が[!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]を使用できません。 [!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]は[!DNL Target]でJSONとして書き出され、VECを使用して作成されたアクティビティでは使用できません。

>[!TIP]
>
>[!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]で人工知能、機械学習、レコメンデーションを使用：
>
>* [!DNL Target]のAIおよびML機能を完全に使用するには、[!UICONTROL A/B テスト &#x200B;] アクティビティの作成中に[自動割り当て](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)または[自動ターゲット &#x200B;](/help/main/c-activities/auto-target/auto-target-to-optimize.md)を選択できます。
>
>* [!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]は、[!DNL Recommendations]のアクティビティではサポートされていません。 ただし、レコメンデーションに[!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]を使用するには、[!UICONTROL A/B テスト &#x200B;] アクティビティ（[!UICONTROL 自動配分]および[!UICONTROL 自動ターゲット &#x200B;]を含む）または[!UICONTROL &#x200B; エクスペリエンスのターゲット設定] （XT）アクティビティを作成し、[&#x200B; レコメンデーションをオファー](/help/main/c-recommendations/recommendations-as-an-offer.md)として含めることができます。

**フォームベースのExperience Composer[!UICONTROL を使用して[!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]を使用するには]:**

1. [!DNL Target]で、[&#x200B; フォームベースのExperience Composer](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)でエクスペリエンスを作成または編集する際に、[!DNL AEM] コンテンツを挿入するページ上の場所を選択し、**[!UICONTROL コンテンツフラグメントを変更]**&#x200B;を選択して[!UICONTROL &#x200B; コンテンツフラグメントを選択] リストを表示します。

   ![content_fragment_list image](/help/main/c-integrating-target-with-mac/aem/assets/choose-content-fragment.png)

   [!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]のリストには、[!DNL AEM]で作成されたコンテンツが表示され、[!DNL Target]内からネイティブに利用できるようになりました。

1. 目的の[!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]を選択し、**[!UICONTROL 保存]**&#x200B;をクリックします。
1. アクティビティの設定を終了します。

## 追加情報

* [!DNL Target]は現在、10分ごとに[!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]を読み込みます。 インポートされた[!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]は、[!DNL Target]で10分以内に利用できるようになりますが、この時間枠は今後も短縮されるべきです。
* [!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]は、[!DNL Target]にJSON オファーとして読み込まれます。 [!UICONTROL &#x200B; コンテンツフラグメント &#x200B;] 「プライマリ」バージョンは[!DNL AEM]に残ります。 [!DNL Target]の[!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]は編集できません。
* [!DNL Adobe I/O]を使用して[!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]を作成することはできません。 上記のように、AEMを使用して[!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]を作成します。
* AEMで[!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]を更新した場合、[!DNL Target]が最新の変更を使用できるように、[!UICONTROL &#x200B; コンテンツフラグメント &#x200B;]を公開して[!DNL Target]に再度書き出す必要があります。
