---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;dynamic;profile attribute matching
description: Adobe TargetRecommendationsで動的にフィルタリングするには、項目（エンティティ）とユーザーのプロファイルの値を比較します。
title: Adobe TargetRecommendationsの動的包含ルールでのプロファイル属性一致によるフィルター
feature: Recommendations
translation-type: tm+mt
source-git-commit: 7b86db4b45f93a3c6169caf81c2cd52236bb5a45
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 7%

---


# ![](/help/assets/premium.png) PREMIUMProfile属性の一致

[!DNL Adobe Target] [!DNL Recommendations]内で動的にフィルターします。これには、項目（エンティティ）とユーザーのプロファイル内の値を比較します。

[!UICONTROL プロファイル属性の一致]は、サイズやお気に入りのブランドなど、訪問者のプロファイルに保存されている値に一致するレコメンデーションを表示する場合に使用します。

>[!NOTE]
>
>条件とプロモーションに対してインクルージョンルール](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md)を作成し、使用する[プロセスは、使用例や例と同様に似ています。

次のシナリオでは、[!UICONTROL プロファイル属性の一致]の使用方法を示します。

* 眼鏡を販売する会社は、訪問者の好きな枠色を「クルミ」として店に出しています。 その特定の訪問者に対して、「くるみ」に一致する眼鏡フレームのみを返すようにレコメンデーションが設定されます。
* 会社のWebサイトを移動する際の訪問者の衣料品のサイズ（小、中、大など）に対してプロファイルパラメーターを定義できます。 レコメンデーションは、そのプロファイルパラメーターと一致するように設定でき、ユーザーの希望する衣料品のサイズのみに固有の返品商品を設定できます。

## プロファイル属性の一致の例{#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL プロファイル属性] の一致では、次の例のように、訪問者のプロファイルーの属性に一致する品目のみをレコメンデーションできます。

### ユーザーのお気に入りブランドから商品をレコメンデーションする

例えば、[!UICONTROL プロファイル属性の一致]オプションを使用して、ブランドが`profile.favoritebrand`に保存されている値またはテキストと等しい場合にのみ品目をレコメンドするルールを作成できます。 このようなルールでは、ある訪問者が特定のブランドのランニングショーツを閲覧している場合は、その訪問者のお気に入りのブランド（その訪問者のプロファイルの `profile.favoritebrand` に保存されている値）と一致する品目のみがレコメンデーションされます。

![お気に入りのブランド](/help/c-recommendations/c-algorithms/assets/favorite-brand.png)

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### ジョブを求職者に一致させる

求職者と仕事を一致させようとしているとします 求職者と同じ都市にあるジョブのみをレコメンデーションしたい。

次の例のように、インクルージョンルールを使用して、訪問者のプロファイルーの求職者の場所をジョブリストに一致させることができます。

![ユーザーの市区町村](/help/c-recommendations/c-algorithms/assets/city.png)

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

### サイズに基づいて品目をレコメンデーション

プロファイル属性の一致がrecommendationsに与える影響を視覚的に示す例として、電気ファンを販売するWebサイトを考えてみましょう。

訪問者がこのWebサイトの様々なファンの画像をクリックすると、各ページには、画像内のファンのサイズが小さいか大きいかに基づいて`entity.size`パラメーターの値が設定されます。

例えば、`entity.size`の値が小さい値と大きい値に設定された回数を追跡およびカウントするプロファイルスクリプトを作成したとします。

その後訪問者がホームページに戻ると、より小さいファンがクリックしたか、より大きいファンがクリックしたかに基づいて、フィルターされたレコメンデーションが表示されます。

Recommendationsは、Webサイトでより小さなファンを増やしていることに基づいている。

![小さなファンの勧め](/help/c-recommendations/c-algorithms/assets/small-fans.png)

Recommendationsは、ウェブサイトでより多くの大きなファンを見たことに基づいている。

![大ファンの推奨](/help/c-recommendations/c-algorithms/assets/large-fans.png)