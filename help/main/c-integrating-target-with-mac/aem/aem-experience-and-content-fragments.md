---
keywords: AEM;Experience Manager;Adobe Experience Manager;統合;エクスペリエンスフラグメント;コンテンツフラグメント
description: ' [!DNL Adobe Target]  アクティビティで  [!DNL Adobe Experience Manager]  エクスペリエンスフラグメントおよびコンテンツフラグメントを使用する方法について説明します。'
title: ' [!DNL Adobe Experience Manager] （AEM）[!UICONTROL エクスペリエンスフラグメント]および[!UICONTROL コンテンツフラグメント]の使用方法?'
feature: Integrations
source-git-commit: 0135831b56c48b0adca49e843c5ddd6574358aa4
workflow-type: ht
source-wordcount: '396'
ht-degree: 100%

---

# AEM [!UICONTROL エクスペリエンスフラグメント]および[!UICONTROL コンテンツフラグメント]の概要

[!DNL Target] アクティビティの [!DNL Adobe Experience Manager]（AEM）で作成した[!UICONTROL エクスペリエンスフラグメント]（XF）および[!UICONTROL コンテンツフラグメント]（CF）を使用して、最適化またはパーソナライゼーションを支援します。

>[!NOTE]
>
>[!DNL Target] で AEM [!UICONTROL エクスペリエンスフラグメント]および[!UICONTROL コンテンツフラグメント]を使用する際は、次の点を考慮してください。
> 
>* これらの機能を使用するには、[!DNL Adobe Experience Manager]（AEM）の顧客である必要があります。各フラグメントタイプ（[エクスペリエンスフラグメント](/help/main/c-integrating-target-with-mac/aem/experience-fragments-aem.md#requirements)または[コンテンツフラグメント](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md#requirements)）の要件を満たしていることを確認します。
>
>* これらの機能は、[!UICONTROL A/B テスト]、[!UICONTROL 自動配分]、[!UICONTROL 自動ターゲット]、[!UICONTROL Automated Personalization]（AP）および[!UICONTROL エクスペリエンスのターゲット設定]（XT）のアクティビティタイプで使用できます。この機能は、[!UICONTROL 多変量分析テスト]（MVT）および [!UICONTROL Recommendations] アクティビティでは使用できません。
>* [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md)（VEC）または[フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) を使用して、[!DNL Target] アクティビティ内で[!UICONTROL エクスペリエンスフラグメント]を使用できます。
>
>* [フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) でのみ[!UICONTROL コンテンツフラグメント]を使用できます。


[!DNL AEM] で作成した[!UICONTROL エクスペリエンスフラグメント]および[!UICONTROL コンテンツフラグメント]を [!DNL Target] アクティビティで使用すると、[!DNL AEM] の使いやすさと機能を、[!DNL Target] の強力な人工知能（AI）および機械学習（ML） 機能と組み合わせて、エクスペリエンスを大規模にテストおよびパーソナライズできます。

[!DNL AEM] では、パーソナライゼーション戦略に生かせるよう、すべてのコンテンツとアセットが一元化されます。[!DNL AEM] では、コードを記述しなくても、デスクトップ、タブレット、モバイルデバイス向けのコンテンツを 1 か所で簡単に作成できます。デバイスごとにページを作成する必要はありません。[!DNL AEM] は、コンテンツを使用して各デバイスのエクスペリエンスを自動的に調整します。

[!DNL Target] では、行動変数、コンテキスト変数、オフライン変数を組み込んだルールベースの手法と AI 駆動の機械学習手法を組み合わせ、それを土台にしてパーソナライズされたエクスペリエンスを幅広く提供できます。[!DNL Target] では、[A/B テスト](/help/main/c-activities/t-test-ab/test-ab.md)および[多変量分析](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)（MVT）アクティビティを簡単に設定および実行して、最適なオファー、コンテンツおよびエクスペリエンスを決定できます。

[!UICONTROL エクスペリエンスフラグメント]および[!UICONTROL コンテンツフラグメント]は、コンテンツ／エクスペリエンスの作成者と管理者を、[!DNL Target] を使用してビジネス成果を高める最適化／パーソナライゼーションの専門家と連携させる大きな一歩になります。

## [!UICONTROL エクスペリエンスフラグメント]および[!UICONTROL コンテンツフラグメント]の差異

[!DNL Adobe Experience Manager] [!UICONTROL エクスペリエンスフラグメント]および[!UICONTROL コンテンツフラグメント]は表面的には似ているように見えるかもしれませんが、各フラグメントタイプは様々なユースケースで重要な役割を果たします。

[!UICONTROL コンテンツフラグメント]および[!UICONTROL エクスペリエンスフラグメント]の類似点、相違点およびそれぞれを使用するタイミングと方法について詳しくは、[[!UICONTROL コンテンツフラグメント]および[!UICONTROL エクスペリエンスフラグメント]について](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/content-fragments/understand-content-fragments-and-experience-fragments.html?lang=ja){target=_blank} in the [AEM Sites videos and tutorials guide](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/overview.html?lang=ja){target=_blank}を参照してください。