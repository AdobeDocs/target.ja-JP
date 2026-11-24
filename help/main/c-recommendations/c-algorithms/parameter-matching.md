---
keywords: 包含ルール；包含基準；レコメンデーション；プロモーション；動的フィルタリング；動的；パラメータマッチング
description: Adobe [!DNL Target]のRecommendationsで、アイテム（エンティティ）をリクエスト（APIまたはmbox）の値と比較して動的にフィルタリングする方法について説明します。
title: パラメーターのマッチング
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: 9ec161b9-1b37-4475-b508-af676126c817
TQID: 'https://experienceleague.adobe.com/GTli-O1p4Gm2Fg9J-L0ukQ8dSw2t-da8OatFLP8Ks9g'
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
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 14%
---
# パラメーターのマッチング {#parameter-matching}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、アイテム（エンティティ）をリクエスト（APIまたはmbox）の値と比較して、[!DNL Adobe Target Recommendations]でレコメンデーションを動的にフィルタリングする方法を説明します。

>[!ENDSHADEBOX]

**[!UICONTROL パラメーターマッチング]**&#x200B;では、ページパラメーターや訪問者のパラメーター（デバイスのサイズや位置情報など）に一致するコンテンツのみを推奨します。 例えば、「industry」ページパラメーターに一致するコンテンツのみを推奨できます。 条件とプロモーションでは、インクルージョンルールを作成、使用する方法は類似しています。使用例やサンプルも同様です。 詳しくは、[動的および静的インクルージョンルールの使用](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md)を参照してください。

その他の例には、次のようなものがあります。

* 画面の幅と高さのMbox パラメーターを使用して、モバイル訪問者をターゲットにし、モバイル デバイスとアクセサリのみを推奨できます。
* レコメンデーションルールは、訪問者がページを表示するために使用するモバイルデバイスの画面の高さに一致するか、それを超えるトップセラー携帯電話のみを返すことができます。
* 地域の位置情報パラメーターを使用して、冬の間にツールの推奨事項を返すことができます。 雪が降る地域の訪問者にはスノーブロワーやその他の除雪具をお勧めしますが、雪が降らない地域の訪問者には推奨されません。

## パラメーターマッチングの例

[!DNL Recommendations]は、[!DNL Target]呼び出しで送信されたパラメーター値と一致する可能性があります。 次の例では、[!DNL Target]は、[!DNL Target]呼び出しで送信された画面の高さと幅のパラメーターに基づいて、訪問者がモバイルデバイスを使用していることを検出し、モバイルデバイスである項目のみを推奨します。

次の[!DNL Target]呼び出しの例を考えてみましょう。

![Target呼び出し](/help/main/c-recommendations/c-algorithms/assets/example-target-call-2.png)

訪問者が表示しているページには、モバイルデバイス製品が表示されます。

![ モバイルデバイス製品](/help/main/c-recommendations/c-algorithms/assets/phones.png)
