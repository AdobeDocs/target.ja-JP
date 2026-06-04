---
keywords: 包含ルール；包含基準；レコメンデーション；プロモーション；動的フィルタリング；動的；プロファイル属性の一致
description: ユーザーのプロファイル内の値に対して項目（エンティティ）を比較することにより、 [!DNL Target Recommendations] で動的にフィルタリングする方法を説明します。
title: Recommendations アクティビティでプロファイル属性の一致をフィルタリングするにはどうすればよいですか？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: d4b837af-771b-41b4-982b-f9f08e4753f2
TQID: https://experienceleague.adobe.com/Gm91Mww5ylvNjUcmzp6KwxIG6LTibvI44LnW67KFzqk
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 495
ht-degree: 3%

---

# プロファイル属性のマッチング

ユーザーのプロファイル内の値に対して項目（エンティティ）を比較することにより、[!DNL Adobe Target Recommendations]で動的にフィルタリングします。

サイズやお気に入りのブランドなど、訪問者のプロファイルに保存されている値に一致する推奨事項を表示する場合は、[!UICONTROL &#x200B; プロファイル属性の一致]を使用します。

>[!NOTE]
>
>条件とプロモーションに含めるルール [&#128279;](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md)を作成して使用する プロセスは、ユースケースと例と同様に類似しています。

次のシナリオは、[!UICONTROL &#x200B; プロファイル属性の一致]の使用方法を示しています。

* 眼鏡を販売する会社が、訪問者が好むフレームの色を「クルミ」として保存します。 特定の訪問者に対しては、色が「クルミ」に一致する眼鏡フレームのみを返すようにレコメンデーションが設定されています。
* プロファイルパラメーターは、企業のweb サイトを移動する際の訪問者の服のサイズ（小、Medium、大など）に対して定義できます。 レコメンデーションは、プロファイルパラメーターに一致するように設定でき、ユーザーが好む服のサイズに限定した商品を返します。

## プロファイル属性の一致の例 {#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL &#x200B; プロファイル属性の一致]を使用すると、以下の例のように、訪問者のプロファイルの属性に一致する項目のみをレコメンドできます。

### 利用者が好むブランドの商品を勧める

例えば、[!UICONTROL &#x200B; プロファイル属性一致] オプションを使用して、ブランドが`profile.favoritebrand`に保存されている値またはテキストと等しい場合にのみアイテムをレコメンドするルールを作成できます。 このようなルールでは、訪問者が特定のブランドのショーツを使用している場合、そのユーザーのお気に入りのブランド（訪問者のプロファイルに`profile.favoritebrand`に保存されている値）に一致するレコメンデーションのみが表示されます。

![お気に入りのブランド &#x200B;](/help/main/c-recommendations/c-algorithms/assets/favorite-brand-new.png)

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### 求職者と求人のマッチング

例えば、求職者に求人を割り当てようとしているとします。 求職者と同じ都市にある求人のみを推薦する必要があります。

インクルージョンルールを使用すると、次の例のように、訪問者のプロファイルからジョブリストへの求職者の場所を一致させることができます。

![&#x200B; ユーザーの市区町村](/help/main/c-recommendations/c-algorithms/assets/city-new.png)

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

![&#x200B; スモールファンのレコメンデーション &#x200B;](/help/main/c-recommendations/c-algorithms/assets/small-fans.png)

web サイトでより多くのファンを表示することにもとづくレコメンデーション：

![大規模なファンのレコメンデーション &#x200B;](/help/main/c-recommendations/c-algorithms/assets/large-fans.png)
