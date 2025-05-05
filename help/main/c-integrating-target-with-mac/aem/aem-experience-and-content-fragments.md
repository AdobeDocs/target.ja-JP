---
keywords: AEM;Experience Manager;Adobe Experience Manager;統合;エクスペリエンスフラグメント;コンテンツフラグメント
description: ' [!DNL Adobe Target]  アクティビティで  [!DNL Adobe Experience Manager]  エクスペリエンスフラグメントおよびコンテンツフラグメントを使用する方法について説明します。'
title: ' [!DNL Adobe Experience Manager]  （AEM） [!UICONTROL Experience Fragments] および [!UICONTROL Content Fragments] の使用方法？'
feature: Integrations
exl-id: 6f1a02da-8f59-4a8b-8e97-c20444ef53c8
source-git-commit: f39ec80d9804fff2c65fce98ca2be5400d99aad0
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 40%

---

# AEM [!UICONTROL Experience Fragments] と [!UICONTROL Content Fragments] の概要

[!DNL Adobe Experience Manager] （AEM）で作成した [!UICONTROL Experience Fragments] （XF）および [!UICONTROL Content Fragments] （CF）を [!DNL Target] アクティビティで使用して、最適化とパーソナライゼーションを支援します。

[!DNL AEM] で作成した [!UICONTROL Experience Fragments] と [!UICONTROL Content Fragments] を [!DNL Target] アクティビティで使用すると、[!DNL AEM] の使いやすさと機能を、強力な人工知能（AI）および機械学習（ML）機能と組み合わせて、エクスペリエンスを大規模にテストおよびパーソナライズで [!DNL Target] ます。

[!DNL AEM] では、パーソナライゼーション戦略に生かせるよう、すべてのコンテンツとアセットが一元化されます。[!DNL AEM] では、コードを記述しなくても、デスクトップ、タブレット、モバイルデバイス向けのコンテンツを 1 か所で簡単に作成できます。デバイスごとにページを作成する必要はありません。[!DNL AEM] は、コンテンツを使用して各デバイスのエクスペリエンスを自動的に調整します。

[!DNL Target] では、行動変数、コンテキスト変数、オフライン変数を組み込んだルールベースの手法と AI 駆動の機械学習手法を組み合わせ、それを土台にしてパーソナライズされたエクスペリエンスを幅広く提供できます。

[!UICONTROL Experience Fragments] と [!UICONTROL Content Fragments] は、コンテンツ/エクスペリエンスの作成者と管理者を、[!DNL Target] を使用してビジネス成果を高める最適化/パーソナライゼーションの専門家と連携させる大きな一歩になります。

## 注意点

[!DNL Target] でAEM [!UICONTROL Experience Fragments] と [!UICONTROL Content Fragments] を使用する際は、次の点を考慮してください。
* これらの機能を使用するには、[!DNL Adobe Experience Manager]（AEM）の顧客である必要があります。各フラグメントタイプ（[エクスペリエンスフラグメント](/help/main/c-integrating-target-with-mac/aem/experience-fragments-aem.md#requirements)または[コンテンツフラグメント](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md#requirements)）の要件を満たしていることを確認します。
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
* [ フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) のみを使用して、[!DNL Target] アクティビティで [!UICONTROL Content Fragments] を使用できます。

## [!UICONTROL Experience Fragments] と [!UICONTROL Content Fragments] の違いは何ですか。

[!DNL Adobe Experience Manager] [!UICONTROL Experience Fragments] と [!UICONTROL Content Fragments] は表面的には似ているように見えるかもしれませんが、各フラグメントタイプは様々なユースケースで重要な役割を果たします。

[!UICONTROL Experience Fragments] と [!UICONTROL Content Fragments] の類似点、相違点およびそれぞれを使用するタイミングと方法について詳しくは、[&#128279;](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/overview.html?lang=ja) [AEM Sites ビデオおよびチュートリアルガイドの [!UICONTROL Content Fragments] と [!UICONTROL Experience Fragments]](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/content-fragments/understand-content-fragments-and-experience-fragments.html?lang=ja){target=_blank} について {target=_blank} を参照してください。
