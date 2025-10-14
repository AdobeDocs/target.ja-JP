---
keywords: 設定;優先度
description: 使用しているイ  [!DNL Adobe Target]  ターフェイスとアクティビティ作成機能に応じて、ページに配信するアクティビティ（またはアクティ  [!DNL Target]  ティ）を異なる方法で決定する方法を説明します。
title: では  [!DNL Target]  様々なアクティビティに優先度をどのように割り当てますか？
feature: Activities
exl-id: c32f1699-e564-40dd-8ff1-7c75a672c6ef
source-git-commit: be6e45ff301f549eb5be24a65b05c4a9c1cd6089
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 39%

---

# 優先度

[!DNL Adobe Target] は、使用している [!DNL Target] インターフェイスとアクティビティ作成機能（[[!UICONTROL Visual Experience Composer (VEC)]](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) または [&#x200B; フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md)）によって、ページに配信するアクティビティ（またはアクティビティ）を決定します。

## [!UICONTROL Visual Experience Composer] のみ、またはグローバル [!UICONTROL Form-Based Experience Composer] リクエストのみを使用して [!DNL Target] {#section_4A0A317DFED345649B58B0CB5B410C8B}

会社が VEC のみを使用している場合、複数のアクティビティのコンテンツを同じ呼び出しで返すことができます。 アクティビティは、次の決定フローを使用して配信されます。

1. [!DNL Target] サーバー呼び出しは、URL に関する情報と共に [!DNL Target] に送られます。
1. [!DNL Target] は、その URL で実行されているすべてのアクティビティを取り込みます。
1. [!DNL Target] は訪問者をアクティビティに一致させようとします。

   訪問者が既に [!UICONTROL A/B Test] アクティビティまたは [!UICONTROL Multivariate Test] アクティビティに含まれている場合、その訪問者はコンバージョンするまでそのアクティビティと照合されます。 以前に [!UICONTROL Experience Targeting] アクティビティにあった場合は、もう一度一致させる必要があります。 オーディエンスルールを満たす場合、訪問者は、これらのアクティビティおよび特定のエクスペリエンスに分類されます。

1. 訪問者が適合するすべてのアクティビティおよびエクスペリエンスのコンテンツがページに返されます。
1. 各アクティビティのコンテンツが異なる [CSS セレクター &#x200B;](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337) を参照する場合は、すべてのコンテンツが表示されます。

   CSS セレクターの重なりや重複がある場合、優先度の最も高いアクティビティコンテンツが表示されます。ページ上で実行されるすべてのアクティビティの結果がカウントされ、レポートに反映されます。

   >[!IMPORTANT]
   >
   >ページ上のすべて [!DNL Target] アクティビティのコンテンツを返します。このコンテンツは最も優先度の低いコンテンツから始まり、各アクティビティで上書きされます（優先度が低い方から高い方へ）。 通常は、最も優先度の高いコンテンツが表示されます。 ただし、優先度の低いアクティビティによってページの DOM の構造が変更された場合は、優先度の高いアクティビティがページ構造を認識しない可能性があるので、優先度の低いコンテンツが表示されます。 ページ上で実行されるすべてのアクティビティの結果がカウントされ、レポートに反映されます。

1. 複数のアクティビティが優先度レベルを共有する場合、次の 2 つのタイマーがあります。

   * 1 つのアクティビティだけがオーディエンスターゲティングを持つ場合、そのアクティビティが表示されます。
   * ターゲティングがすべてまたは何も設定されていない場合は、最初に承認されたアクティビティが表示されます。

## [!UICONTROL Form-Based Experience Composer] および [!UICONTROL Visual Experience Composer] {#section_4620253E1CE942DD830724C7822B175F}

会社が [!UICONTROL Form-Based Experience Composer] *and* を VEC として使用している場合、複数の [!UICONTROL Form-Based Experience Composer] および VEC アクティビティのコンテンツが配信されます。 以前は、フォームベースのワークフローから配信できるアクティビティは 1 つのみでした。配信できるフォームベースのアクティビティ数に制限がなくなりました。

アクティビティの配信は、次の決定フローを使用して決定されます。

1. サ [!DNL Target] バーコールは、[!DNL Target] リクエストと URL に関する情報と共に [!DNL Target] に送られます。
1. [!DNL Target] は、その [!DNL Target] リクエストで実行されているすべてのアクティビティを取り込みます。
1. [!DNL Target] は訪問者をアクティビティに一致させようとします。

   訪問者が既に [!UICONTROL A/B Test] アクティビティまたは [!UICONTROL Multivariate Test] アクティビティに参加している場合、その訪問者はコンバージョンするまでテストを照合します。 以前に [!UICONTROL Experience Targeting] アクティビティにあった場合は、もう一度一致させる必要があります。 オーディエンスルールを満たす場合、訪問者は、これらのアクティビティおよび特定のエクスペリエンスに分類されます。

1. フォームベースのアクティビティが最も優先度が高い場合、そのアクティビティコンテンツは、VEC アクティビティから一致するすべてのアクティビティコンテンツと共に返されます。
1. VEC アクティビティが最も優先度が高い場合、一致するすべての VEC アクティビティのコンテンツが返されますが、フォームベースのアクティビティコンテンツは返されません。

   ページ上で実行されるすべてのアクティビティの結果がカウントされ、レポートに反映されます。

**例**

ブランド検索キーワード「Nike」をターゲットにするアクティビティと、ブランド化されていないキーワード「スニーカー」をターゲットにするアクティビティが 2 つある場合は、両方のアクティビティの優先度がチェックされます。 Nike アクティビティの優先度が高い場合は、そのコンテンツが表示されます。スニーカーのアクティビティの優先度が高い場合は、そちらのコンテンツが表示されます。

ターゲットアクティビティの双方が同じ優先度の場合、最後に表示されたアクティビティが表示されます。このページに初めて訪問する訪問者の場合は、最後にアクティブ化されたアクティビティが表示されます。

## 非グローバル [!UICONTROL Form-Based Experience Composer] リクエストの [!DNL Target] {#section_C3F5F09B0B2D4EF795C5929D5C426A8C}

会社がフォームベースのコンポーザーでグローバル [!DNL Target] リクエスト以外の [!DNL Target] リクエストを使用している場合、1 回の呼び出しで返すことができるアクティビティは 1 つだけです。 アクティビティの配信は、次の決定フローを使用して決定されます。

1. [!DNL Target] サーバーコールは、[!DNL Target] リクエストと URL に関する情報と共に [!DNL Target] に送られます。
1. [!DNL Target] は、その [!DNL Target] リクエストで実行されているすべてのアクティビティを取り込みます。
1. [!DNL Target] は訪問者を最も優先度の高いアクティビティに一致させようとします。

   訪問者が既に [!UICONTROL A/B Test] アクティビティまたは [!UICONTROL Multivariate Test] アクティビティに含まれている場合、その訪問者はコンバージョンするまでそのアクティビティと照合されます。 以前に [!UICONTROL Experience Targeting] アクティビティにあった場合は、もう一度一致させる必要があります。 オーディエンスルールを満たす場合、訪問者は、これらのアクティビティおよび特定のエクスペリエンスに分類されます。

1. 複数のアクティビティが優先度レベルを共有する場合、次の 2 つのタイマーがあります。

   * 1 つのアクティビティだけがオーディエンスターゲティングを持つ場合、そのアクティビティが表示されます。
   * ターゲティングがすべてまたは何も設定されていない場合は、最初に承認されたアクティビティが表示されます。

## 例 {#section_F6A788AAC3884A2FA03E47F0557A1213}

>[!NOTE]
>
>設定に応じて、優先度の値が変わります。従来の設定である [!UICONTROL Low]、[!UICONTROL Medium]、[!UICONTROL High] を使用するか、0～999 の細かい優先度を有効にすることができます。 詳しくは、[&#x200B; アクティビティの設定 &#x200B;](/help/main/c-activities/activity-settings.md#task_C6B2FF8374724933BE79A83549B9CD02) を参照してください。

応答：offer1

**2 つのアクティビティが、異なるセレクター用に [!UICONTROL Visual Experience Composer] で作成されたオファーのみを使用する**

* アクティビティ 1: target-global-mbox、selector1、visualExpCompOffer1、priority low
* アクティビティ 2: target-global-mbox、selector2、visualExpCompOffer2、priority high

応答：visualExpCompOffer1、visualExpCompOffer2

**2 つのアクティビティが使用するのは、同じセレクターの [!UICONTROL Visual Experience Composer] で作成されたオファーのみです**

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
