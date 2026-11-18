---
keywords: 設定;優先度
description: '[!DNL Adobe Target]が、使用している[!DNL Target] インターフェイスとアクティビティ作成関数に応じて、ページに配信するアクティビティ（またはアクティビティ）を異なる方法で決定する方法について説明します。'
title: '[!DNL Target]が別のアクティビティに優先度を割り当てる方法を教えてください。'
feature: Activities
exl-id: c32f1699-e564-40dd-8ff1-7c75a672c6ef
TQID: 'https://experienceleague.adobe.com/KSkJ1CDkd4hgwnLQ1RKn8l8r2MDIO-6flcHcdN0c0oQ'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: 6efa6b7a-8062-5c41-aef4-b4853cc306ae
    internal-label: Activities
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 8c6f23b495228ab930e6649aa2f9e6dae506cae2
workflow-type: tm+mt
source-wordcount: '1043'
ht-degree: 22%
---
# 優先度 {#priority}

>[!BEGINSHADEBOX]

**このページで：** エクスペリエンスコンポーザーと使用中の[!DNL Target] リクエストの種類に応じて、[!DNL Adobe Target]がページに配信するアクティビティを決定する方法を説明します。

>[!ENDSHADEBOX]

[!DNL Adobe Target]は、使用している[!DNL Target] インターフェイスと、どのアクティビティ作成関数（[**[!UICONTROL Visual Experience Composer （VEC） &#x200B;]**](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md)または[&#x200B; フォームベース Experience Composer](/help/main/c-experiences/form-experience-composer.md)）に応じて、ページに配信するアクティビティまたはアクティビティを決定します。 次の表は、3つのケースをまとめたもので、以下の節で詳しく説明します。

| シナリオ | を提供できる活動 | 返されたコンテンツ |
|---|---|---|
| **[!UICONTROL Visual Experience Composer]**&#x200B;のみ、またはグローバル [!DNL Target]要求のみを含む&#x200B;**[!UICONTROL フォームベースのExperience Composer]** | その他 | 一致するすべてのアクティビティのコンテンツ。 セレクターが重なる場合、優先度の高いアクティビティのコンテンツが表示されます。 |
| **[!UICONTROL フォームベースのExperience Composer]**&#x200B;および&#x200B;**[!UICONTROL Visual Experience Composer]** | その他 | フォームベースのアクティビティの優先順位が最も高い場合は、そのコンテンツと、一致するすべてのVEC アクティビティのコンテンツが優先されます。 VEC アクティビティの優先順位が最も高い場合は、一致するすべてのVEC アクティビティのコンテンツのみが優先されます。 |
| **[!UICONTROL グローバル以外の[!DNL Target]要求を含むフォームベースのExperience Composer]** | 1回あたりの通話 | 最も優先度の高いマッチングアクティビティのコンテンツ。 |

## VEC、またはグローバルリクエストを含む[!UICONTROL &#x200B; フォームベースのExperience Composer] {#section_4A0A317DFED345649B58B0CB5B410C8B}

自社でVECを独占的に使用している場合、同じ呼び出しに対して複数のアクティビティのコンテンツを返すことができます。 アクティビティは、次の決定フローを使用して配信されます。

1. [!DNL Target] サーバーコールが[!DNL Target]に達しました。 呼び出しは、要求されたページのURLに関する情報を保持します。
1. [!DNL Target]は、そのURLで実行されているすべてのアクティビティを取得します。 これらのアクティビティは、配信の候補です。
1. [!DNL Target]は、訪問者を候補アクティビティに一致させようとします。

   {{visitor-matching}}

1. 訪問者が一致するすべてのアクティビティとエクスペリエンスのコンテンツがページに返されるので、同じ呼び出しに対して複数のアクティビティのコンテンツを配信できます。
1. [!DNL Target]は、各アクティビティのコンテンツが参照する[CSS セレクター](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337)を比較します。 アクティビティが異なるセレクターを参照する場合、すべてのコンテンツが表示されます。
1. セレクターが重複している場合、または重複している場合は、最も優先度の高いアクティビティのコンテンツが表示されます。

   >[!IMPORTANT]
   >
   >[!DNL Target]は、ページ上のすべてのアクティビティのコンテンツを返します。最初のコンテンツは優先度が最も低いコンテンツで始まり、その後、各アクティビティによって優先度が最も低いものから高いものまで上書きされます。 通常、これは最も優先度の高いコンテンツが表示されます。 ただし、優先度の低いアクティビティがページのDOMの構造を変更した場合、優先度の高いアクティビティはページ構造を認識しない可能性があるため、優先度の低いコンテンツが表示されます。

1. 複数のアクティビティが優先度レベルを共有する場合は、タイブレークが適用されます。 いずれかのアクティビティにオーディエンスターゲティングがある場合は、そのアクティビティが表示されます。 すべてのアクティビティにターゲティングが設定されている場合、最初に承認されたアクティビティが表示されます。
1. ページ上で実行されるすべてのアクティビティの結果がカウントされ、レポートに反映されます。

## [!UICONTROL &#x200B; フォームベースのExperience Composer]およびVEC {#section_4620253E1CE942DD830724C7822B175F}

お客様の会社が[!UICONTROL Form-Based Experience Composer] *および* VECを使用している場合は、複数の[!UICONTROL Form-Based Experience Composer]およびVEC アクティビティのコンテンツを配信できます。 以前は、フォームベースのワークフローから配信できるアクティビティは 1 つのみでした。 配信できるフォームベースのアクティビティ数に制限がなくなりました。

アクティビティの配信は、次の決定フローを使用して決定されます。

1. [!DNL Target] サーバーコールが[!DNL Target]に達しました。 呼び出しには、[!DNL Target] リクエストとURLに関する情報が含まれます。
1. [!DNL Target]は、その[!DNL Target] リクエストで実行されているすべてのアクティビティを取得します。 これらのアクティビティは、配信の候補です。
1. [!DNL Target]は、訪問者を候補アクティビティに一致させようとします。

   {{visitor-matching}}

1. [!DNL Target]は、一致するアクティビティのうち、最も優先度が高いものを確認し、そのアクティビティが[!UICONTROL &#x200B; フォームベースのExperience Composer]またはVECで作成されたかどうかを確認します。
1. フォームベースのアクティビティの優先順位が最も高い場合、そのコンテンツは、一致するすべてのVEC アクティビティのコンテンツとともに返されます。
1. VEC アクティビティの優先度が最も高い場合、一致するすべてのVEC アクティビティのコンテンツが返されますが、フォームベースのアクティビティコンテンツは返されません。
1. ページ上で実行されるすべてのアクティビティの結果がカウントされ、レポートに反映されます。

**例**

2つのアクティビティが存在します。1つはブランド検索キーワード「Nike」をターゲットとし、もう1つはブランド以外のキーワード「sneakers」をターゲットにします。 両方の活動の優先順位がチェックされます。 Nike アクティビティの優先度が高い場合、そのコンテンツが表示されます。 スニーカーのアクティビティの優先度が高い場合は、そちらのコンテンツが表示されます。

ターゲットアクティビティの双方が同じ優先度の場合、最後に表示されたアクティビティが表示されます。 このページに初めて訪問する訪問者の場合は、最後にアクティブ化されたアクティビティが表示されます。

## [!UICONTROL &#x200B; グローバル以外のリクエストを含むフォームベースのExperience Composer] {#section_C3F5F09B0B2D4EF795C5929D5C426A8C}

会社がフォームベースのコンポーザーでグローバル [!DNL Target] リクエスト以外の[!DNL Target] リクエストを使用する場合、呼び出しごとに1つのアクティビティのコンテンツのみを返すことができます。 アクティビティの配信は、次の決定フローを使用して決定されます。

1. [!DNL Target] サーバーコールが[!DNL Target]に達しました。 呼び出しには、[!DNL Target] リクエストとURLに関する情報が含まれます。
1. [!DNL Target]は、その[!DNL Target] リクエストで実行されているすべてのアクティビティを取得します。 これらのアクティビティは、配信の候補です。
1. [!DNL Target]は、訪問者を最も優先度の高い候補アクティビティに一致させようとします。

   {{visitor-matching}}

1. 複数のアクティビティが優先度レベルを共有する場合は、タイブレークが適用されます。 いずれかのアクティビティにオーディエンスターゲティングがある場合は、そのアクティビティが表示されます。 すべてのアクティビティにターゲティングが設定されている場合、最初に承認されたアクティビティが表示されます。
1. その単一アクティビティのコンテンツがページに戻されます。

## 例 {#section_F6A788AAC3884A2FA03E47F0557A1213}

>[!NOTE]
>
>設定に応じて、優先度の値が変わります。 **[!UICONTROL Low]**、**[!UICONTROL Medium]**&#x200B;または&#x200B;**[!UICONTROL High]**&#x200B;の従来の設定を使用するか、0 ～ 999の細かい優先度を有効にできます。 詳しくは、[&#x200B; アクティビティ設定](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#section_DCBDC354261F420EBD4B43EA34947BAC)を参照してください。

**2つのアクティビティでは、異なるセレクター**&#x200B;に対して[!UICONTROL Visual Experience Composer]で作成されたオファーのみを使用します

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

>[!VIDEO](https://video.tv.adobe.com/v/3507944?captions=jpn)
