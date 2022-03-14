---
keywords: インクルージョンルール；インクルージョン条件；レコメンデーション；プロモーション；プロモーション；動的フィルタリング；動的；プロファイル属性の一致
description: Adobeで動的にフィルタリングする方法を説明します [!DNL Target] Recommendationsを比較することを推奨します。
title: Recommendationsアクティビティで一致するプロファイル属性でフィルタリングする方法を教えてください。
feature: Recommendations
exl-id: d4b837af-771b-41b4-982b-f9f08e4753f2
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 6%

---

# ![プレミアム](/help/main/assets/premium.png) プロファイル属性のマッチング

で動的にフィルタリング [!DNL Adobe Target] [!DNL Recommendations] 品目（エンティティ）とユーザーのプロファイルの値を比較する方法を示します。

用途 [!UICONTROL プロファイル属性のマッチング] サイズやお気に入りのブランドなど、訪問者のプロファイルに保存された値に一致するレコメンデーションを表示する場合に、

>[!NOTE]
>
>この [インクルージョンルールの作成と使用のプロセス](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) の条件とプロモーションは、の使用例や例と同様に似ています。

以下のシナリオで、 [!UICONTROL プロファイル属性のマッチング]:

* メガネを販売する会社は、訪問者が好きなフレームカラーを「くるみ」として店に入れています。 その特定の訪問者に対して、「クルミ」の色に一致する眼鏡フレームのみを返すように設定することをお勧めします。
* 訪問者が会社の Web サイトをナビゲートする際の訪問者の服のサイズ（小、中、大など）に対して、プロファイルパラメーターを定義できます。 レコメンデーションは、そのプロファイルパラメーターに合わせて設定し、ユーザーの希望する衣料品のサイズに限定した商品を返すことができます。

## プロファイル属性のマッチングの例 {#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL プロファイル属性のマッチング] では、以下の例に示すように、訪問者のプロファイルの属性に一致する項目のみをレコメンデーションできます。

### ユーザーのお気に入りのブランドから品目をレコメンデーション

例えば、 [!UICONTROL プロファイル属性のマッチング] オプションを使用して、ブランドがに保存されている値やテキストと等しい品目のみをレコメンデーションするルールを作成できます。 `profile.favoritebrand`. このようなルールでは、ある訪問者が特定のブランドのランニングショーツを閲覧している場合は、その訪問者のお気に入りのブランド（その訪問者のプロファイルの `profile.favoritebrand` に保存されている値）と一致する品目のみがレコメンデーションされます。

![お気に入りのブランド](/help/main/c-recommendations/c-algorithms/assets/favorite-brand.png)

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### ジョブと求職者との一致

求職者とのマッチングを試みているとします 求職者と同じ都市にいるジョブのみをレコメンデーションしたい場合。

次の例に示すように、インクルージョンルールを使用して、訪問者のプロファイルから求人情報の検索場所をジョブリストに一致させることができます。

![ユーザーの市区町村](/help/main/c-recommendations/c-algorithms/assets/city.png)

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

### サイズに基づく品目のレコメンデーション

プロファイル属性のマッチングがレコメンデーションに与える影響の視覚的な例については、電気ファンを販売する Web サイトを考えてみましょう。

訪問者がこの Web サイト上の様々なファンの画像をクリックすると、各ページが `entity.size` 画像内のファンのサイズが小さいか大きいかに基づくパラメーター。

追跡するプロファイルスクリプトを作成し、 `entity.size` は「小」と「大」のどちらに設定されているかを比較して選択します。

その後訪問者がホームページに戻ると、小さいファンと大きいファンのどちらがクリックされたかに基づいて、フィルターされたレコメンデーションが表示されます。

Recommendationsは、Web サイトでのより多くの小規模なファンの閲覧に基づいています。

![小さなファンのレコメンデーション](/help/main/c-recommendations/c-algorithms/assets/small-fans.png)

Recommendationsは、Web サイトでのより多くの大きなファンの表示に基づいています。

![大ファンのレコメンデーション](/help/main/c-recommendations/c-algorithms/assets/large-fans.png)
