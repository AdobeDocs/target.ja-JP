---
keywords: インクルージョンルール；インクルージョン条件；レコメンデーション；プロモーション；動的；動的フィルタリング；動的；エンティティ属性のマッチング
description: 潜在的な項目のプールを  [!DNL Target Recommendations]  ユーザーがやり取りした特定の項目と比較することで、で動的にフィルタリングする方法を説明します。
title: Recommendations アクティビティでエンティティ属性のマッチングでフィルタリングするにはどうすればよいですか。
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: aadd3132-d590-4dc9-b01b-bedf41bc7441
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 2%

---

# エンティティ属性のマッチング

ユーザーがやり取りした特定の項目に、可能性のあるレコメンデーション項目のプールを比較することで、[!DNL Adobe Target Recommendations] で動的にフィルタリングします。

>[!NOTE]
>
>条件やプロモーションに対する [&#x200B; インクルージョンルールの作成プロセスと使用プロセス &#x200B;](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) は、ユースケースと例と同様です。

例えば、次の例のように、現在の項目のブランドに一致する項目のみをレコメンデーションします。

ブランドランディングページの mbox が `entity.brand=brandA` を返した場合、ブランド A 製品のみが返され、そのページに表示されます。 同様に、ブランド B のブランドランディングページでは、ブランド B の製品のみが返されます。 このタイプの動的インクルージョンルールでは、ユーザーは、各ブランド名に一致するコレクションや静的フィルターを指定するのではなく、すべてのブランドページにわたって関連するブランド結果を返す 1 つのレコメンデーションルールのみを指定する必要があります。

このプロセスを機能させるには、ランディングページの mbox で `entity.brand` を配信する必要があります。

## エンティティ属性のマッチングの例

[!UICONTROL Entity Attribute Matching] では、次のように一致する項目のみをレコメンデーションできます。

* ユーザーが現在表示している項目の属性
* ユーザーが最近表示した項目
* ユーザーが最近購入した項目
* ユーザーが最も頻繁に閲覧した項目
* 訪問者プロファイルのカスタム属性に保存される項目

### ブランドに基づいた推奨項目

エンティティ属性ルールが作成されると、ページで渡されたエンティティ値に一致しない属性を持つすべてのレコメンデーションが除外されます。

製品ブランドに一致するレコメンデーションをページに次の例で表示します。

Brand A 製品を使用するページにアクセスすると、ページは `entity.brand` パラメーターの値を「BrandA」に設定します。

![Target 呼び出しの例 &#x200B;](/help/main/c-recommendations/c-algorithms/assets/example-target-call.png)

ページのレコメンデーションには、ブランド A 製品のみが表示されます。

![Brand A の推奨事項 &#x200B;](/help/main/c-recommendations/c-algorithms/assets/brandA.png)

ブランド B の製品ページを表示すると、`entity.brand` の値が「BrandB」にリセットされ、ブランド B の製品がブランド B の製品ページで推奨されます。

![&#x200B; ブランド B の推奨事項 &#x200B;](/help/main/c-recommendations/c-algorithms/assets/brandB.png)

### より高価な製品へのアップセル

アパレルretailerで、ユーザーに対して、より高価で、したがって、より収益性の高い商品を検討するように促したいとします。 「次に等しい」演算子と「次の範囲内に等しい」演算子を使用して、同じカテゴリおよび同じブランドの高価な商品を宣伝できます。 例えば、靴retailerでは、次のサンプルに示すように、ランニングシューズを見ている訪問者にアップセルする取り組みとして、より高価なランニングシューズを宣伝できます。

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

### プライベートラベル製品のプロモーション

動的フィルターと静的フィルターを混在させて、プライベートラベルの製品を宣伝できます。 例えば、会社のホームブランドのトナーカートリッジを宣伝して、トナーを見ている訪問者にとってより収益性の高い販売を促進することができます。また、次のサンプルのように、会社のホームブランドのペンを宣伝して、ペンを見ている訪問者にとってより収益性の高い販売を促進することができます。

![&#x200B; ハウスブランド &#x200B;](/help/main/c-recommendations/c-algorithms/assets/housebrand-new.png)
）

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```
