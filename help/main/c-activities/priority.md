---
keywords: 設定;優先度
description: 使用している [!DNL Target]  インターフェイスとアクティビティ作成関数に応じて、ページに配信するアクティビティ（またはアクティビティ）を [!DNL Adobe Target] によって決定する方法について説明します。
title: 異なるアクティビティに [!DNL Target] 優先度を割り当てる方法
feature: Activities
exl-id: c32f1699-e564-40dd-8ff1-7c75a672c6ef
TQID: https://experienceleague.adobe.com/KSkJ1CDkd4hgwnLQ1RKn8l8r2MDIO-6flcHcdN0c0oQ
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 927
ht-degree: 39%

---

# 優先度

[!DNL Adobe Target]は、使用している[!DNL Target] インターフェイスと、どのアクティビティ作成関数（[[!UICONTROL Visual Experience Composer (VEC)]](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md)または[ フォームベースのExperience Composer](/help/main/c-experiences/form-experience-composer.md)）に応じて、ページに配信するアクティビティ（またはアクティビティ）を決定します。

## [!UICONTROL Visual Experience Composer]のみ、またはグローバル [!DNL Target]要求のみを使用する[!UICONTROL Form-Based Experience Composer] {#section_4A0A317DFED345649B58B0CB5B410C8B}

自社でVECを独占的に使用している場合、同じ呼び出しに対して複数のアクティビティのコンテンツを返すことができます。 アクティビティは、次の決定フローを使用して配信されます。

1. [!DNL Target] サーバー呼び出しは、URLに関する情報とともに[!DNL Target]に到達します。
1. [!DNL Target]は、そのURLで実行されているすべてのアクティビティを取得します。
1. 訪問者をアクティビティに照合しようとしました。[!DNL Target]

   訪問者が既に[!UICONTROL A/B Test]または[!UICONTROL Multivariate Test] アクティビティにある場合、コンバージョンするまで、そのアクティビティと一致します。 以前に[!UICONTROL Experience Targeting] アクティビティに参加していた場合は、再度一致させる必要があります。 オーディエンスルールを満たす場合、訪問者は、これらのアクティビティおよび特定のエクスペリエンスに分類されます。

1. 訪問者が適合するすべてのアクティビティおよびエクスペリエンスのコンテンツがページに返されます。
1. 各アクティビティのコンテンツが異なる[CSS セレクター](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337)を参照している場合、すべてのコンテンツが表示されます。

   CSS セレクターの重なりや重複がある場合、優先度の最も高いアクティビティコンテンツが表示されます。 ページ上で実行されるすべてのアクティビティの結果がカウントされ、レポートに反映されます。

   >[!IMPORTANT]
   >
   >[!DNL Target]は、ページ上のすべてのアクティビティのコンテンツを返します。最初のコンテンツは優先度が最も低いコンテンツで始まり、その後、各アクティビティによって優先度が最も低いものから高いものまで上書きされます。 通常、これは最も優先度の高いコンテンツが表示されます。 ただし、優先度の低いアクティビティがページのDOMの構造を変更した場合、優先度の高いアクティビティがページ構造を認識しない可能性があるため、優先度の低いコンテンツが表示されます。 ページ上で実行されるすべてのアクティビティの結果がカウントされ、レポートに反映されます。

1. 複数のアクティビティが優先レベルを共有する場合、2つのタイブレーカーがあります。

   * 1 つのアクティビティだけがオーディエンスターゲティングを持つ場合、そのアクティビティが表示されます。
   * すべての場合またはまったくターゲティングがない場合は、最初に承認されたアクティビティが表示されます。

## [!UICONTROL Form-Based Experience Composer] および [!UICONTROL Visual Experience Composer] {#section_4620253E1CE942DD830724C7822B175F}

お客様の会社がVECを[!UICONTROL Form-Based Experience Composer] *および*&#x200B;使用している場合、複数の[!UICONTROL Form-Based Experience Composer]およびVEC アクティビティからコンテンツを配信できます。 以前は、フォームベースのワークフローから配信できるアクティビティは 1 つのみでした。 配信できるフォームベースのアクティビティ数に制限がなくなりました。

アクティビティの配信は、次の決定フローを使用して決定されます。

1. [!DNL Target]要求とURLに関する情報を含む[!DNL Target] サーバー呼び出しが[!DNL Target]に届きます。
1. [!DNL Target]は、その[!DNL Target] リクエストで実行されているすべてのアクティビティを取得します。
1. 訪問者をアクティビティに照合しようとしました。[!DNL Target]

   訪問者が既に[!UICONTROL A/B Test]または[!UICONTROL Multivariate Test] アクティビティにある場合、コンバージョンするまでテストに一致します。 以前に[!UICONTROL Experience Targeting] アクティビティに参加していた場合は、再度一致させる必要があります。 オーディエンスルールを満たす場合、訪問者は、これらのアクティビティおよび特定のエクスペリエンスに分類されます。

1. フォームベースのアクティビティが最優先事項である場合、そのアクティビティコンテンツは、VEC アクティビティのすべての一致するアクティビティコンテンツと共に返されます。
1. VEC アクティビティが最優先度の場合、一致するすべてのVEC アクティビティのコンテンツが返されますが、フォームベースのアクティビティコンテンツは返されません。

   ページ上で実行されるすべてのアクティビティの結果がカウントされ、レポートに反映されます。

**例**

ブランド検索キーワード「Nike」をターゲットとするアクティビティと、ブランド以外のキーワード「sneakers」をターゲットにするアクティビティが2つある場合、両方のアクティビティの優先順位がチェックされます。 Nike アクティビティの優先度が高い場合は、そのコンテンツが表示されます。 スニーカーのアクティビティの優先度が高い場合は、そちらのコンテンツが表示されます。

ターゲットアクティビティの双方が同じ優先度の場合、最後に表示されたアクティビティが表示されます。 このページに初めて訪問する訪問者の場合は、最後にアクティブ化されたアクティビティが表示されます。

## [!UICONTROL Form-Based Experience Composer]と非グローバル [!DNL Target]要求 {#section_C3F5F09B0B2D4EF795C5929D5C426A8C}

会社がフォームベースのコンポーザーでグローバル [!DNL Target] リクエスト以外の[!DNL Target] リクエストを使用する場合、呼び出しごとに1つのアクティビティのコンテンツのみを返すことができます。 アクティビティの配信は、次の決定フローを使用して決定されます。

1. [!DNL Target] サーバーコールが[!DNL Target]に到達し、[!DNL Target] リクエストとURLに関する情報が表示されます。
1. [!DNL Target]は、その[!DNL Target] リクエストで実行されているすべてのアクティビティを取得します。
1. [!DNL Target]は、訪問者を最も優先度の高いアクティビティに一致させます。

   訪問者が既に[!UICONTROL A/B Test]または[!UICONTROL Multivariate Test] アクティビティにある場合、コンバージョンするまで、そのアクティビティと一致します。 以前に[!UICONTROL Experience Targeting] アクティビティに参加していた場合は、再度一致させる必要があります。 オーディエンスルールを満たす場合、訪問者は、これらのアクティビティおよび特定のエクスペリエンスに分類されます。

1. 複数のアクティビティが優先レベルを共有する場合、2つのタイブレーカーがあります。

   * 1 つのアクティビティだけがオーディエンスターゲティングを持つ場合、そのアクティビティが表示されます。
   * すべての場合またはまったくターゲティングがない場合は、最初に承認されたアクティビティが表示されます。

## 例 {#section_F6A788AAC3884A2FA03E47F0557A1213}

>[!NOTE]
>
>設定に応じて、優先度の値が変わります。 [!UICONTROL Low]、[!UICONTROL Medium]または[!UICONTROL High]の従来の設定を使用するか、0 ～ 999の細かい優先度を有効にできます。 詳しくは、[ アクティビティ設定](/help/main/c-activities/activity-settings.md#task_C6B2FF8374724933BE79A83549B9CD02)を参照してください。

応答：offer1

**2つのアクティビティでは、異なるセレクター**&#x200B;に[!UICONTROL Visual Experience Composer]で作成されたオファーのみを使用します

* アクティビティ 1: target-global-mbox、selector1、visualExpCompOffer1、priority low
* アクティビティ 2: target-global-mbox、selector2、visualExpCompOffer2、priority high

応答：visualExpCompOffer1、visualExpCompOffer2

**2つのアクティビティでは、同じセレクター**&#x200B;に[!UICONTROL Visual Experience Composer]で作成されたオファーのみを使用します

* アクティビティ 1: target-global-mbox、selector1、visualExpCompOffer1、priority low
* アクティビティ 2: target-global-mbox、selector1、visualExpCompOffer2、priority high

応答：visualExpCompOffer1、visualExpCompOffer2

## トレーニングビデオ：アクティビティ設定（3:02）

このビデオでは、アクティビティの設定について説明します。

* アクティビティの目的の入力
* アクティビティの優先度の設定
* アクティビティの開始時刻と停止時刻の設定
* レポートフィルター作成とレポートのためのオーディエンス追加
* アクティビティのメモの入力

>[!VIDEO](https://video.tv.adobe.com/v/17381)
