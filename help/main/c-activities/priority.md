---
keywords: 設定;優先度
description: Adobe [!DNL Target] どのアクティビティをページに配信するかを、どのアクティビティに応じて異なる方法で決定します [!DNL Target] インターフェイスと、使用するアクティビティ作成機能を示します。
title: 方法 [!DNL Target] 異なるアクティビティに優先度を割り当てますか？
feature: Activities
exl-id: c32f1699-e564-40dd-8ff1-7c75a672c6ef
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1162'
ht-degree: 87%

---

# 優先度

Target は、使用する Target インターフェイスおよびアクティビティ作成機能（Visual Experience Composer またはフォームベースの Experience Composer）に応じて別々に、どのアクティビティをページに配信するかを決定します。

## Target Standard/Premium Visual Experience Composer のみ、またはグローバルを使用したフォームベースのコンポーザー [!DNL Target] リクエストのみ {#section_4A0A317DFED345649B58B0CB5B410C8B}

会社が Target Standard/Premium および Visual Experience Composer を単独で使用している場合、複数のアクティビティからのコンテンツは、同じ呼び出しに対して返すことができます。アクティビティは、次の決定フローを使用して配信されます。

1. Target サーバーの呼び出しは URL に関する情報と共に Target に伝わります。
1. Target は、その URL で実行中のすべてのアクティビティを取り込みます。
1. Target は、訪問者をアクティビティに適合させようとします。

   訪問者が既に A/B テストまたは多変量分析テストにある場合、コンバージョンがおこなわれるまで、そのテストに適合します。以前、エクスペリエンスのターゲット化アクティビティにあった場合、もう一度適合させる必要があります。オーディエンスルールを満たす場合、訪問者は、これらのアクティビティおよび特定のエクスペリエンスに分類されます。

1. 訪問者が適合するすべてのアクティビティおよびエクスペリエンスのコンテンツがページに返されます。
1. 各アクティビティのコンテンツが異なる[CSS セレクター](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337)を参照する場合、すべてのコンテンツが表示されます。

   CSS セレクターの重なりや重複がある場合、優先度の最も高いアクティビティコンテンツが表示されます。ページ上で実行されるすべてのアクティビティの結果がカウントされ、レポートに反映されます。

   >[!IMPORTANT]
   >
   >Target は、ページ上のすべてのアクティビティのコンテンツを、優先度が最も低いものから順番に返し、続いて、そのコンテンツは優先度の低いものから高いものへと、各アクティビティによって上書きされます。その結果、ほとんどの場合は、優先度が最も高いコンテンツが表示されます。ただし、優先度が低いアクティビティによってページの DOM の構造が変更されると、優先度が高いアクティビティによってページの構造が認識されないので、優先度が低いコンテンツが表示されます。ページ上で実行されるすべてのアクティビティの結果がカウントされ、レポートに反映されます。

1. 複数のアクティビティが同じ優先度を共有している場合、さらに 2 つの基準があります。

   * 1 つのアクティビティだけがオーディエンスターゲティングを持つ場合、そのアクティビティが表示されます。
   * すべてのアクティビティにターゲットが設定されている場合や、どのアクティビティにもターゲットが設定されていない場合は、最初に承認されたアクティビティが表示されます。

## Target Standard/Premium のフォームベースのコンポーザーと [!DNL Target] Standard/Premium Visual Experience Composer {#section_4620253E1CE942DD830724C7822B175F}

>[!NOTE]
>
>この情報は、[!DNL Target Classic] で作成された実行中のすべてのキャンペーンにも当てはまります。

会社が Target Standard/Premium のフォームベースのコンポーザーおよび Target Standard/Premium の Visual Experience Composer を使用している場合、複数の Visual Experience Composer アクティビティからのコンテンツを配信できますが、フォームベースのワークフローからのアクティビティの場合は 1 つのみです。アクティビティの配信は、次の決定フローを使用して決定されます。

1. Target サーバー呼び出しは、 [!DNL Target] リクエストと URL。
1. Target Classic と Standard は、その中で実行中のすべてのアクティビティを抽出します [!DNL Target] リクエスト。
1. Target は、訪問者をアクティビティに適合させようとします。

   訪問者が既に A/B テストまたは多変量分析テストにある場合、コンバージョンがおこなわれるまで、そのテストに適合します。以前、エクスペリエンスのターゲット化アクティビティにあった場合、もう一度適合させる必要があります。オーディエンスルールを満たす場合、訪問者は、これらのアクティビティおよび特定のエクスペリエンスに分類されます。

1. フォームベースのアクティビティの優先度が最も高い場合、Visual Experience Composer アクティビティからの適合するすべてのアクティビティコンテンツと共に、そのアクティビティコンテンツが返されます。
1. Visual Experience Composer のアクティビティの優先度が最も高い場合、Visual Experience Composer アクティビティからのすべての適合するコンテンツが返されますが、Target Classic またはフォームベースのアクティビティコンテンツは返されません。

   ページ上で実行されるすべてのアクティビティの結果がカウントされ、レポートに反映されます。

**例**

2 つのアクティビティがあり、片方は「Nike」のブランド名を検索キーワードのターゲットとし、もう片方はブランド名をキーワードとしないスニーカーをターゲットとしているとします。この場合、両方のアクティビティの優先度がチェックされます。Nike アクティビティの優先度が高い場合は、そのコンテンツが表示されます。スニーカーのアクティビティの優先度が高い場合は、そちらのコンテンツが表示されます。

ターゲットアクティビティの双方が同じ優先度の場合、最後に表示されたアクティビティが表示されます。このページに初めて訪問する訪問者の場合は、最後にアクティブ化されたアクティビティが表示されます。

## Target Standard/Premium のフォームベースのコンポーザーと非グローバル [!DNL Target] リクエスト {#section_C3F5F09B0B2D4EF795C5929D5C426A8C}

>[!NOTE]
>
>この情報は、Target Classic で作成された実行中のすべてのキャンペーンにも当てはまります。

会社が [!DNL Target] グローバル以外のリクエスト [!DNL Target] フォームベースのコンポーザーでのリクエストでは、呼び出しごとに 1 つのアクティビティからのコンテンツのみ返すことができます。 アクティビティの配信は、次の決定フローを使用して決定されます。

1. この [!DNL Target] サーバーコールが発生 [!DNL Target] ～に関する情報を持って [!DNL Target] リクエストと URL。
1. [!DNL Target] は、実行中のすべてのアクティビティを [!DNL Target] リクエスト。
1. [!DNL Target] は、訪問者を優先度の最も高いアクティビティに適合させようとします。

   訪問者が既に A/B テストまたは多変量分析テストにある場合、コンバージョンがおこなわれるまで、そのテストに適合します。以前、エクスペリエンスのターゲット化アクティビティにあった場合、もう一度適合させる必要があります。オーディエンスルールを満たす場合、訪問者は、これらのアクティビティおよび特定のエクスペリエンスに分類されます。

1. 複数のアクティビティが同じ優先度を共有している場合、さらに 2 つの基準があります。

   * 1 つのアクティビティだけがオーディエンスターゲティングを持つ場合、そのアクティビティが表示されます。
   * すべてのアクティビティにターゲットが設定されている場合や、どのアクティビティにもターゲットが設定されていない場合は、最初に承認されたアクティビティが表示されます。

## 例 {#section_F6A788AAC3884A2FA03E47F0557A1213}

>[!NOTE]
>
>設定に応じて、優先度の値が変わります。従来の「低」、「中」、「高」の各設定も使用できますが、0 から 999 の値を入力して詳細な優先度を設定することもできます。詳しくは、「[アクティビティの設定](/help/main/c-activities/activity-settings.md#task_C6B2FF8374724933BE79A83549B9CD02)」を参照してください。

**2 つの Target Classic キャンペーンで、グローバルでない Target リクエストを使用します**

* キャンペーン 1: homePageHero、offer1、priority high
* キャンペーン 2: homePageHero、offer2、priority low

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
>Target Classic は、セレクターの競合を処理しないので、これは前述の 2 番目の使用例と同じ応答です。Target Standard は、セレクターが DOM と視覚的の両方で競合している可能性がある場合、そうした行動および他の使用例をとらえます（通常、エクスペリエンスエディターレベルかキャンペーンシミュレーションモードでおこなわれます）。

**Visual Experience Composer で作成されたオファーを使用する 2 つのアクティビティと、2 つの Target Classic キャンペーン**

* アクティビティ 1: target-global-mbox、selector1、visualExpCompOffer1、medium high
* アクティビティ 2: target-global-mbox、selector2、visualExpCompOffer2、priority low
* キャンペーン 1: target-global-mbox、offer1、priority high
* キャンペーン 2: target-global-mbox、offer2、priority low

応答：offer1、visualExpCompOffer2、visualExpCompOffer1

>[!NOTE]
>
>組み合わされた応答の順番は、従来のコンテンツが先になり（使用例 1 のように、1 つの従来の応答のみが処理されます）、次に Visual Experience Composer が逆の優先順位で並べられた応答を提供します。

## トレーニングビデオ：アクティビティの設定（3:02）

このビデオでは、アクティビティの設定について説明します。

* アクティビティの目的の入力
* アクティビティの優先度の設定
* アクティビティの開始時刻と停止時刻の設定
* レポートフィルター作成とレポートのためのオーディエンス追加
* アクティビティのメモの入力

>[!VIDEO](https://video.tv.adobe.com/v/17381)
