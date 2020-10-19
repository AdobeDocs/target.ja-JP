---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;dynamic;entity attribute matching
description: 推定品目のプールを、ユーザーが操作を行った特定の品目と比較して、Adobe TargetRecommendationsで動的にフィルタリングします。
title: Adobe TargetRecommendationsの動的包含ルールでのエンティティ属性一致によるフィルター
feature: criteria
translation-type: tm+mt
source-git-commit: b51c980d8e7db3ee574350a04f9056fe5b00a703
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 0%

---


# ![PREMIUM](/help/assets/premium.png) Entity Attribute Matching

Filter dynamically in [!DNL Adobe Target] [!DNL Recommendations] by comparing a pool of potential recommendations items to a specific item that the user has interacted with.

例えば、次の例のように、現在の品目のブランドに一致するレコメンデーション品目のみを表示します。

ブランドランディングページのmboxが返され `entity.brand=Nike`る場合は、Nike製品のみが返され、そのページに表示されます。 同様に、Adidasのブランドランディングページでは、Adidas製品のみが返されます。 このタイプの動的包含ルールでは、ユーザーは、各ブランド名に一致するコレクションや静的フィルターを指定する代わりに、すべてのブランドページで関連するブランド結果を返す1つのレコメンデーションルールを指定する必要があります。

## エンティティ属性の一致の例

[!UICONTROL エンティティ属性の一致] では、次のように、一致する品目のみをレコメンデーションできます。

* ユーザーが現在表示中の項目の属性。
* ユーザーが最後に閲覧した品目
* ユーザーが最近購入した品目
* ユーザーが最も頻繁に閲覧した品目
* 訪問者のプロファイルーのカスタム属性に格納されたアイテム

### より高価な製品にアップセル

アパレル小売業者で、ユーザーに高価格でより利益率の高い商品の検討を促したいとします。 「等しい」演算子と「次の範囲内」演算子を使用して、同じカテゴリおよび同じブランドのより高価な品目をプロモーションできます。 例えば、靴小売業者は、次のコード例のように、ランニングシューズを見る訪問者を高額で販売するために、より高価なランニングシューズの販売を促進できます。

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

### プライベートラベル商品の販促

動的な製品と静的なフィルターを組み合わせて、プライベートラベルの製品を推進できます。 例えば、オフィス供給会社は、次のコード例のように、会社の住宅ブランドのトナーカートリッジを促進して、トナーを探す訪問者の売り上げを増やし、会社の住宅ブランドのペンを促進して、ペンを探す訪問者の売り上げを増やします。

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```
