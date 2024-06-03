---
keywords: 設定;優先度
description: 方法 [!DNL Adobe Target] ページに配信するアクティビティ（1 つまたは複数）を、対象によって異なる方法で決定します [!DNL Target] インターフェイスと、使用しているアクティビティ作成機能。
title: 方法 [!DNL Target] 異なるアクティビティに優先度を割り当てますか？
feature: Activities
exl-id: c32f1699-e564-40dd-8ff1-7c75a672c6ef
source-git-commit: be6e45ff301f549eb5be24a65b05c4a9c1cd6089
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 37%

---

# 優先度

[!DNL Adobe Target] ページに配信するアクティビティ（1 つまたは複数）を、対象によって異なる方法で決定します [!DNL Target] インターフェイスとアクティビティ作成関数（[[!UICONTROL Visual Experience Composer (VEC)]](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) または [フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md)）を使用しています。

## [!UICONTROL Visual Experience Composer] のみ、または [!UICONTROL Form-Based Experience Composer] グローバルの使用 [!DNL Target] リクエストのみ {#section_4A0A317DFED345649B58B0CB5B410C8B}

会社が VEC のみを使用している場合、複数のアクティビティのコンテンツを同じ呼び出しで返すことができます。 アクティビティは、次の決定フローを使用して配信されます。

1. この [!DNL Target] サーバーコールの送信先 [!DNL Target] URL に関する情報と共に使用します。
1. [!DNL Target] その URL で実行されているすべてのアクティビティを取り込みます。
1. [!DNL Target] は訪問者をアクティビティに一致させようとします。

   訪問者がに既に入っている場合 [!UICONTROL A/B Test] または [!UICONTROL Multivariate Test] アクティビティの場合、変換されるまでそのアクティビティに一致します。 以前に [!UICONTROL Experience Targeting] アクティビティは、もう一度一致する必要があります。 オーディエンスルールを満たす場合、訪問者は、これらのアクティビティおよび特定のエクスペリエンスに分類されます。

1. 訪問者が適合するすべてのアクティビティおよびエクスペリエンスのコンテンツがページに返されます。
1. 各アクティビティのコンテンツが異なる参照の場合 [CSS セレクター](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337)を選択すると、すべてのコンテンツが表示されます。

   CSS セレクターの重なりや重複がある場合、優先度の最も高いアクティビティコンテンツが表示されます。ページ上で実行されるすべてのアクティビティの結果がカウントされ、レポートに反映されます。

   >[!IMPORTANT]
   >
   >[!DNL Target] ページ上のすべてのアクティビティのコンテンツを返します。優先順位が最も低いコンテンツから始まり、各アクティビティで上書きされます。優先順位が低い順に並んでいます。 通常は、最も優先度の高いコンテンツが表示されます。 ただし、優先度の低いアクティビティによってページの DOM の構造が変更された場合は、優先度の高いアクティビティがページ構造を認識しない可能性があるので、優先度の低いコンテンツが表示されます。 ページ上で実行されるすべてのアクティビティの結果がカウントされ、レポートに反映されます。

1. 複数のアクティビティが優先度レベルを共有する場合、次の 2 つのタイマーがあります。

   * 1 つのアクティビティだけがオーディエンスターゲティングを持つ場合、そのアクティビティが表示されます。
   * ターゲティングがすべてまたは何も設定されていない場合は、最初に承認されたアクティビティが表示されます。

## [!UICONTROL Form-Based Experience Composer] および [!UICONTROL Visual Experience Composer] {#section_4620253E1CE942DD830724C7822B175F}

会社が次を使用している場合 [!UICONTROL Form-Based Experience Composer] *および* VEC、複数のコンテンツ [!UICONTROL Form-Based Experience Composer] および VEC アクティビティで配信できます。 以前は、フォームベースのワークフローから 1 つのアクティビティのみが配信できました。 を配信できるフォームベースのアクティビティの数に制限がなくなりました。

アクティビティの配信は、次の決定フローを使用して決定されます。

1. [!DNL Target] サーバーコールの送信先 [!DNL Target] に関する情報を使用 [!DNL Target] リクエストと URL。
1. [!DNL Target] その中で実行されているすべてのアクティビティを取り込む [!DNL Target] リクエスト。
1. [!DNL Target] は訪問者をアクティビティに一致させようとします。

   訪問者がに既に入っている場合 [!UICONTROL A/B Test] または [!UICONTROL Multivariate Test] アクティビティは、コンバージョンするまでそのテストに一致します。 以前に [!UICONTROL Experience Targeting] アクティビティは、もう一度一致する必要があります。 オーディエンスルールを満たす場合、訪問者は、これらのアクティビティおよび特定のエクスペリエンスに分類されます。

1. フォームベースのアクティビティが最も優先度が高い場合、そのアクティビティコンテンツは、VEC アクティビティから一致するすべてのアクティビティコンテンツと共に返されます。
1. VEC アクティビティが最も優先度が高い場合、一致するすべての VEC アクティビティのコンテンツが返されますが、フォームベースのアクティビティコンテンツは返されません。

   ページ上で実行されるすべてのアクティビティの結果がカウントされ、レポートに反映されます。

**例**

ブランド検索キーワード「Nike」をターゲットにするアクティビティと、ブランド化されていないキーワード「スニーカー」をターゲットにするアクティビティが 2 つある場合は、両方のアクティビティの優先度がチェックされます。 Nike アクティビティの優先度が高い場合は、そのコンテンツが表示されます。スニーカーのアクティビティの優先度が高い場合は、そちらのコンテンツが表示されます。

ターゲットアクティビティの双方が同じ優先度の場合、最後に表示されたアクティビティが表示されます。このページに初めて訪問する訪問者の場合は、最後にアクティブ化されたアクティビティが表示されます。

## [!UICONTROL Form-Based Experience Composer] 非大域を使用 [!DNL Target] リクエスト {#section_C3F5F09B0B2D4EF795C5929D5C426A8C}

を使用している場合 [!DNL Target] グローバル以外の要求 [!DNL Target] リクエスト フォームベースのコンポーザーでは、呼び出しごとに 1 つのアクティビティのコンテンツのみを返すことができます。 アクティビティの配信は、次の決定フローを使用して決定されます。

1. この [!DNL Target] サーバーコールの送信先 [!DNL Target] に関する情報を使用 [!DNL Target] リクエストと URL。
1. [!DNL Target] その中で実行されているすべてのアクティビティを取り込む [!DNL Target] リクエスト。
1. [!DNL Target] は訪問者を最も優先度の高いアクティビティに一致させようとします。

   訪問者がに既に入っている場合 [!UICONTROL A/B Test] または [!UICONTROL Multivariate Test] アクティビティの場合、変換されるまでそのアクティビティに一致します。 以前に [!UICONTROL Experience Targeting] アクティビティは、もう一度一致する必要があります。 オーディエンスルールを満たす場合、訪問者は、これらのアクティビティおよび特定のエクスペリエンスに分類されます。

1. 複数のアクティビティが優先度レベルを共有する場合、次の 2 つのタイマーがあります。

   * 1 つのアクティビティだけがオーディエンスターゲティングを持つ場合、そのアクティビティが表示されます。
   * ターゲティングがすべてまたは何も設定されていない場合は、最初に承認されたアクティビティが表示されます。

## 例 {#section_F6A788AAC3884A2FA03E47F0557A1213}

>[!NOTE]
>
>設定に応じて、優先度の値が変わります。の従来の設定を使用できます [!UICONTROL Low], [!UICONTROL Medium]、または [!UICONTROL High]または、0～999 の細かい優先度を有効にすることもできます。 詳しくは、を参照してください [アクティビティの設定](/help/main/c-activities/activity-settings.md#task_C6B2FF8374724933BE79A83549B9CD02).

応答：offer1

**2 つのアクティビティでは、 [!UICONTROL Visual Experience Composer] 様々なセレクター用**

* アクティビティ 1: target-global-mbox、selector1、visualExpCompOffer1、priority low
* アクティビティ 2: target-global-mbox、selector2、visualExpCompOffer2、priority high

応答：visualExpCompOffer1、visualExpCompOffer2

**2 つのアクティビティでは、 [!UICONTROL Visual Experience Composer] 同じセレクター用**

* アクティビティ 1: target-global-mbox、selector1、visualExpCompOffer1、priority low
* アクティビティ 2: target-global-mbox、selector1、visualExpCompOffer2、priority high

応答：visualExpCompOffer1、visualExpCompOffer2

## トレーニングビデオ：アクティビティの設定（3:02）

このビデオでは、アクティビティの設定について説明します。

* アクティビティの目的の入力
* アクティビティの優先度の設定
* アクティビティの開始時刻と停止時刻の設定
* レポートフィルター作成とレポートのためのオーディエンス追加
* アクティビティのメモの入力

>[!VIDEO](https://video.tv.adobe.com/v/17381)
