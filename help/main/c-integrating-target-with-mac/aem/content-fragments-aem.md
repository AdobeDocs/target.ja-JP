---
keywords: エクスペリエンス;json;AEM;Adobe Experience Manager;Adobe Target への書き出し;コンテンツフラグメント;フラグメント;CF;cf;headless;personalization;experimentation
description: ' [!DNL Adobe Target]  アクティビティで  [!DNL Adobe Experience Manager] [!UICONTROL  コンテンツフラグメント]を使用する方法について説明します。'
title: ' [!DNL Adobe Experience Manager] （AEM）[!UICONTROL コンテンツフラグメント]の使用方法?'
badgePrerelease: label="Prerelease"
feature: Integrations
exl-id: 2057d9fe-c0f9-41d5-82e1-529db9ef7ca5
source-git-commit: 1cc328732bed41303ab0b1c6857dcbc812940022
workflow-type: tm+mt
source-wordcount: '779'
ht-degree: 82%

---

# AEM [!UICONTROL コンテンツフラグメント]

用途 [!UICONTROL コンテンツフラグメント] (CF) を [!DNL Adobe Experience Manager] (AEM) [!DNL Target] アクティビティを使用して、ヘッドレスなパーソナライゼーションと実験を支援します。

>[!NOTE]
>
>この機能は、2023 年 4 月 12 日にプレリリース機能として使用できるようになり、2023 年 4 月 26 日に GA（一般リリース）リリースで使用できるようになります。

## 注意点

[!DNL Target] で AEM [!UICONTROL コンテンツフラグメント]を使用する際は、次の点を考慮してください。

* この機能を使用するには、 [!DNL Adobe Experience Manager as a Cloud Service] 顧客。 詳しくは、次の[要件](#section_AE6F0971E1574B3AA324003599B96E5A)を参照してください。
* [!UICONTROL エクスペリエンスフラグメント] および [!UICONTROL コンテンツフラグメント] は、次のアクティビティタイプで使用できます。

   * [[!UICONTROL A/B テスト]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL 自動配分]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL 自動ターゲット]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Automated Personalization]（AP）](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL エクスペリエンスのターゲット設定]（XT）](/help/main/c-activities/t-experience-target/experience-target.md)

* [!UICONTROL エクスペリエンスフラグメント] および [!UICONTROL コンテンツフラグメント] は、次のアクティビティタイプでは使用できません。

   * [[!UICONTROL 多変量分析テスト] （MVT）](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL レコメンデーション]](/help/main/c-recommendations/recommendations.md)

* [フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) のみを使用して、[!DNL Target] アクティビティで[!UICONTROL コンテンツフラグメント]を使用できます。[!UICONTROL Visual Experience Composer]（VEC）を使用して [!DNL Target] アクティビティで[!UICONTROL コンテンツフラグメント]を使用することは&#x200B;*できません*。

AEM [!UICONTROL コンテンツフラグメント]および[!UICONTROL エクスペリエンスフラグメント]について詳しくは、[AEM [!UICONTROL エクスペリエンスフラグメント]および[!UICONTROL コンテンツフラグメント]の概要](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md)を参照してください。

## 要件 {#requirements}

[!DNL Target] 内の[!UICONTROL コンテンツフラグメント]機能を使用してプロビジョニングする必要があります。また、 [[!DNL AEM] as a Cloud Service](https://experienceleague.corp.adobe.com/docs/experience-manager-cloud-service.html){target=_blank}. アカウント担当者が、この機能を利用するための条件を満たすお手伝いをいたします。

統合の有効化と認証の詳細情報については、[Adobe Target カスタマーケア](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)にお問い合わせください。

## [!DNL AEM] での[!UICONTROL コンテンツフラグメント]の設定と使用 {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

[!UICONTROL コンテンツフラグメント]を書き出して [!DNL Target] アクティビティで使用するには、AEM でいくつかの準備手順を実行する必要があります。詳しくは、 [コンテンツフラグメントのAdobe Targetへの書き出し](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/content-fragments-target.html?lang=ja){target=_blank} 内 *Experience Manageras a Cloud Service文書*. このリンクは、リリース日（2023 年 4 月 13 日）に利用可能になります

[!UICONTROL コンテンツフラグメント]のデザイン、作成、キュレーション、公開について詳しくは、[[!UICONTROL コンテンツフラグメント]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/content-fragments.html?lang=ja){target=_blank} and [Working with Content Fragments](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragments.html?lang=ja){target=_blank} in the [Experience Manager as a Cloud Service documentation](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/home.html?lang=ja){target=_blank}を参照してください。

## [!DNL Target] アクティビティでの[!UICONTROL コンテンツフラグメントの使用] {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

上記のタスクを実行すると、[!UICONTROL コンテンツフラグメント]が [!DNL Target] の[!UICONTROL オファー]ページに表示されます。

[!DNL Target] は現在、読み込む[!UICONTROL コンテンツフラグメント]を 10 分ごとに検索します。読み込んだ[!UICONTROL コンテンツフラグメント]は 10 分以内に [!DNL Target] で使用可能になります。ただし、この時間枠は今後短縮される予定です。

[!UICONTROL コンテンツフラグメント]は、JSON オファーとして [!DNL Target] に読み込まれます。[!UICONTROL コンテンツフラグメント]の「プライマリ」バージョンは [!DNL AEM] にあります。[!DNL Target] 内の[!UICONTROL コンテンツフラグメント]は編集できません。

[!UICONTROL HTML XF]、[!UICONTROL JSON XF] および[!UICONTROL コンテンツフラグメント]でフィルタリングおよび検索すると、[!DNL Target] に書き出される様々なオファータイプを区別できます。

![コンテンツフラグメントタイプでのフィルタリング：Target UI の HTML または JSON](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

リスト内の[!UICONTROL コンテンツフラグメント]にポインタを合わせ、「[!UICONTROL 表示]」アイコン（ ![情報アイコン](/help/main/c-integrating-target-with-mac/aem/assets/icon-info.png)）をクリックすると、[!UICONTROL AEM パス]や [!UICONTROL AEM ディープリンク]など、[!UICONTROL コンテンツフラグメント]に関する追加情報が表示されます。「[!UICONTROL オファーの使用状況]」タブをクリックして、このオファーを参照するアクティビティを表示します。

![コンテンツフラグメント情報ポップアップ](/help/main/c-integrating-target-with-mac/aem/assets/cf-info-popup.png)

[フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) のみを使用して、[!DNL Target] アクティビティで[!UICONTROL コンテンツフラグメント]を使用できます。[Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md)（VEC）を使用して [!DNL Target] アクティビティで[!UICONTROL コンテンツフラグメント]を使用することは&#x200B;*できません*。[!UICONTROL コンテンツフラグメント]は [!DNL Target] で JSON として書き出され、VEC を使用して作成されたアクティビティでは使用できません。

>[!TIP]
>
>次のような場合に、[!UICONTROL コンテンツフラグメント]で人工知能、機械学習、Recommendations を使用します。
>
>* を完全に使用するには [!DNL Target] AI および ML 機能では、 [自動配分](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) または [自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md) 作成中に [!UICONTROL A/B テスト] アクティビティ。
>
>* [!UICONTROL コンテンツフラグメント]は、[!DNL Recommendations] アクティビティではサポートされていません。ただし、Recommendations に[!UICONTROL コンテンツフラグメント]を使用するには、[!UICONTROL A/B テスト]アクティビティ（[!UICONTROL 自動配分]と[!UICONTROL 自動ターゲット]を含む）または[!UICONTROL エクスペリエンスのターゲット設定]（XT）アクティビティを作成し、[Recommendations をオファーとして含める](/help/main/c-recommendations/recommendations-as-an-offer.md)ことができます。


**[!UICONTROL フォームベースの Experience Composer] を使用して[!UICONTROL コンテンツフラグメント]を使用するには：**

1. [!DNL Target] の[フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) でエクスペリエンスを作成または編集する際に、[!DNL AEM] コンテンツを挿入するページ上の場所を選択し、「**[!UICONTROL コンテンツフラグメントを変更]**」を選択して[!UICONTROL コンテンツフラグメントを選択]リストを表示します。

   ![content_fragment_list image](/help/main/c-integrating-target-with-mac/aem/assets/choose-content-fragment.png)

   [!UICONTROL コンテンツフラグメント]リストには、[!DNL AEM] で作成され、[!DNL Target] 内からネイティブで使用可能になったコンテンツが表示されます。

1. 対象の[!UICONTROL コンテンツフラグメント]を選択し、「**[!UICONTROL 保存]**」をクリックします。
1. アクティビティの設定を終了します。

## 追加情報

* [!DNL Target] は現在、読み込む[!UICONTROL コンテンツフラグメント]を 10 分ごとに検索します。読み込んだ[!UICONTROL コンテンツフラグメント]は 10 分以内に [!DNL Target] で使用可能になります。ただし、この時間枠は今後短縮される予定です。
* [!UICONTROL コンテンツフラグメント]は、JSON オファーとして [!DNL Target] に読み込まれます。[!UICONTROL コンテンツフラグメント]の「プライマリ」バージョンは [!DNL AEM] にあります。[!DNL Target] 内の[!UICONTROL コンテンツフラグメント]は編集できません。
* [!DNL Adobe I/O] を使用して[!UICONTROL コンテンツフラグメント]を作成することはできません。前述のとおり、[!UICONTROL コンテンツフラグメント]は AEM を使用して作成してください。
* AEM で[!UICONTROL コンテンツフラグメント]を更新する場合は、[!UICONTROL エクスペリエンスフラグメント]を公開して [!DNL Target] に再度書き出し、[!DNL Target] が最新の変更を使用できるようにする必要があります。
