---
keywords: 包含ルール；包含基準；レコメンデーション；プロモーション；動的フィルタリング；動的；パラメータマッチング
description: Adobe [!DNL Target]のRecommendationsで、アイテム（エンティティ）をリクエスト（APIまたはmbox）の値と比較して動的にフィルタリングする方法について説明します。
title: Recommendations アクティビティでパラメーターの一致をフィルタリングするにはどうすればよいですか？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: 9ec161b9-1b37-4475-b508-af676126c817
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
source-git-commit: ed3d4b67c78791454c55a2cad4908a37a4d60e26
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 15%
---
# パラメーターのマッチング

アイテム（エンティティ）をリクエスト（APIまたはmbox）の値と比較して、動的にフィルタリングします。

例えば、次の例のように、「業界」ページパラメーターや、デバイスのサイズや位置情報などの他のパラメーターと一致するコンテンツのみをレコメンドします。

* 画面の幅と高さのMbox パラメーターを使用して、モバイル訪問者をターゲットにし、モバイル デバイスとアクセサリのみを推奨できます。
* 訪問者がページの表示を使用しているモバイルデバイスの画面の高さに一致するか、それを超えるトップセラーの携帯電話のみを返すレコメンデーションルールを作成します。
* 地域の位置情報パラメーターを使用して、冬の間にツールの推奨事項を返すことができます。 雪が降る地域の訪問者にはスノーブロワーやその他の除雪具をお勧めしますが、雪が降らない地域の訪問者にはお勧めしません。

>[!NOTE]
>
>アクティビティが2016年10月31日より前に作成された場合、「パラメーター一致」フィルターを使用すると、その配信は失敗します。 この問題を回避する方法は次のとおりです。
>
>* 新しいアクティビティを作成し、条件を追加します。
>* 「パラメーターのマッチング」フィルターを含まない条件を使用します。
>* 条件から「パラメーターのマッチング」フィルターを削除します。

## パラメーターの一致の例

[!UICONTROL  パラメーターマッチング ]を使用すると、次の例のように、ページパラメーターや訪問者のパラメーター（デバイスのサイズや位置情報など）に一致するコンテンツをレコメンドできます。

[!DNL Recommendations]は、[!DNL Target]呼び出しで送信されたパラメーター値と一致する可能性があります。 この場合、[!DNL Target]は、[!DNL Target]呼び出しで送信された画面の高さと幅のパラメーターに基づいて、訪問者がモバイルデバイスを使用していることを検出し、モバイルデバイスである項目のみを推奨します。

次のTarget呼び出しの例を考えてみましょう。

![Target呼び出し](/help/main/c-recommendations/c-algorithms/assets/example-target-call-2.png)

訪問者が閲覧しているページに、モバイルデバイス商品が表示されます。

![ モバイルデバイス製品](/help/main/c-recommendations/c-algorithms/assets/phones.png)
