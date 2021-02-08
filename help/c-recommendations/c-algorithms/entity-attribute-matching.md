---
keywords: 包含ルール；包含条件；レコメンデーション；プロモーション；動的フィルタリング；動的；エンティティ属性の一致
description: Adobe TargetRecommendationsで、見込み品目のプールを、ユーザーが操作を行った特定の品目と比較して、動的にフィルタリングする方法を説明します。
title: Recommendationsアクティビティでエンティティ属性の照合を使用してフィルタリングする方法
feature: Recommendations
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 0%

---


# ![PREMIUMEntity属性の](/help/assets/premium.png) 一致

推定品目のプールをユーザーが操作を行った特定の品目と比較して、[!DNL Adobe Target] [!DNL Recommendations]内で動的にフィルタリングします。

>[!NOTE]
>
>条件とプロモーションに対してインクルージョンルール](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md)を作成し、使用する[プロセスは、使用例や例と同様に似ています。

例えば、次の例のように、現在の品目のブランドに一致する品目のみをレコメンデーションします。

ブランドランディングページのmboxが`entity.brand=brandA`を返す場合、ブランドA製品のみが返され、そのページに表示されます。 同様に、ブランドBのブランドランディングページでは、ブランドBの商品のみが返されます。 このタイプの動的包含ルールでは、各ブランド名に一致するコレクションや静的フィルターを指定する代わりに、すべてのブランドページで関連するブランド結果を返すレコメンデーションルールを1つだけ指定する必要があります。

この機能を有効にするには、mbox内の`entity.brand`をこれらのランディングページーで配信する必要があります。

## エンティティ属性の一致の例

[!UICONTROL エンティティ属性] の一致では、次のように、一致する品目のみをレコメンデーションできます。

* ユーザーが現在表示中の項目の属性。
* ユーザーが最後に閲覧した品目
* ユーザーが最近購入した品目
* ユーザーが最も頻繁に閲覧した品目
* 訪問者のプロファイルーのカスタム属性に格納されたアイテム

### ブランドに基づいて品目をレコメンデーション

エンティティ属性ルールを作成すると、ページで渡されたエンティティ値と一致しない属性を持つすべてのレコメンデーションがフィルターで除外されます。

次の例は、ページに表示される商品ブランドに合わせたレコメンデーションを示しています。

ブランドA製品を含むページにアクセスすると、そのページでは`entity.brand`パラメーターの値が「BrandA」に設定されます。

![ターゲット呼び出しの例](/help/c-recommendations/c-algorithms/assets/example-target-call.png)

ページのレコメンデーションでは、ブランドA製品のみが表示されます。

![ブランドAの推奨事項](/help/c-recommendations/c-algorithms/assets/brandA.png)

その後ブランドB製品ページを表示すると、`entity.brand`値は「BrandB」にリセットされ、ブランドB製品ページでレコメンデーションされたブランドB製品が表示されます。

![ブランドBの推奨事項](/help/c-recommendations/c-algorithms/assets/brandB.png)

### より高価な製品にアップセル

アパレル小売業者で、ユーザーに高価格でより利益率の高い商品の検討を促したいとします。 「等しい」演算子と「次の範囲内」演算子を使用して、同じカテゴリおよび同じブランドのより高価な品目をプロモーションできます。 例えば、靴小売業者は、ランニングシューズを見ている訪問者を高額で販売するために、より高価なランニングシューズの販売を促進できます。次に例を示します。

![アップセル](/help/c-recommendations/c-algorithms/assets/upsell.png)

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

動的な製品と静的なフィルターを組み合わせて、プライベートラベルの製品を推進できます。 例えば、オフィス供給会社は、次の例のように、会社の住宅ブランドのトナーカートリッジを促進して、トナーを探す訪問者の売り上げを増やし、会社の住宅ブランドのペンを促進して、ペンを探す訪問者の売り上げを増やします。

![ハウスブランド](/help/c-recommendations/c-algorithms/assets/housebrand.png)

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```
