---
keywords: 包含ルール；包含基準；レコメンデーション；プロモーション；動的フィルタリング；動的；プロファイル属性の一致
description: Adobe [!DNL Target] Recommendationsで、項目（エンティティ）とユーザープロファイルの値を比較して動的にフィルタリングする方法について説明します。
title: Recommendations アクティビティでプロファイル属性の一致をフィルタリングするにはどうすればよいですか？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: d4b837af-771b-41b4-982b-f9f08e4753f2
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 10%

---

# プロファイル属性のマッチング

ユーザーのプロファイル内の値に対して項目（エンティティ）を比較することにより、[!DNL Adobe Target] [!DNL Recommendations]で動的にフィルタリングします。

サイズやお気に入りのブランドなど、訪問者のプロファイルに保存されている値に一致する推奨事項を表示する場合は、[!UICONTROL  プロファイル属性の一致]を使用します。

>[!NOTE]
>
>条件とプロモーションに含めるルール ](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md)を作成して使用する[ プロセスは、ユースケースと例と同様に類似しています。

次のシナリオは、[!UICONTROL  プロファイル属性の一致]の使用方法を示しています。

* 眼鏡を販売する会社が、訪問者が好むフレームの色を「クルミ」として保存します。 特定の訪問者に対しては、色が「クルミ」に一致する眼鏡フレームのみを返すようにレコメンデーションが設定されています。
* プロファイルパラメーターは、企業のweb サイトを移動する際の訪問者の服のサイズ（小、Medium、大など）に対して定義できます。 レコメンデーションは、プロファイルパラメーターに一致するように設定でき、ユーザーが好む服のサイズに限定した商品を返します。

## プロファイル属性の一致の例 {#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL  プロファイル属性の一致]を使用すると、以下の例のように、訪問者のプロファイルから属性に一致する項目のみをレコメンドできます。

### 利用者が好むブランドの商品を勧める

例えば、[!UICONTROL  プロファイル属性一致] オプションを使用して、ブランドが`profile.favoritebrand`に保存されている値またはテキストと等しい場合にのみアイテムをレコメンドするルールを作成できます。 このようなルールでは、ある訪問者が特定のブランドのランニングショーツを閲覧している場合は、その訪問者のお気に入りのブランド（その訪問者のプロファイルの `profile.favoritebrand` に保存されている値）と一致する品目のレコメンデーションのみが表示されます。

![お気に入りのブランド ](/help/main/c-recommendations/c-algorithms/assets/favorite-brand.png)

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### 求職者と求人のマッチング

例えば、求職者に求人を割り当てようとしているとします。 求職者と同じ都市にある求人のみを推薦する必要があります。

インクルージョンルールを使用すると、次の例のように、求職者の位置を訪問者のプロファイルから求人情報に一致させることができます。

![ ユーザーの市区町村](/help/main/c-recommendations/c-algorithms/assets/city.png)

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

### サイズに応じた商品のレコメンデーション

プロファイル属性のマッチングがレコメンデーションにどのような影響を与えるかを視覚的に示す例として、扇風機を販売するweb サイトを考えてみましょう。

訪問者がこのweb サイト上のファンの様々な画像をクリックすると、各ページは、画像内のファンのサイズが小さいか大きいかに基づいて`entity.size` パラメーターの値を設定します。

`entity.size`の値が小さい値と大きい値に設定された回数を追跡およびカウントするプロファイルスクリプトを作成したとします。

その後、訪問者がホームページに戻ると、より多くのスモールファンまたは大規模なファンがクリックされたかどうかに基づいて、フィルタリングされたレコメンデーションが表示されます。

web サイトでより多くの小規模なファンを表示することに基づくレコメンデーション：

![ スモールファンのレコメンデーション ](/help/main/c-recommendations/c-algorithms/assets/small-fans.png)

web サイトでより多くのファンを表示することにもとづくレコメンデーション：

![大規模なファンのレコメンデーション ](/help/main/c-recommendations/c-algorithms/assets/large-fans.png)
