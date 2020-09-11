---
keywords: inclusion rules;inclusion criteria;recommendations;create new criteria;promotion;promotions;dynamic filtering;dynamic;empty values;ignore filtering rule;static filter;filter by value;entity attribute matching;profile attribute matching;parameter matching;filter by value;static filter
description: 条件およびプロモーション用のインクルージョンルールをAdobe TargetRecommendationsで作成し、より良い結果を得るために動的または静的フィルタールールを追加する方法について説明します。
title: Adobe TargetRecommendationsで動的および静的インクルージョンルールを使用
feature: criteria
mini-toc-levels: 3
uuid: f0ee2086-1126-44a4-9379-aa897dc0e06b
translation-type: tm+mt
source-git-commit: 381c405e55475f2474881541698d69b87eddf6fb
workflow-type: tm+mt
source-wordcount: '1478'
ht-degree: 56%

---


# ![PREMIUM](/help/assets/premium.png) 動的および静的インクルージョンルールの使用{#use-dynamic-and-static-inclusion-rules}

Adobe Targetで条件およびプロモーション用のインクルージョンルールを作成し、レコメンデーションの結果を高めるために動的または静的フィルタールールを追加する方法について説明します。

条件とプロモーションでは、インクルージョンルールを作成、使用する方法は類似しています。使用例やサンプルも同様です。このトピックでは、条件およびプロモーションと、インクルージョンルールの使い方について説明します。

## フィルタールールを条件に追加する {#section_CD0D74B8D3BE4A75A78C36CF24A8C57F}

[条件の作成](../../c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE)時に、**[!UICONTROL インクルージョンルール]**&#x200B;の「**[!UICONTROL フィルタールールを追加]**」をクリックします。 

![](assets/inclusion_options_new.png)

利用できるオプションは、選択した業種とレコメンデーションキーによって変わります。

## フィルタールールをプロモーションに追加する {#section_D59AFB62E2EE423086281CF5D18B1076}

[プロモーションの作成](../../c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14)時に、「**[!UICONTROL 属性別にプロモート]**」、「**[!UICONTROL フィルタールールを追加]**」の順にクリックします。

![](assets/inclusion_options.png)

## フィルターのタイプ {#section_0125F1ED10A84C0EB45325122460EBCD}

次の表には、条件とプロモーションで利用できるフィルターオプションのタイプがまとめられています。

### 動的フィルター

動的フィルタリングには、次のオプションを使用できます。

#### エンティティ属性のマッチング

推定品目のプールを、ユーザーが操作を行った特定の品目と比較して、動的にフィルタリングします。

例えば、現在の品目のブランドと一致する品目のみをレコメンデーションできます。

使用可能な演算子：

* equals
* 次と等しくない
* 範囲内
* 次を含む
* 次を含まない
* 次の語句で始まる
* 次の語句で終わる
* 値が存在する
* 値が存在しない
* 次よりも大きいか等しい
* 次よりも小さいか等しい

#### プロファイル属性のマッチング

項目（エンティティ）をユーザーのプロファイルー内の値と比較して、動的にフィルタリングします。

例えば、訪問者が好きなブランドと一致する品目のみをレコメンデーションできます。

使用可能な演算子：

* equals
* 次と等しくない
* 次を含む
* 次を含まない
* 次の語句で始まる
* 次の語句で終わる
* 次よりも大きいか等しい
* 次よりも小さいか等しい
* 範囲内

#### パラメーターのマッチング

項目（エンティティ）とリクエスト（APIまたはmbox）内の値を比較して、動的にフィルターします。

例えば、「業種」ページパラメーターに一致するコンテンツのみをレコメンデーションできます。

重要：2016 年 11 月 1 日以前に作成されたアクティビティの場合、「パラメーターのマッチング」フィルターを使用すると配信に失敗します。この問題を回避する方法は次のとおりです。

* 新しいアクティビティを作成し、条件を追加します。
* 「パラメーターのマッチング」フィルターを含まない条件を使用します。
* 条件から「パラメーターのマッチング」フィルターを削除します。

使用可能な演算子：

* equals
* 次と等しくない
* 次を含む
* 次を含まない
* 次の語句で始まる
* 次の語句で終わる
* 次よりも大きいか等しい
* 次よりも小さいか等しい
* 範囲内

### 値でフィルター

動的フィルタリングには、次のオプションを使用できます。

#### 静的フィルター

フィルタリングする1つ以上の静的な値を手動で入力します。

例えば、MPAA レーティングが「G」または「PG」のコンテンツのみをレコメンデーションできます。

使用可能な演算子：

* equals
* 次と等しくない
* 次を含む
* 次を含まない
* 次の語句で始まる
* 次の語句で終わる
* 値が存在する
* 値が存在しない
* 次よりも大きいか等しい
* 次よりも小さいか等しい

>[!NOTE]
>
>Target 17.6.1 リリース（2017 年 6 月）以前におけるインクルージョンルールの設定方法に慣れている場合は、一部のオプションや演算子が変わっていることに気付くかもしれません。選択したオプションに適用できる演算子のみが表示されるようになり、いくつかの演算子は、よりわかりやすく一貫性のある名前に変更されています（「一致」が「次に等しい」になるなど）。このリリース以前に作成された既存の除外ルールは、新しい方式に自動的に移行されているので、手動で再設定をおこなう必要はありません。

インクルージョンルールは必要に応じて無制限に作成できます。インクルージョンルールは AND 演算子で結合します。品目がレコメンデーションに含まれるためには、すべてのルールを満たす必要があります。

## 動的な条件とプロモーションの例

動的条件と動的プロモーションは、静的条件と静的プロモーションよりもかなり効果的で、成果やエンゲージメントを高めることができます。

マーケティング活動で動的プロモーションを使用する際に、参考になる例を次に示します。

### 次と等しい

動的プロモーションで「等しい」演算子を使用すると、訪問者がWebサイト上のアイテム（製品、記事、映画など）を表示している場合に、次のアイテムの他のアイテムをプロモーションできます。

* 同じブランド
* 同じカテゴリ
* 同じカテゴリの自社ブランド
* 同じ店舗

### 次と等しくない

動的プロモーションで「等しくない」演算子を使用すると、訪問者がWebサイト上のアイテム（製品、記事、映画など）を表示している場合に、次のアイテムの他のアイテムをプロモーションできます。

* 別の TV シリーズ
* 別のジャンル
* 別の商品シリーズ
* 別のスタイル ID

### is between (範囲内)

動的プロモーションで「次の範囲内」演算子を使用すると、訪問者がWebサイト上のアイテム（製品、記事、映画など）を表示している場合に、次のような他のアイテムをプロモーションできます。

* より高価格
* より低価格
* 価格がプラスマイナス 30％
* 同じシーズンの後続のエピソード
* シリーズの前巻

## Handling empty values when filtering by Entity Attribute Matching, Profile Attribute Matching, and Parameter Matching {#section_7D30E04116DB47BEA6FF840A3424A4C8}

You can choose several options to handle empty values when filtering by [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching], and [!UICONTROL Parameter Matching] for exit criteria and promotions.

以前は、値が空の場合は何も結果が返されませんでした。次の図のように、「*x* が空の場合」ドロップダウンリストを使用することで、条件に空の値があった場合に実行する処理を選択できます。

![](assets/empty_value.png)

処理を選択するには、歯車アイコン（![](assets/icon_gear.png)）にマウスポインターを置いてから、目的の処理を選択します。

| アクション | 利用できるマッチング | 詳細 |
|--- |--- |--- |
| このフィルタールールを無視 | プロファイル属性のマッチング<br>パラメーターのマッチング | プロファイル属性のマッチングとパラメーターのマッチングのデフォルトの処理です。<br>このオプションではルールを無視するよう指定します。例えば、3 つのフィルタールールがあり、3 つ目のルールでは何も値が返されなかった場合は、何も結果を返さないのではなく、値が空だった 3 つ目のルールのみを無視できます。 |
| どの項目もプロモートしない | エンティティ属性<br>の一致プロファイル属性<br>の一致パラメーターの一致 | エンティティ属性のマッチングのデフォルトの処理です。<br>[!DNL Target] にこのオプションが追加される前の処理方法です。この条件の結果を表示しません。 |
| 静的値を使用 | エンティティ属性のマッチング<br>プロファイル属性のマッチング<br>パラメーターのマッチング | 値が空だった場合に静的値を使用するよう設定できます。 |

## プロファイル属性の一致の例 {#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL 「プロファイル属性の一致] 」では、次の例のように、訪問者のプロファイルーの属性に一致する品目のみをレコメンデーションできます。

### 例1:ユーザーのお気に入りブランドから商品をレコメンデーションする

For example, you can use the [!UICONTROL Profile Attribute Matching] option to create a rule that recommends items only where the brand equals the value or text stored in `profile.favoritebrand`. このようなルールでは、ある訪問者が特定のブランドのランニングショーツを閲覧している場合は、その訪問者のお気に入りのブランド（その訪問者のプロファイルの `profile.favoritebrand` に保存されている値）と一致する品目のみがレコメンデーションされます。

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### 例2:ジョブを求職者に一致させる

求職者と仕事を一致させようとしているとします 求職者と同じ都市にあるジョブのみをレコメンデーションしたい。

次の例のように、インクルージョンルールを使用して、訪問者のプロファイルーの求職者の場所をジョブリストに一致させることができます。

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

## エンティティ属性の一致の例

[!UICONTROL エンティティ属性の照合] では、次の例のように、現在閲覧中の品目、最近閲覧された品目、最近購入した品目、最も頻繁に閲覧した品目または訪問者プロファイルのカスタム属性に保存された品目に一致する品目のみをレコメンデーションできます。

### 例3:より高価な製品にアップセル

アパレル小売業者で、ユーザーに高価格でより利益率の高い商品の検討を促したいとします。 「等しい」演算子と「次の範囲内」演算子を使用して、同じカテゴリおよび同じブランドのより高価な品目をプロモーションできます。 例えば、靴の小売業者は、ランニングシューズを見ている訪問者を高額で販売するために、より高価なランニングシューズを販売することができます。

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

### 例4:プライベートラベル商品の販促

動的な製品と静的なフィルターを組み合わせて、プライベートラベルの製品を推進できます。 例えば、オフィス供給会社は、会社の家のブランドのトナーカートリッジを促進して、トナーを探す訪問者の売り上げを増やし、会社の家のブランドのペンを促進して、ペンを探す訪問者の売り上げを増やすことができます。

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```

## 注意事項 {#section_A889FAF794B7458CA074DEE06DD0E345}

>[!IMPORTANT]
>
>データタイプが異なる属性に対して「次に等しい」および「等しくない」演算子を使用した動的な条件またはプロモーションでは、実行時に互換性がない可能性があります。You should use [!UICONTROL Value], [!UICONTROL Margin], [!UICONTROL Inventory], and [!UICONTROL Environment] values wisely on the right hand side if the left hand side has predefined attributes or custom attributes.

![](assets/left_right.png)

以下の表に、効果的なルールと実行時に互換性のない可能性のあるルールを示します。

| 互換性のあるルール | 互換性のない可能性のあるルール |
|--- |--- |
| value - is between - 90% and 110% of current item&#39;s - salesValue | salesValue - is between - 90% and 110% of current item&#39;s - value |
| value - is between - 90% and 110% of current item&#39;s - value | clearancePrice - is between - 90% and 110% of current item&#39;s - margin |
| margin - is between - 90% and 110% of current item&#39;s - margin | storeInventory - equals - current item&#39;s - inventory |
| inventory - equals - current item&#39;s - inventory |  |
