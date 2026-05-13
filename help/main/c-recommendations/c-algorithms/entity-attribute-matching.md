---
keywords: 包含ルール；包含基準；レコメンデーション；プロモーション；動的フィルタリング；動的；エンティティ属性の一致
description: 潜在的なアイテムのプールを、ユーザーが操作した特定のアイテムと比較して、 [!DNL Target Recommendations] で動的にフィルタリングする方法について説明します。
title: Recommendations アクティビティでエンティティ属性の一致をフィルタリングするにはどうすればよいですか？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: aadd3132-d590-4dc9-b01b-bedf41bc7441
TQID: https://experienceleague.adobe.com/2cBSfWXS96u7iumehPd7enxPjQcebkQCdSBSHWOUcJg
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 540
ht-degree: 4%

---

# エンティティ属性のマッチング

潜在的なレコメンデーション項目のプールを、ユーザーが操作した特定の項目と比較することで、[!DNL Adobe Target Recommendations]で動的にフィルターを実行します。

>[!NOTE]
>
>条件とプロモーションに含めるルール ](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md)を作成して使用する[ プロセスは、ユースケースと例と同様に類似しています。

例えば、次の例のように、現在の項目のブランドに一致する項目のみをレコメンデーションします。

ブランド ランディングページのmboxが`entity.brand=brandA`を返した場合、ブランド Aの製品のみが返され、そのページに表示されます。 同様に、ブランド Bのブランドランディングページでは、ブランド Bの商品のみが返されます。 この種類の動的インクルージョンルールでは、ユーザーは、各ブランド名に一致するコレクションや静的フィルターを指定するのではなく、すべてのブランドページにわたって関連するブランド結果を返すレコメンデーションルールを1つだけ指定する必要があります。

このプロセスを機能させるには、これらのランディングページのmboxで`entity.brand`を配信する必要があります。

## エンティティ属性の一致の例

[!UICONTROL Entity Attribute Matching]では、次のように一致する項目のみをレコメンデーションできます。

* ユーザーが現在表示している項目の属性
* ユーザーが最近閲覧した項目
* ユーザーが最近購入した商品
* ユーザーが最も頻繁に閲覧する項目
* 訪問者のプロファイルのカスタム属性に保存された項目

### ブランドに基づいた商品のレコメンデーション

エンティティ属性ルールを作成すると、ページで渡されたエンティティ値と一致しない属性を持つすべてのレコメンデーションが除外されます。

次の例は、ページに表示されている商品ブランドに一致するレコメンデーションを示しています。

ブランド A製品を特徴とするページにアクセスすると、ページは`entity.brand` パラメーターの値を「BrandA」に設定します。

![Target呼び出しの例](/help/main/c-recommendations/c-algorithms/assets/example-target-call.png)

ページのレコメンデーションには、ブランド Aの商品のみが表示されます。

![ ブランド Aのおすすめ](/help/main/c-recommendations/c-algorithms/assets/brandA.png)

ブランド Bの製品ページを表示すると、`entity.brand`の値が「ブランド B」にリセットされ、ブランド Bの製品ページでブランド Bの製品が推奨されます。

![ ブランド B レコメンデーション ](/help/main/c-recommendations/c-algorithms/assets/brandB.png)

### より高価な商品へのアップセル

例えば、アパレル企業が、retailerの高価格帯の商品を購入するように促したい場合、 「等しい」演算子と「次の値の間にある」演算子を使用すると、同じカテゴリと同じブランドの高価な項目を宣伝できます。 例えば、靴のretailerは、次のサンプルのように、ランニングシューズを見ている訪問者にアップセルするために、より高価なランニングシューズを宣伝できます。

![ アップセル ](/help/main/c-recommendations/c-algorithms/assets/upsell-new.png)

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

動的フィルターと静的フィルターを組み合わせることで、プライベートラベルの商品を宣伝できます。 たとえば、オフィス用品メーカーは、同社のハウスブランドのトナーカートリッジを宣伝して、トナーを見る訪問者にとってより収益性の高い販売を促進することができます。また、次の例のように、同社のハウスブランドのペンを宣伝して、ペンを見る訪問者にとってより収益性の高い販売を促進することもできます。

![ ハウスブランド](/help/main/c-recommendations/c-algorithms/assets/housebrand-new.png)
)

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```
