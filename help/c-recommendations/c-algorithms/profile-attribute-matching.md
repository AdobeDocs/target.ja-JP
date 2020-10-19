---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;dynamic;profile attribute matching
description: Adobe TargetRecommendationsで動的にフィルタリングするには、項目（エンティティ）とユーザーのプロファイルの値を比較します。
title: Adobe TargetRecommendationsの動的包含ルールでのプロファイル属性一致によるフィルター
feature: criteria
translation-type: tm+mt
source-git-commit: c814215476ef6e40f4f175fe3f9dbb2c26b966eb
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 5%

---


# ![PREMIUM](/help/assets/premium.png) プロファイル属性の一致

項目（エンティティ） [!DNL Adobe Target][!DNL Recommendations] をユーザーのプロファイルー内の値と比較して、動的にフィルターします。

サイズやお気に入りのブランドなど、訪問者のプロファイルに保存されている値に一致するレコメンデーションを表示する場合は、  プロファイル属性の一致を使用します。

>[!NOTE]
>
>The [process for creating and using inclusion rules](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) for criteria and promotions is similar, as are the use cases and examples.

次のシナリオでは、 [!UICONTROL プロファイル属性の照合の使用方法を示します]。

* 眼鏡を販売する会社は、訪問者の好きな枠色を「クルミ」として店に出しています。 その特定の訪問者に対して、「くるみ」に一致する眼鏡フレームのみを返すようにレコメンデーションが設定されます。
* 会社のWebサイトを移動する際の訪問者の衣料品のサイズ（小、中、大など）に対してプロファイルパラメーターを定義できます。 レコメンデーションは、そのプロファイルパラメーターと一致するように設定でき、ユーザーの希望する衣料品のサイズのみに固有の返品商品を設定できます。

## プロファイル属性の一致の例 {#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL 「プロファイル属性の一致] 」では、次の例のように、訪問者のプロファイルーの属性に一致する品目のみをレコメンデーションできます。

### ユーザーのお気に入りブランドから商品をレコメンデーションする

For example, you can use the [!UICONTROL Profile Attribute Matching] option to create a rule that recommends items only where the brand equals the value or text stored in `profile.favoritebrand`. このようなルールでは、ある訪問者が特定のブランドのランニングショーツを閲覧している場合は、その訪問者のお気に入りのブランド（その訪問者のプロファイルの `profile.favoritebrand` に保存されている値）と一致する品目のみがレコメンデーションされます。

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### ジョブを求職者に一致させる

求職者と仕事を一致させようとしているとします 求職者と同じ都市にあるジョブのみをレコメンデーションしたい。

次の例のように、インクルージョンルールを使用して、訪問者のプロファイルーの求職者の場所をジョブリストに一致させることができます。

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

### 訪問者のサイズに合う服をレコメンデーションする

訪問者のプロファイルーで設定されている服のサイズに合う服をレコメンデーションする例を見てみましょう。

製品ページからmbox呼び出し `entity.size` が送信されます（下の図の赤い矢印）。

訪問者が最後に訪問したページから訪問者の [プロファイル属性と値を取り込む](/help/c-target/c-visitor-profile/profile-parameters.md) プロファイルスクリプトを作成できます。

例：

```
if ((mbox.name=="target-global-mbox") &&(mbox.param('entity.size') == 'small')) { return 'small';
}

else if ((mbox.name=="target-global-mbox") &&(mbox.param('entity.size') == 'medium')) { return 'medium';
}

else if ((mbox.name=="target-global-mbox") &&(mbox.param('entity.size') == 'large')) { return 'large';
}
```

プロファイルスクリプトは、という名前のmboxから `entity.size` 値をキャプチャ `target-global-mbox` し、その値をという名前のプロファイル属性 `user.size` （下の図の青い矢印）として返します。

![サイズmbox呼び出し](/help/c-recommendations/c-algorithms/assets/size.png)

レコメンデーション条件を作成する場合は、「 **[!UICONTROL 追加フィルタリングルール]**」をクリックし、「 **[!UICONTROL プロファイル属性の一致」を選択します]**。

![プロファイル属性の一致の図](/help/c-recommendations/c-algorithms/assets/profile-attribute-matching.png)

に `user.size` プロファイルが読み込ま [!DNL Target]れている場合、mbox呼び出し(`size`)で渡された値をプロファイルスクリプト名(`user.size`)に一致させるようにルールを設定すると、その値がドロップダウンに表示され、一致の対象となります。

次に、「user.size」に格納されている値やテキストを「size」「equals」として選択し、プロファイル属性との一致を確認します。

![サイズの例](/help/c-recommendations/c-algorithms/assets/example-size.png)

プロファイル属性ルールを構築すると、訪問者に格納されているプロファイル属性と一致しない属性を持つレコメンデーションがすべてフィルターで除外されます。

### サイズに基づいて品目をレコメンデーション

プロファイル属性の一致がrecommendationsに与える影響を視覚的に示す例として、電気ファンを販売するWebサイトを考えてみましょう。

訪問者がこのWebサイトの様々なファンの画像をクリックすると、各ページに、画像内のファンのサイズが小さいか大きいかに基づいて、 `entity.size` パラメーターの値が設定されます。

例えば、の値が小さい値と大きい値のどちらに設定されたかを追跡し、回数をカウントするプロファイルスクリプト `entity.size` を作成したとします。

その後訪問者がホームページに戻ると、より小さいファンがクリックしたか、より大きいファンがクリックしたかに基づいて、フィルターされたレコメンデーションが表示されます。

Recommendationsは、Webサイトでより小さなファンを増やしていることに基づいている。

![小さなファンの勧め](/help/c-recommendations/c-algorithms/assets/small-fans.png)

Recommendationsは、ウェブサイトでより多くの大きなファンを見たことに基づいている。

![大ファンの推奨](/help/c-recommendations/c-algorithms/assets/large-fans.png)