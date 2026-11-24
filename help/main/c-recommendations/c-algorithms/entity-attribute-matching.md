---
keywords: 包含ルール；包含基準；レコメンデーション；プロモーション；動的フィルタリング；動的；エンティティ属性の一致
description: 潜在的なアイテムのプールを、ユーザーが操作した特定のアイテムと比較して、[!DNL Target Recommendations]で動的にフィルタリングする方法について説明します。
title: エンティティ属性のマッチング
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: aadd3132-d590-4dc9-b01b-bedf41bc7441
TQID: 'https://experienceleague.adobe.com/2cBSfWXS96u7iumehPd7enxPjQcebkQCdSBSHWOUcJg'
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
source-wordcount: '505'
ht-degree: 9%
---
# エンティティ属性のマッチング {#entity-attribute-matching}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、潜在的な推奨アイテムのプールを、訪問者が操作した特定のアイテムと比較することで、[!DNL Adobe Target Recommendations]でレコメンデーションを動的にフィルタリングする方法について説明します。

>[!ENDSHADEBOX]

**[!UICONTROL エンティティ属性一致]**&#x200B;では、訪問者が操作した項目の属性に一致する項目のみが推奨されます。 条件とプロモーションでは、インクルージョンルールを作成、使用する方法は類似しています。使用例やサンプルも同様です。 詳しくは、[動的および静的インクルージョンルールの使用](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md)を参照してください。

## エンティティ属性の一致の例

**[!UICONTROL エンティティ属性の一致]**&#x200B;は、一致する項目のみを推奨できます。例：

* 訪問者が現在表示している項目の属性
* 訪問者が最近閲覧した項目
* 訪問者が最近購入した商品
* 訪問者が最も頻繁に閲覧する項目
* 訪問者のプロファイル内のカスタム属性に格納された項目

### ブランドに基づいた商品のレコメンデーション

エンティティ属性ルールを作成すると、ページで渡されたエンティティ値と一致しない属性を持つすべてのレコメンデーションがフィルタリングされます。 このプロセスが機能するには、ページ上のmboxで`entity.brand`値を配信する必要があります。

この種類の動的インクルージョンルールでは、ブランド名ごとにコレクションや静的フィルターではなく、すべてのブランドページをまたいで関連するブランド結果を返すために、1つのレコメンデーションルールのみを指定する必要があります。

例えば、ブランド Aの製品を特徴とするページが表示される場合、ページは`entity.brand` パラメーターの値を「BrandA」に設定します。 ブランドのランディングページで、mboxは`entity.brand=brandA`を返します。

![Target呼び出しの例](/help/main/c-recommendations/c-algorithms/assets/example-target-call.png)

ページのレコメンデーションにはブランド Aの商品のみが含まれます。

![&#x200B; ブランド Aのおすすめ](/help/main/c-recommendations/c-algorithms/assets/brandA.png)

ブランド Bの製品ページが表示されると、`entity.brand`の値が「ブランド B」にリセットされ、ブランド Bの製品のみが推奨されます。 同様に、ブランド Bのブランドランディングページでは、ブランド Bの商品のみが返されます。

![&#x200B; ブランド B レコメンデーション &#x200B;](/help/main/c-recommendations/c-algorithms/assets/brandB.png)

### より高価な商品へのアップセル

訪問者に高価格を検討し、より収益性の高い商品を検討するように促すために、「等しい」および「間にある」演算子は、同じカテゴリと同じブランドからより高価な商品を宣伝できます。 例えば、靴のretailerでは、次のサンプルのように、ランニングシューズを見ている訪問者に対して、より高額なランニングシューズを宣伝してアップセルすることができます。

![&#x200B; アップセル &#x200B;](/help/main/c-recommendations/c-algorithms/assets/upsell-new.png)

```
Entity Attribute Matching
category - equals - current item's - category 
And 
Entity Attribute Matching
brand - equals - current item's - brand 
And 
Entity Attribute Matching
value - is between - 100% and 1000% of - current item's - value
```

### プライベートブランド商品の促進

ダイナミックフィルターと静的フィルターを混在させて、プライベートラベルの商品を宣伝することもできます。 例えば、オフィス用品メーカーは、次の例のように、自社のハウスブランドのトナーカートリッジを宣伝することで、トナーを見ている訪問者にとってより収益性の高い販売を促進できます。

![&#x200B; ハウスブランド &#x200B;](/help/main/c-recommendations/c-algorithms/assets/housebrand-new.png)

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```
