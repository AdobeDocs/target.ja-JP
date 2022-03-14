---
keywords: インクルージョンルール；インクルージョン条件；レコメンデーション；プロモーション；プロモーション；動的フィルタリング；動的；エンティティ属性の一致
description: Adobeで動的にフィルタリングする方法を説明します [!DNL Target] Recommendationsを使用する場合は、見込み品目のプールと、ユーザーが操作した特定の品目を比較します。
title: Recommendationsアクティビティで一致するエンティティ属性でフィルタリングする方法を教えてください。
feature: Recommendations
exl-id: aadd3132-d590-4dc9-b01b-bedf41bc7441
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 0%

---

# ![プレミアム](/help/main/assets/premium.png) エンティティ属性のマッチング

で動的にフィルタリング [!DNL Adobe Target] [!DNL Recommendations] 推定レコメンデーション品目のプールを、ユーザーが操作した特定の品目と比較することで実現します。

>[!NOTE]
>
>この [インクルージョンルールの作成と使用のプロセス](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) の条件とプロモーションは、の使用例や例と同様に似ています。

例えば、次の例に示すように、現在の品目のブランドと一致する品目のみをレコメンデーションします。

ブランドランディングページの mbox が `entity.brand=brandA`に設定すると、ブランド A 製品のみが返され、そのページに表示されます。 同様に、ブランド B のブランドランディングページでは、ブランド B 製品のみが返されます。 このタイプの動的インクルージョンルールでは、各ブランド名に一致するコレクションや静的フィルターを指定するのではなく、すべてのブランドページで関連するブランド結果を返すレコメンデーションルールを 1 つだけ指定する必要があります。

なお、 `entity.brand` を mbox に設定しておく必要があります。

## エンティティ属性のマッチングの例

[!UICONTROL エンティティ属性のマッチング] では、一致する品目のみをレコメンデーションできます。次に例を示します。

* ユーザーが現在表示している項目の属性
* ユーザーが最近表示した品目
* ユーザーが最近購入した品目
* ユーザーが最も頻繁に閲覧した品目
* 訪問者のプロファイルのカスタム属性に保存された項目

### ブランドに基づく品目のレコメンデーション

エンティティ属性ルールを作成すると、ページで渡されたエンティティ値と一致しない属性を持つレコメンデーションがすべて除外されます。

次の例は、ページに表示される製品ブランドと一致するレコメンデーションを示しています。

Brand A 製品を含むページにアクセスすると、そのページによって `entity.brand` パラメーターを「BrandA」に設定します。

![Target の呼び出しの例](/help/main/c-recommendations/c-algorithms/assets/example-target-call.png)

ページのレコメンデーションには、ブランド A 製品のみが表示されます。

![ブランド A のレコメンデーション](/help/main/c-recommendations/c-algorithms/assets/brandA.png)

その後、ブランド B 製品ページを表示すると、 `entity.brand` の値は「BrandB」にリセットされ、Brand B 製品ページで推奨される Brand B 製品が表示されます。

![ブランド B の推奨事項](/help/main/c-recommendations/c-algorithms/assets/brandB.png)

### より高価な製品へのアップセル

アパレル小売業者で、ユーザーに高価格で、より収益性の高い品目を検討するよう促したいとします。 「次に等しい」および「範囲内」演算子を使用して、同じカテゴリと同じブランドの、より高額な品目をプロモーションできます。 例えば、靴小売業者は、次のサンプルのように、ランニングシューズを見ている訪問者をアップセルするために、より高価なランニングシューズをプロモーションできます。

![アップセル](/help/main/c-recommendations/c-algorithms/assets/upsell.png)

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

動的フィルターと静的フィルターを組み合わせて、プライベートラベル製品を宣伝できます。 例えば、オフィス用品会社は、会社の自社ブランドのトナーカートリッジをプロモートして、トナーを探す訪問者にとってより有益な販売を促し、会社の自社ブランドのペンをプロモートして、ペンを探す訪問者にとってより有益な販売を促すことができます。

![ハウスブランド](/help/main/c-recommendations/c-algorithms/assets/housebrand.png)

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```
