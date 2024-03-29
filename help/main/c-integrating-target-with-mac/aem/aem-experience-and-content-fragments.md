---
keywords: AEM;Experience Manager;Adobe Experience Manager;統合;エクスペリエンスフラグメント;コンテンツフラグメント
description: ' [!DNL Adobe Target]  アクティビティで  [!DNL Adobe Experience Manager]  エクスペリエンスフラグメントおよびコンテンツフラグメントを使用する方法について説明します。'
title: ' [!DNL Adobe Experience Manager] （AEM）[!UICONTROL エクスペリエンスフラグメント]および[!UICONTROL コンテンツフラグメント]の使用方法?'
feature: Integrations
exl-id: 6f1a02da-8f59-4a8b-8e97-c20444ef53c8
source-git-commit: f39ec80d9804fff2c65fce98ca2be5400d99aad0
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 100%

---

# AEM [!UICONTROL エクスペリエンスフラグメント]および[!UICONTROL コンテンツフラグメント]の概要

[!DNL Target] アクティビティの [!DNL Adobe Experience Manager]（AEM）で作成した[!UICONTROL エクスペリエンスフラグメント]（XF）および[!UICONTROL コンテンツフラグメント]（CF）を使用して、最適化とパーソナライゼーションを支援します。

[!DNL AEM] で作成した[!UICONTROL エクスペリエンスフラグメント]および[!UICONTROL コンテンツフラグメント]を [!DNL Target] アクティビティで使用すると、[!DNL AEM] の使いやすさと機能を、[!DNL Target] の強力な人工知能（AI）および機械学習（ML） 機能と組み合わせて、エクスペリエンスを大規模にテストおよびパーソナライズできます。

[!DNL AEM] では、パーソナライゼーション戦略に生かせるよう、すべてのコンテンツとアセットが一元化されます。[!DNL AEM] では、コードを記述しなくても、デスクトップ、タブレット、モバイルデバイス向けのコンテンツを 1 か所で簡単に作成できます。デバイスごとにページを作成する必要はありません。[!DNL AEM] は、コンテンツを使用して各デバイスのエクスペリエンスを自動的に調整します。

[!DNL Target] では、行動変数、コンテキスト変数、オフライン変数を組み込んだルールベースの手法と AI 駆動の機械学習手法を組み合わせ、それを土台にしてパーソナライズされたエクスペリエンスを幅広く提供できます。

[!UICONTROL エクスペリエンスフラグメント]および[!UICONTROL コンテンツフラグメント]は、コンテンツ／エクスペリエンスの作成者と管理者を、[!DNL Target] を使用してビジネス成果を高める最適化／パーソナライゼーションの専門家と連携させる大きな一歩になります。

## 注意点

[!DNL Target] で AEM [!UICONTROL エクスペリエンスフラグメント]および[!UICONTROL コンテンツフラグメント]を使用する際は、次の点を考慮してください。
* これらの機能を使用するには、[!DNL Adobe Experience Manager]（AEM）の顧客である必要があります。各フラグメントタイプ（[エクスペリエンスフラグメント](/help/main/c-integrating-target-with-mac/aem/experience-fragments-aem.md#requirements)または[コンテンツフラグメント](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md#requirements)）の要件を満たしていることを確認します。
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
* [フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) のみを使用して、[!DNL Target] アクティビティで[!UICONTROL コンテンツフラグメント]を使用できます。

## [!UICONTROL エクスペリエンスフラグメント]および[!UICONTROL コンテンツフラグメント]の差異

[!DNL Adobe Experience Manager] [!UICONTROL エクスペリエンスフラグメント]および[!UICONTROL コンテンツフラグメント]は表面的には似ているように見えるかもしれませんが、各フラグメントタイプは様々なユースケースで重要な役割を果たします。

[!UICONTROL エクスペリエンスフラグメント]および[!UICONTROL コンテンツフラグメント]の類似点、相違点およびそれぞれを使用するタイミングと方法について詳しくは、[[!UICONTROL コンテンツフラグメント]および[!UICONTROL エクスペリエンスフラグメント]について](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/content-fragments/understand-content-fragments-and-experience-fragments.html?lang=ja){target=_blank} in the [AEM Sites videos and tutorials guide](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/overview.html?lang=ja){target=_blank}を参照してください。
