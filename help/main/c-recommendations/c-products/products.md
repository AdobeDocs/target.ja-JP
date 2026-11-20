---
keywords: 製品;コレクション
description: Adobe [!DNL Target]の推奨事項のエンティティについて説明します。 エンティティとは、記事、映画、製品など、[!DNL Target]を使用して推奨するアイテムを指します。
title: エンティティの使用方法
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: ffe23eea-b914-4c86-ad54-c63c1cc1c0d7
TQID: 'https://experienceleague.adobe.com/zfISb59XJ5qrD1-FA0syglPPswIL8cA0N0pBpY4tgIE'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 5ed511322cc9f04c349471f8ad84a17526d4925f
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 7%
---
# エンティティの基本を学ぶ {#get-started-entities}

>[!BEGINSHADEBOX]

**このページで：** [!DNL Adobe Target Recommendations]のエンティティとその管理場所について説明します。

>[!ENDSHADEBOX]

エンティティは、[!DNL Recommendations]が推奨できる項目です。 エンティティには、製品、コンテンツ（記事、スライドショー、画像、映画、TV番組など）、求人情報、レストランなどがあります。

[!DNL Recommendations]は、設定した条件に従って、コレクションのアイテムを表示します。

## エンティティがレコメンデーションにリーチする方法

エンティティに関する情報は、次のような方法で[!DNL Recommendations]に渡すことができます。

* ページから[&#x200B; エンティティ属性](/help/main/c-recommendations/c-products/entity-attributes.md)が送信され、mboxまたは`targetPageParams`を使用しています。
* CSV ファイル、[!DNL Google Product Search] フィード形式、[!DNL Adobe Analytics]製品分類を使用できる[&#x200B; フィード &#x200B;](/help/main/c-recommendations/c-products/feeds.md)を使用します。
* すべて実現できます。

[!DNL Target]がフィードとmboxの両方からアイテムのデータを収集する場合、最新のデータが使用されます。

アップロードされたエンティティとエンティティ属性値は、61日後に有効期限が切れます。 少なくとも60日ごとに1回は、各項目を再度送信してください。 それ以外の場合、[!DNL Target]はアイテムが関連性がなくなったと見なし、カタログから削除します。

## エンティティの管理

以下のページを使用して、エンティティを操作します。

* [&#x200B; エンティティ属性](/help/main/c-recommendations/c-products/entity-attributes.md)および[&#x200B; カスタムエンティティ属性](/help/main/c-recommendations/c-products/custom-entity-attributes.md): [!DNL Recommendations]に渡す製品またはコンテンツ情報を定義します。
* [&#x200B; フィード &#x200B;](/help/main/c-recommendations/c-products/feeds.md): エンティティまたはコンテンツの情報をレコメンデーションに取り込みます。
* [&#x200B; カタログ検索](/help/main/c-recommendations/c-products/catalog-search.md): カタログ内のアイテムを検索します。
* [&#x200B; コレクション &#x200B;](/help/main/c-recommendations/c-products/collections.md): コレクションを設定します。 [!DNL Recommendations] アクティビティの作成時に、各エクスペリエンスのコレクションが選択されます。
* [除外](/help/main/c-recommendations/c-products/exclusions.md)：特定の項目がレコメンデーションに表示されないようにします。 除外は、アカウント内のすべてのアクティビティに適用されます。
