---
keywords: インクルージョンルール；インクルージョン条件；レコメンデーション；プロモーション；動的；動的フィルタリング；動的；プロファイル属性のマッチング
description: 項目（エンティティ）をユーザーのプロファイルの値と比較することで、Adobe [!DNL Target] Recommendationsを動的にフィルタリングする方法を説明します。
title: Recommendations アクティビティでプロファイル属性のマッチングを使用してフィルタリングするにはどうすればよいですか。
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: d4b837af-771b-41b4-982b-f9f08e4753f2
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 9%

---

# プロファイル属性のマッチング

ユーザーのプロファイルの値に対して項目（エンティティ）を比較することで、[!DNL Adobe Target] [!DNL Recommendations] で動的にフィルタリングします。

サイズやお気に入りのブランドなど、訪問者のプロファイルに保存されている値に一致するお勧めを表示する場合は、[!UICONTROL Profile Attribute Matching] を使用します。

>[!NOTE]
>
>条件やプロモーションに対する [ インクルージョンルールの作成プロセスと使用プロセス ](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) は、ユースケースと例と同様です。

次のシナリオは、[!UICONTROL Profile Attribute Matching] の使用方法を示しています。

* 眼鏡を販売する会社が、訪問者が好きなフレームの色を「くるみ」として保存しています。 特定の訪問者に対しては、カラーで「クルミ」に一致する眼鏡フレームのみを返すようレコメンデーションが設定されます。
* プロファイルパラメーターは、訪問者が会社の web サイトを移動する際に、その訪問者の衣料品のサイズ（小、Medium、大など）に対して定義できます。 レコメンデーションは、そのプロファイルパラメーターに一致するように設定でき、ユーザーの好みの衣料品サイズに固有の製品のみを返すことができます。

## プロファイル属性のマッチングの例 {#section_9873E2F22E094E479569D05AD5BB1D40}

以下の例に示 [!UICONTROL Profile Attribute Matching] ように、訪問者のプロファイルの属性に一致する項目のみをレコメンデーションできます。

### ユーザーのお気に入りのブランドからの推奨項目

例えば、「[!UICONTROL Profile Attribute Matching]」オプションを使用して、ブランドが `profile.favoritebrand` に格納されている値またはテキストと等しい項目のみを推奨するルールを作成できます。 このようなルールでは、ある訪問者が特定のブランドのランニングショーツを閲覧している場合は、その訪問者のお気に入りのブランド（その訪問者のプロファイルの `profile.favoritebrand` に保存されている値）と一致する品目のみがレコメンデーションされます。

![ お気に入りのブランド ](/help/main/c-recommendations/c-algorithms/assets/favorite-brand.png)

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### 求職者とジョブのマッチング

求職者に見合う仕事にしようとしているとしましょう。 求職者と同じ市区町村にあるジョブのみをレコメンデーションします。

次の例に示すように、インクルージョンルールを使用して、求職者の場所を訪問者のプロファイルから求人情報に一致させることができます。

![ ユーザーの市区町村 ](/help/main/c-recommendations/c-algorithms/assets/city.png)

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

### サイズに応じた推奨項目

プロファイル属性のマッチングが Recommendations に与える影響の視覚的な例については、扇風機を販売する web サイトを検討してください。

訪問者がこの web サイト上のファンの様々な画像をクリックすると、各ページは、画像内のファンのサイズが小さいか大きいかに基づいて `entity.size` パラメーターの値を設定します。

`entity.size` の値が small と large に設定された回数を追跡およびカウントするプロファイルスクリプトを作成したとします。

その後、訪問者がホームページに戻ると、小さなファンまたは大きなファンのどちらをクリックしたかに基づいてフィルタリングされたレコメンデーションが表示されます。

Recommendationsは、Web サイトで多くの小さなファンを見ることに基づいています。

![ 小規模なファンの推奨事項 ](/help/main/c-recommendations/c-algorithms/assets/small-fans.png)

Recommendationsは、Web サイトでより多くの大きなファンを見ることに基づいています。

![ 大規模なファンの推奨事項 ](/help/main/c-recommendations/c-algorithms/assets/large-fans.png)
