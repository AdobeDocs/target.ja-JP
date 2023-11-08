---
keywords: 設定;優先度
description: 方法を学ぶ [!DNL Adobe Target] どのアクティビティをページに配信するかを、どのアクティビティに応じて異なる方法で決定します [!DNL Target] インターフェイスと、使用するアクティビティ作成機能を示します。
title: 方法 [!DNL Target] 異なるアクティビティに優先度を割り当てますか？
feature: Activities
exl-id: c32f1699-e564-40dd-8ff1-7c75a672c6ef
source-git-commit: 18765a82b5dca94654a412e2012a3f6c1a7b5128
workflow-type: tm+mt
source-wordcount: '1105'
ht-degree: 40%

---

# 優先度

[!DNL Adobe Target] どのアクティビティをページに配信するかを、どのアクティビティに応じて異なる方法で決定します [!DNL Target] インターフェイスとどのアクティビティ作成機能 ([[!UICONTROL Visual Experience Composer]](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) または [フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md)) を使用している。

## [!DNL Target Standard/Premium] [!UICONTROL Visual Experience Composer] のみ、または [!UICONTROL フォームベースの Experience Composer] グローバルの使用 [!DNL Target] リクエストのみ {#section_4A0A317DFED345649B58B0CB5B410C8B}

会社が [!DNL Target Standard/Premium] そして [!UICONTROL Visual Experience Composer] 排他的に、複数のアクティビティのコンテンツを、同じ呼び出しに対して返すことができます。 アクティビティは、次の決定フローを使用して配信されます。

1. The [!DNL Target] サーバーコールが発生する [!DNL Target] を参照してください。
1. [!DNL Target] は、その URL で実行中のすべてのアクティビティを取り込みます。
1. [!DNL Target] は、訪問者をアクティビティに適合させようとします。

   訪問者が既に [!UICONTROL A/B テスト] または [!UICONTROL 多変量分析テスト] アクティビティに適合し、コンバージョンがおこなわれるまで、そのアクティビティに適合します。 以前、 [!UICONTROL エクスペリエンスのターゲット設定] アクティビティの場合は、もう一度そのアクティビティに一致させる必要があります。 オーディエンスルールを満たす場合、訪問者は、これらのアクティビティおよび特定のエクスペリエンスに分類されます。

1. 訪問者が適合するすべてのアクティビティおよびエクスペリエンスのコンテンツがページに返されます。
1. 各アクティビティのコンテンツが異なる[CSS セレクター](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337)を参照する場合、すべてのコンテンツが表示されます。

   CSS セレクターの重なりや重複がある場合、優先度の最も高いアクティビティコンテンツが表示されます。ページ上で実行されるすべてのアクティビティの結果がカウントされ、レポートに反映されます。

   >[!IMPORTANT]
   >
   >[!DNL Target] は、ページ上のすべてのアクティビティのコンテンツを、優先度が最も低いものから順番に返し、続いて、そのコンテンツは優先度の低いものから高いものへと、各アクティビティによって上書きされます。通常、これにより、最も優先度の高いコンテンツが表示されます。 ただし、優先度が低いアクティビティによってページの DOM の構造が変更された場合は、優先度が高いアクティビティによってページの構造が認識されない可能性があるので、優先度が低いコンテンツが表示されます。 ページ上で実行されるすべてのアクティビティの結果がカウントされ、レポートに反映されます。

1. 複数のアクティビティが優先度レベルを共有する場合、2 つの基準があります。

   * 1 つのアクティビティだけがオーディエンスターゲティングを持つ場合、そのアクティビティが表示されます。
   * すべてのもの、または何もターゲティングがない場合は、最初に承認されたアクティビティが表示されます。

## [!DNL Target Standard/Premium] [!UICONTROL フォームベースの Experience Composer] および [!DNL Target Standard/Premium] [!UICONTROL Visual Experience Composer] {#section_4620253E1CE942DD830724C7822B175F}

>[!NOTE]
>
>この情報は、[!DNL Target Classic] で作成された実行中のすべてのキャンペーンにも当てはまります。

会社が [!UICONTROL フォームベースの Experience Composer] in [!DNL Target Standard/Premium] そして [!DNL Target Standard/Premium] [!UICONTROL Visual Experience Composer]、次に複数の [!UICONTROL Visual Experience Composer] アクティビティは配信できますが、フォームベースのワークフローのアクティビティは 1 つだけです。 アクティビティの配信は、次の決定フローを使用して決定されます。

1. [!DNL Target] サーバーコールが発生する [!DNL Target] ～に関する情報を持って [!DNL Target] リクエストと URL。
1. [!DNL Target Classic] および [!DNL Target Standard/Premium] それを実行しているすべてのアクティビティを取り込む [!DNL Target] リクエスト。
1. [!DNL Target] は、訪問者をアクティビティに適合させようとします。

   訪問者が既に [!UICONTROL A/B テスト] または [!UICONTROL 多変量分析テスト] アクティビティの場合は、コンバージョンがおこなわれるまで、テストに適合します。 以前、 [!UICONTROL エクスペリエンスのターゲット設定] アクティビティの場合は、もう一度そのアクティビティに一致させる必要があります。 オーディエンスルールを満たす場合、訪問者は、これらのアクティビティおよび特定のエクスペリエンスに分類されます。

1. フォームベースのアクティビティの優先度が最も高い場合は、そのアクティビティのコンテンツと、 [!UICONTROL Visual Experience Composer] アクティビティ。
1. 次の場合、 [!UICONTROL Visual Experience Composer] アクティビティの優先順位が最も高い場合は、一致するすべての [!UICONTROL Visual Experience Composer] アクティビティは返されますが、 [!DNL Target Classic] またはフォームベースのアクティビティコンテンツが返されます。

   ページ上で実行されるすべてのアクティビティの結果がカウントされ、レポートに反映されます。

**例**

2 つのアクティビティがあり、一方がブランデッド検索キーワード「Nike」をターゲティングし、もう一方がブランド以外のキーワード「sneakers」をターゲティングしている場合、両方のアクティビティの優先度がチェックされます。 Nike アクティビティの優先度が高い場合は、そのコンテンツが表示されます。スニーカーのアクティビティの優先度が高い場合は、そちらのコンテンツが表示されます。

ターゲットアクティビティの双方が同じ優先度の場合、最後に表示されたアクティビティが表示されます。このページに初めて訪問する訪問者の場合は、最後にアクティブ化されたアクティビティが表示されます。

## [!DNL Target Standard/Premium] [!UICONTROL フォームベースの Experience Composer] 非グローバル [!DNL Target] リクエスト {#section_C3F5F09B0B2D4EF795C5929D5C426A8C}

>[!NOTE]
>
>この情報は、 [!DNL Target Classic].

会社が [!DNL Target] グローバル以外のリクエスト [!DNL Target] フォームベースのコンポーザーでのリクエストでは、呼び出しごとに 1 つのアクティビティからのコンテンツのみ返すことができます。 アクティビティの配信は、次の決定フローを使用して決定されます。

1. The [!DNL Target] サーバーコールが発生する [!DNL Target] ～に関する情報を持って [!DNL Target] リクエストと URL。
1. [!DNL Target] は、実行中のすべてのアクティビティを [!DNL Target] リクエスト。
1. [!DNL Target] は、訪問者を最も優先度の高いアクティビティに適合させようとします。

   訪問者が既に [!UICONTROL A/B テスト] または [!UICONTROL 多変量分析テスト] アクティビティに適合し、コンバージョンがおこなわれるまで、そのアクティビティに適合します。 以前、 [!UICONTROL エクスペリエンスのターゲット設定] アクティビティの場合は、もう一度そのアクティビティに一致させる必要があります。 オーディエンスルールを満たす場合、訪問者は、これらのアクティビティおよび特定のエクスペリエンスに分類されます。

1. 複数のアクティビティが優先度レベルを共有する場合、2 つの基準があります。

   * 1 つのアクティビティだけがオーディエンスターゲティングを持つ場合、そのアクティビティが表示されます。
   * すべてのもの、または何もターゲティングがない場合は、最初に承認されたアクティビティが表示されます。

## 例 {#section_F6A788AAC3884A2FA03E47F0557A1213}

>[!NOTE]
>
>設定に応じて、優先度の値が変わります。従来の設定の [!UICONTROL 低], [!UICONTROL 中]または [!UICONTROL 高]または、0 ～ 999 の詳細な優先度を有効にすることもできます。 詳しくは、 [アクティビティの設定](/help/main/c-activities/activity-settings.md#task_C6B2FF8374724933BE79A83549B9CD02).

**2 [!DNL Target Classic] アクティビティは非グローバルを使用 [!DNL Target] リクエスト**

* アクティビティ 1: homePageHero、offer1、priority high
* アクティビティ 2: homePageHero, offer2, priority low

応答：offer1

**2 つのアクティビティで、異なるセレクター用に Visual Experience Composer で作成されたオファーのみを使用する**

* アクティビティ 1: target-global-mbox、selector1、visualExpCompOffer1、priority low
* アクティビティ 2: target-global-mbox、selector2、visualExpCompOffer2、priority high

応答：visualExpCompOffer1、visualExpCompOffer2

**2 つのアクティビティで、同じセレクター用に Visual Experience Composer で作成されたオファーのみを使用する**

* アクティビティ 1: target-global-mbox、selector1、visualExpCompOffer1、priority low
* アクティビティ 2: target-global-mbox、selector1、visualExpCompOffer2、priority high

応答：visualExpCompOffer1、visualExpCompOffer2

>[!NOTE]
>
>これは、上記の 2 番目の使用例と同じ応答です。 [!DNL Target Classic] セレクターの競合を処理しませんでした。 [!DNL Target Standard/Premium] は、セレクターが DOM と視覚的の両方で競合する場合（通常、エクスペリエンスエディターレベルまたはアクティビティシミュレーションモードでおこなわれる）に、このような動作やその他の使用例をキャッチします。

**2 つのアクティビティで、 [!UICONTROL Visual Experience Composer] と 2 [!DNL Target Classic] アクティビティ**

* アクティビティ 1: target-global-mbox、selector1、visualExpCompOffer1、medium high
* アクティビティ 2: target-global-mbox、selector2、visualExpCompOffer2、priority low
* アクティビティ 1: target-global-mbox、offer1、priority high
* アクティビティ 2: target-global-mbox、offer2、priority low

応答：offer1、visualExpCompOffer2、visualExpCompOffer1

>[!NOTE]
>
>組み合わされた回答の順序は次のとおりです。 [!DNL Target Classic] コンテンツが先になります。 1 つだけ [!DNL Target Classic] 応答は、使用例 1 のように処理され、次に [!UICONTROL Visual Experience Composer] 逆の優先度で並べられた応答をオファーします。

## トレーニングビデオ：アクティビティの設定（3:02）

このビデオでは、アクティビティの設定について説明します。

* アクティビティの目的の入力
* アクティビティの優先度の設定
* アクティビティの開始時刻と停止時刻の設定
* レポートフィルター作成とレポートのためのオーディエンス追加
* アクティビティのメモの入力

>[!VIDEO](https://video.tv.adobe.com/v/17381)
