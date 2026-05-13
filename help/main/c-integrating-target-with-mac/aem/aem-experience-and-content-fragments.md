---
keywords: AEM;Experience Manager;Adobe Experience Manager;統合;エクスペリエンスフラグメント;コンテンツフラグメント
description: ' [!DNL Adobe Target]  アクティビティで  [!DNL Adobe Experience Manager]  エクスペリエンスフラグメントおよびコンテンツフラグメントを使用する方法について説明します。'
title: ' [!DNL Adobe Experience Manager]  （AEM） [!UICONTROL Experience Fragments]と[!UICONTROL Content Fragments]の使用方法を教えてください。'
feature: Integrations
exl-id: 6f1a02da-8f59-4a8b-8e97-c20444ef53c8
TQID: https://experienceleague.adobe.com/OlgveSjoE0rh1orFsbEZVCSbjd3TKEk8fdBbbXtLxhA
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: f7c7de77-382f-4f48-8b36-61a170f06d3d
topic_v2: id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: e0eb8757-182f-49f3-94a4-1587d16f5094id: e6ff21d3-dec6-4298-8590-7c749fffaf78id: eb30f47f-d87a-400f-8f78-63ce7979ff56
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 341
ht-degree: 43%

---

# AEM [!UICONTROL Experience Fragments]と[!UICONTROL Content Fragments]の概要

[!DNL Target] アクティビティの[!DNL Adobe Experience Manager] （AEM）で作成された[!UICONTROL Experience Fragments] （XF）と[!UICONTROL Content Fragments] （CF）を使用して、最適化とパーソナライゼーションを支援します。

[!DNL Target]のアクティビティで[!DNL AEM]で作成された[!UICONTROL Experience Fragments]と[!UICONTROL Content Fragments]を使用すると、[!DNL AEM]の使いやすさとパワーを、[!DNL Target]の強力な人工知能（AI）および機械学習（ML）機能と組み合わせて、エクスペリエンスを大規模にテストおよびパーソナライズできます。

[!DNL AEM] では、パーソナライゼーション戦略に生かせるよう、すべてのコンテンツとアセットが一元化されます。 [!DNL AEM] では、コードを記述しなくても、デスクトップ、タブレット、モバイルデバイス向けのコンテンツを 1 か所で簡単に作成できます。 デバイスごとにページを作成する必要はありません。 [!DNL AEM] は、コンテンツを使用して各デバイスのエクスペリエンスを自動的に調整します。

[!DNL Target] では、行動変数、コンテキスト変数、オフライン変数を組み込んだルールベースの手法と AI 駆動の機械学習手法を組み合わせ、それを土台にしてパーソナライズされたエクスペリエンスを幅広く提供できます。

[!UICONTROL Experience Fragments]と[!UICONTROL Content Fragments]は、[!DNL Target]を使用してビジネス成果を促進している最適化とパーソナライゼーションの専門家に、コンテンツ/エクスペリエンスの作成者とマネージャーをリンクさせるための大きな前進です。

## 注意点

[!DNL Target]でAEM [!UICONTROL Experience Fragments]および[!UICONTROL Content Fragments]を使用する場合は、次の点を考慮してください。
* これらの機能を使用するには、[!DNL Adobe Experience Manager]（AEM）の顧客である必要があります。 各フラグメントタイプ（[エクスペリエンスフラグメント](/help/main/c-integrating-target-with-mac/aem/experience-fragments-aem.md#requirements)または[コンテンツフラグメント](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md#requirements)）の要件を満たしていることを確認します。
* [!UICONTROL Experience Fragments]と[!UICONTROL Content Fragments]は、次のアクティビティタイプで使用できます。

   * [[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Automated Personalization] （AP）](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL Experience Targeting] （XT）](/help/main/c-activities/t-experience-target/experience-target.md)

* [!UICONTROL Experience Fragments]と[!UICONTROL Content Fragments]は、次のアクティビティの種類では利用できません：

   * [[!UICONTROL Multivariate Test] （MVT）](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)

* [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) （VEC）と[ フォームベースのExperience Composer](/help/main/c-experiences/form-experience-composer.md)を使用して、[!DNL Target]のアクティビティで[!UICONTROL Experience Fragments]を利用できます。
* [ フォームベースのExperience Composer](/help/main/c-experiences/form-experience-composer.md)のみを使用して、[!DNL Target]のアクティビティで[!UICONTROL Content Fragments]を使用できます。

## [!UICONTROL Experience Fragments]と[!UICONTROL Content Fragments]の違いとは？

[!DNL Adobe Experience Manager] [!UICONTROL Experience Fragments]と[!UICONTROL Content Fragments]は表面的には似ているように見えるかもしれませんが、各フラグメントタイプは異なるユースケースで重要な役割を果たします。

[!UICONTROL Experience Fragments]と[!UICONTROL Content Fragments]が似ている方法、異なる方法、およびそれぞれの使用方法について詳しくは、[AEM Sites ビデオとチュートリアル ガイド ](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/overview.html?lang=ja){target=_blank}の[理解[!UICONTROL Content Fragments]と[!UICONTROL Experience Fragments]](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/content-fragments/understand-content-fragments-and-experience-fragments.html?lang=ja){target=_blank}を参照してください。
