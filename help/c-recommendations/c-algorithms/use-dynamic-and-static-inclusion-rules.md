---
keywords: inclusion rules;inclusion criteria;recommendations;create new criteria;promotion;promotions;dynamic filtering;dynamic;empty values;ignore filtering rule;static filter;filter by value;entity attribute matching;profile attribute matching;parameter matching;filter by value;static filter
description: 条件およびプロモーション用のインクルージョンルールをAdobe TargetRecommendationsで作成し、より良い結果を得るために動的または静的フィルタールールを追加する方法について説明します。
title: Adobe TargetRecommendationsで動的および静的インクルージョンルールを使用
feature: criteria
mini-toc-levels: 3
uuid: f0ee2086-1126-44a4-9379-aa897dc0e06b
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '1062'
ht-degree: 39%

---


# ![PREMIUM](/help/assets/premium.png) 動的および静的インクルージョンルールの使用{#use-dynamic-and-static-inclusion-rules}

Information about creating inclusion rules for criteria and promotions in [!DNL Adobe Target] and adding additional dynamic or static filtering rules to achieve better results for your recommendations.

>[!NOTE]
>
>条件とプロモーションでは、インクルージョンルールを作成、使用する方法は類似しています。使用例やサンプルも同様です。この節では、条件とプロモーション、およびインクルージョンルールの使用について説明します。

## フィルタールールを条件に追加する {#section_CD0D74B8D3BE4A75A78C36CF24A8C57F}

[条件の作成](/help/c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE)時に、**[!UICONTROL インクルージョンルール]**&#x200B;の「**[!UICONTROL フィルタールールを追加]**」をクリックします。 

![](assets/inclusion_options_new.png)

利用できるオプションは、選択した業種とレコメンデーションキーによって変わります。

## フィルタールールをプロモーションに追加する {#section_D59AFB62E2EE423086281CF5D18B1076}

[プロモーションの作成](/help/c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14)時に、「**[!UICONTROL 属性別にプロモート]**」、「**[!UICONTROL フィルタールールを追加]**」の順にクリックします。

![](assets/inclusion_options.png)

## フィルターのタイプ {#section_0125F1ED10A84C0EB45325122460EBCD}

以下の節では、条件とプロモーションの両方に対して、 [!UICONTROL 動的フィルタリング] (Dynamic Filtering)と値による [!UICONTROL フィルタリング(Filter by Value] )のフィルタリングオプションのタイプをリストします。

### 動的フィルター

動的インクルージョンルールは静的インクルージョンルールよりも強力で、より優れた結果とエンゲージメントをもたらします。 次の点に留意してください。

* 動的なインクルージョンルールは、ユーザーのプロファイルパラメーターまたはmbox呼び出し内の属性を一致させることで、レコメンデーションを配信します。

   例えば、「最頻訪問条件」のレコメンデーションを作成してから返されるレコメンデーションのセットをフィルターし、レコメンデーションが表示されるページにユーザーがアクセスしたときに渡される属性に対して、レコメンデーションを（リアルタイムで）除外できます。

* 静的ルールを使用して、（コレクションを使用する代わりに）レコメンデーションに含める品目を制限します。

* 必要な数の動的インクルージョンルールを作成できます。 インクルージョンルールは AND 演算子で結合します。品目がレコメンデーションに含まれるためには、すべてのルールを満たす必要があります。

動的フィルタリングには、次のオプションを使用できます。

| 動的フィルタリングオプション | 詳細 |
| --- | --- |
| [エンティティ属性のマッチング](/help/c-recommendations/c-algorithms/entity-attribute-matching.md) | 推定品目のプールを、ユーザーが操作を行った特定の品目と比較して、動的にフィルタリングします。<br>訪問者のお気に入りのブランドなど、訪問者にとって最も魅力的なレコメンデーションを表示したい場合に、  エンティティ属性の一致を使用します。 |
| [プロファイル属性のマッチング](/help/c-recommendations/c-algorithms/profile-attribute-matching.md) | 項目（エンティティ）をユーザーのプロファイルー内の値と比較して、動的にフィルタリングします。<br>サイズやお気に入りのブランドなど、訪問者のプロファイルに保存されている値に一致するレコメンデーションを表示する場合は、  プロファイル属性の一致を使用します。 |
| [パラメーターのマッチング](/help/c-recommendations/c-algorithms/parameter-matching.md) | 項目（エンティティ）とリクエスト（APIまたはmbox）内の値を比較して、動的にフィルターします。<br>「 [!UICONTROL パラメーターの一致] 」を使用して、ページのパラメーターまたは訪問者のパラメーター（デバイスのサイズや地域など）に一致するコンテンツを推奨します。 |

### 値でフィルター

次のオプションは、値によるフィルタリングに使用できます。

| 値によるフィルタリングオプション | 詳細 |
| --- | --- |
| [静的フィルター](/help/c-recommendations/c-algorithms/static-value.md) | フィルタリングする1つ以上の静的な値を手動で入力します。 |

## 動的な条件とプロモーションの例

動的な条件とプロモーションは静的な条件やプロモーションよりもはるかに強力で、より良い結果とエンゲージメントをもたらします。

以下の例は、マーケティング活動で動的なプロモーションをどのように使用できるかに関する一般的なアイデアを提供しています。

| 演算子 | 例 |
| --- | --- |
| 次と等しい | 動的プロモーションで「等しい」演算子を使用すると、訪問者がWebサイト上のアイテム（製品、記事、映画など）を表示している場合に、次のアイテムの他のアイテムをプロモーションできます。<ul><li>同じブランド</li><li>同じカテゴリ</li><li>同じカテゴリの自社ブランド</li><li>同じ店舗</li></ul> |
| 次と等しくない | 動的プロモーションで「等しくない」演算子を使用すると、訪問者がWebサイト上のアイテム（製品、記事、映画など）を表示している場合に、次のアイテムの他のアイテムをプロモーションできます。<ul><li>別の TV シリーズ</li><li>別のジャンル</li><li>別の商品シリーズ</li><li>別のスタイル ID</li></ul> |
| is between (範囲内) | 動的プロモーションで「次の範囲内」演算子を使用すると、訪問者がWebサイト上のアイテム（製品、記事、映画など）を表示している場合に、次のような他のアイテムをプロモーションできます。<ul><li>より高価格</li><li>より低価格</li><li>価格がプラスマイナス 30％</li><li>同じシーズンの後続のエピソード</li><li>シリーズの前巻</li></ul> |

## Handling empty values when filtering by Entity Attribute Matching, Profile Attribute Matching, and Parameter Matching {#section_7D30E04116DB47BEA6FF840A3424A4C8}

You can choose several options to handle empty values when filtering by [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching], and [!UICONTROL Parameter Matching] for exit criteria and promotions.

以前は、値が空の場合は何も結果が返されませんでした。次の図のように、「*x* が空の場合」ドロップダウンリストを使用することで、条件に空の値があった場合に実行する処理を選択できます。

![](assets/empty_value.png)

処理を選択するには、歯車アイコン（![](assets/icon_gear.png)）にマウスポインターを置いてから、目的の処理を選択します。

| アクション | 利用できるマッチング | 詳細 |
|--- |--- |--- |
| [!UICONTROL このフィルタールールを無視] | [!UICONTROL プロファイル属性の一致][!UICONTROL とパラメータの一致] | This is the default action for [!UICONTROL Profile Attribute Matching] and [!UICONTROL Parameter Matching].<br>このオプションではルールを無視するよう指定します。例えば、3 つのフィルタールールがあり、3 つ目のルールでは何も値が返されなかった場合は、何も結果を返さないのではなく、値が空だった 3 つ目のルールのみを無視できます。 |
| [!UICONTROL この条件の結果を表示しない]<br>（条件のみ） | [!UICONTROL エンティティ属性の一致]、 [!UICONTROL プロファイル属性の一致]、 [!UICONTROL パラメータの一致] | This is the default action for [!UICONTROL Entity Attribute Matching].<br>[!DNL Target] にこのオプションが追加される前の処理方法です。この条件の結果を表示しません。 |
| [!UICONTROL どの項目もプロモーションしない<br>（プロモーションのみ）] | [!UICONTROL エンティティ属性の一致]、 [!UICONTROL プロファイル属性の一致]、 [!UICONTROL パラメータの一致] | This is the default action for [!UICONTROL Entity Attribute Matching].<br>[!DNL Target] にこのオプションが追加される前の処理方法です。この条件の結果を表示しません。 |
| [!UICONTROL 静的値を使用] | [!UICONTROL エンティティ属性の一致]、 [!UICONTROL プロファイル属性の一致]、 [!UICONTROL パラメータの一致] | 値が空だった場合に静的値を使用するよう設定できます。 |

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
