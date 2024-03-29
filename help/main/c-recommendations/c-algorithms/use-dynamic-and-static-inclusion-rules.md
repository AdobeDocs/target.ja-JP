---
keywords: インクルージョンルール;包含条件;レコメンデーション;新しい条件の作成;プロモーション;動的フィルター;動的;空の値;フィルタールールの無視;静的フィルター;値でフィルター;エンティティ属性のマッチング;プロファイル属性のマッチング;パラメーターのマッチング;値でフィルター;静的フィルター
description: Adobe [!DNL Target] Recommendationsを参照してください。 より良い結果を得るには、より動的なフィルタールールまたは静的なフィルタールールを追加します。
title: Recommendationsで動的および静的インクルージョンルールを使用する方法を教えてください。
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
mini-toc-levels: 3
exl-id: 49b20e75-ee55-4239-94a0-6d175e2d4811
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '2093'
ht-degree: 16%

---

# 動的および静的インクルージョンルールの使用

条件とプロモーションのインクルージョンルールを [!DNL Adobe Target] 動的または静的なフィルタールールを追加して、レコメンデーションの結果を高めることができます。

条件とプロモーションでは、インクルージョンルールを作成、使用する方法は類似しています。使用例やサンプルも同様です。この節では、条件とプロモーション、およびインクルージョンルールの使用について説明します。

## フィルタールールを条件に追加する {#section_CD0D74B8D3BE4A75A78C36CF24A8C57F}

[条件の作成](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE)時に、**[!UICONTROL インクルージョンルール]**&#x200B;の「**[!UICONTROL フィルタールールを追加]**」をクリックします。 

![inclusion_options_new image](assets/inclusion_options_new.png)

利用できるオプションは、選択した業種とレコメンデーションキーによって変わります。

## フィルタールールをプロモーションに追加する {#section_D59AFB62E2EE423086281CF5D18B1076}

[プロモーションの作成](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14)時に、「**[!UICONTROL 属性別にプロモート]**」、「**[!UICONTROL フィルタールールを追加]**」の順にクリックします。

![inclusion_options 画像](assets/inclusion_options.png)

## フィルターのタイプ {#section_0125F1ED10A84C0EB45325122460EBCD}

以下の節では、 [!UICONTROL 動的フィルタリング] および [!UICONTROL 値でフィルター] 条件とプロモーションの両方で

### 動的フィルター

動的インクルージョンルールは、静的インクルージョンルールよりも強力で、より優れた結果とエンゲージメントを生み出します。 次の点に留意してください。

* 動的インクルージョンルールは、ユーザーのプロファイルパラメーターまたは mbox 呼び出しで属性を照合し、レコメンデーションを提供します。

   例えば、「最頻使用条件」レコメンデーションを作成できます。 返されたレコメンデーションのセットから、ユーザーがレコメンデーションが表示されるページにアクセスする際に渡された属性に対して、（リアルタイムで）レコメンデーションを除外できます。

* （コレクションを使用する代わりに）レコメンデーションに含める品目を制限するには、静的ルールを使用します。

* 動的インクルージョンルールは必要な数だけ作成できます。 インクルージョンルールは AND 演算子で結合します。品目がレコメンデーションに含まれるためには、すべてのルールを満たす必要があります。

動的フィルタリングには、次のオプションを使用できます。

| 動的フィルターオプション | 詳細 |
| --- | --- |
| [エンティティ属性のマッチング](/help/main/c-recommendations/c-algorithms/entity-attribute-matching.md) | 潜在的なレコメンデーション品目のプールと、ユーザーがやり取りした特定の品目を比較することで、動的にフィルタリングします。<br>用途 [!UICONTROL エンティティ属性のマッチング] 訪問者が最も好きなブランドなど、訪問者に最も訴えかける可能性が高いレコメンデーションを表示する場合に、このオプションを使用します。 |
| [プロファイル属性のマッチング](/help/main/c-recommendations/c-algorithms/profile-attribute-matching.md) | 品目（エンティティ）とユーザーのプロファイルの値を比較することで、動的にフィルタリングします。<br>用途 [!UICONTROL プロファイル属性のマッチング] サイズやお気に入りのブランドなど、訪問者のプロファイルに保存された値に一致するレコメンデーションを表示する場合に、 |
| [パラメーターのマッチング](/help/main/c-recommendations/c-algorithms/parameter-matching.md) | 品目（エンティティ）とリクエスト（API または mbox）の値を比較することで、動的にフィルタリングします。<br>用途 [!UICONTROL パラメーターのマッチング] をクリックして、ページパラメーターまたは訪問者のパラメーター（デバイスディメンションや地域など）に一致するコンテンツをレコメンデーションします。 |

### 値でフィルター

値によるフィルタリングには、次のオプションを使用できます。

| 「値によるフィルター」オプション | 詳細 |
| --- | --- |
| [静的フィルター](/help/main/c-recommendations/c-algorithms/static-value.md) | フィルタリングする 1 つ以上の静的値を手動で入力します。 |

## 使用可能な演算子 {#operators}

動的な条件とプロモーションは、静的な条件やプロモーションよりもはるかに強力で、より良い結果とエンゲージメントを生み出します。

以下の例は、マーケティング活動で動的なプロモーションと除外を使用する方法に関する一般的なアイデアを提供しています。

| 演算子 | 例 |
| --- | --- |
| 次と等しい<br>（エンティティ属性のマッチング、プロファイル属性のマッチング、パラメーターのマッチング、静的フィルターで使用できます）。 | 動的プロモーションで「次に等しい」演算子を使用すると、訪問者が Web サイトで品目（商品、記事、映画など）を閲覧しているときに、以下のような条件に該当する他の品目をプロモーションできます。<ul><li>同じブランド</li><li>同じカテゴリ</li><li>同じカテゴリ AND （自社ブランド）</li><li>同じ店</li></ul> |
| 次と等しくない<br>（エンティティ属性のマッチング、プロファイル属性のマッチング、パラメーターのマッチング、静的フィルターで使用できます）。 | 動的プロモーションで「等しくない」演算子を使用すると、訪問者が Web サイトで品目（商品、記事、映画など）を閲覧しているときに、以下のような条件に該当する他の品目をプロモーションできます。<ul><li>別のテレビシリーズ</li><li>異なるジャンル</li><li>別の製品シリーズ</li><li>別のスタイル ID</li></ul> |
| Does Not Contain Substring<br>（エンティティ属性のマッチング、プロファイル属性のマッチング、パラメーターのマッチング、静的フィルターで使用できます）。 | 訪問者が Web サイトで品目（製品など）を閲覧しているときに、「次の部分文字列を含まない」演算子を使用して、以下に示すその他の品目をプロモーションできます。<ul><li>敬称に敬称が含まれていません</li></ul> |
| 次で始まる<br>（エンティティ属性のマッチング、プロファイル属性のマッチング、パラメーターのマッチング、静的フィルターで使用できます）。 | 「次の語句で始まる」演算子を使用すると、訪問者が Web サイトで品目（製品など）を閲覧しているときに、以下に示すその他の品目をプロモーションできます。<ul><li>製品名がiPhoneで始まる</li></ul> |
| 次で終わる<br>（エンティティ属性のマッチング、プロファイル属性のマッチング、パラメーターのマッチング、静的フィルターで使用できます）。 | 「次の語句で終わる」演算子を使用すると、訪問者が Web サイトで品目（製品など）を閲覧しているときに、以下に示すその他の品目をプロモーションできます。<ul><li>コンテンツが EN で終わる（英語を示す）</li></ul> |
| Is Greater Than Or Equal To<br>（エンティティ属性のマッチング、プロファイル属性のマッチング、パラメーターのマッチング、静的フィルターで使用できます）。 | 「次よりも大きいか等しい」演算子を使用して、訪問者が Web サイトで品目（製品など）を閲覧している場合に、以下に示すその他の品目をプロモーションできます。<ul><li>コストが同じか、コストが高い</li></ul> |
| Is Less Than Or Equal To<br>（エンティティ属性のマッチング、プロファイル属性のマッチング、パラメーターのマッチング、静的フィルターで使用できます）。 | 「次よりも小さいか等しい」演算子を使用すると、訪問者が Web サイトで品目（製品など）を閲覧しているときに、以下に該当する他の品目をプロモーションできます。<ul><li>コストが同じか、コストが低い</li><li>コストの低い品目を除外</li></ul> |
| Is Between<br>（エンティティ属性のマッチング、プロファイル属性のマッチング、パラメーターのマッチングで使用できます）。 | 動的プロモーションで「範囲内」演算子を使用すると、訪問者が Web サイトで品目（商品、記事、映画など）を閲覧しているときに、以下のような他の品目をプロモーションできます。<ul><li>より高価</li><li>低コスト</li><li>コストプラスマイナス 30%</li><li>同シーズンの後のエピソード</li><li>シリーズの前の書籍</li></ul> |
| リストに含まれる<br>（プロファイル属性のマッチングとパラメーターのマッチングで使用できます） | プロファイル属性のマッチングで「is contained in list」演算子を使用すると、訪問者が Web サイトで品目（製品、記事、映画など）を閲覧しているときに、以下のような条件に該当する他の品目をプロモーションできます。<ul><li>訪問者の地域で使用できます</li></ul>**例**:訪問者の地域で利用可能な品目のみをレコメンデーションする必要がある場合。<br>フィルタールールは次のようになります。<br>`availableGeographies list contains an item in user.currentGeography`<br>**注意**:この演算子を使用する場合、 [右側](#caveats) ルールの |
| リストに含まれていません<br>（プロファイル属性のマッチングとパラメーターのマッチングで使用できます） | プロファイル属性のマッチングで「リストに含まれていない」演算子を使用すると、訪問者が Web サイトで品目（製品、記事、映画など）を閲覧しているときに、以下に示す他の品目を除外できます。<ul><li>訪問者が閲覧した直近 10 項目のリスト</li></ul></ul>**例**:訪問者が最近表示し、関心を示さなかった品目をプロモーションしたくない場合。<br>フィルタールールは次のようになります。<br>`id is not contained in list user.lastViewedItems`<br>**注意**:この演算子を使用する場合、 [右側](#caveats) ルールの |
| リストに次の項目が含まれています：<br>（エンティティ属性のマッチング、プロファイル属性のマッチング、パラメーターのマッチングで使用できます）。 | プロファイル属性のマッチングで「リストに含まれる項目」演算子を使用すると、訪問者が Web サイトで項目（スポーツイベントやコンサートなど）を閲覧しているときに、以下のような条件に該当する他の項目をプロモーションできます。<ul><li>訪問者のお気に入りのチームの 1 つに関連付け</li></ul>**例**:訪問者のお気に入りのチームの 1 つに関連付けられたゲームをレコメンデーションしたい場合。<br>フィルタールールは次のようになります。<br>` teamsPlaying list contains an item in user.favoriteTeams`<br>**注意**:この演算子を使用する場合、 [両側](#caveats) ルールの |
| リストに次の項目が含まれていません：<br>（エンティティ属性のマッチング、プロファイル属性のマッチング、パラメーターのマッチングで使用できます）。 | パラメーター属性のマッチングで、「リストに項目が含まれない」演算子を使用すると、訪問者が Web サイトで項目（製品、記事、映画など）を表示しているときに、以下に示す他の項目を除外できます。<ul><li>禁止されたタイプのリストに含まれます</li></ul>**例**:タバコやアルコールなど、大人の訪問者が利用できる品目を除外したい場合。<br>フィルタールールは次のようになります。<br>`itemType is not contained in list mbox.prohibitedTypes`<br>**注意**:この演算子を使用する場合、 [両側](#caveats) ルールの |
| リストに含まれる項目：<br>（エンティティ属性のマッチング、プロファイル属性のマッチング、パラメーターのマッチングで使用できます）。 | プロファイル属性マッチングで「リストに含まれるすべての項目」演算子を使用すると、訪問者が Web サイトで項目（ジョブの投稿やレシピなど）を表示しているときに、以下に示す他の項目をプロモーションできます。<ul><li>一連のスキルを含める</li><li>必要な材料のセットを含める</li></ul>**例 1**:訪問者に一連のスキル (Java、C++、HTML) があるとします。 カタログの項目は、必要なスキル (Java およびHTML) を持つジョブです。 訪問者にジョブをレコメンデーションする前に、訪問者のプロファイルに必要なすべてのスキルが含まれていることを確認する必要があります。<br>フィルタールールは次のようになります。<br>`profile.jobSeekerSkills contains all items in entity.requiredSkills`<br>**例 2**:ユーザーが食器用具のリストを持っているとします。 レシピには、必要な材料のリストが含まれています。 訪問者にレシピをレコメンデーションする前に、訪問者のプロファイルに必要なすべての成分が含まれていることを確認する必要がある場合。<br>フィルタールールは次のようになります。<br>`profile.ingredientsInPantry contains all items in recipe.ingredientsRequired`<br>**注意**:この演算子を使用する場合、 [両側](#caveats) ルールの |
| リストに含まれない項目：<br>（エンティティ属性のマッチング、プロファイル属性のマッチング、パラメーターのマッチングで使用できます）。 | エンティティ属性マッチングで「list does not contain all items in」演算子を使用すると、訪問者が Web サイトで品目（スポーツイベントやコンサートなど）を閲覧しているときに、以下に示すその他の品目をプロモーションできます。<ul><li>一連のチームを含めない</li></ul>**例**:スポーツイベントに 2 つのチームが含まれるとします。 訪問者のプロファイルは、この訪問者がこれらのチームのゲームを表示したくないことを示します。 これらのチームがプレイしている場合に、ゲームをレコメンデーションしないようにします。<br>フィルタールールは次のようになります。<br>`profile.leastfavoriteTeams does not contain all items in entity.teamsPlaying`<br>**注意**:この演算子を使用する場合、 [両側](#caveats) ルールの |

## エンティティ属性のマッチング、プロファイル属性のマッチング、パラメーターのマッチングでフィルタリングする際の空の値の処理 {#section_7D30E04116DB47BEA6FF840A3424A4C8}

フィルター処理で空の値を処理するには、いくつかのオプションを選択できます [!UICONTROL エンティティ属性のマッチング], [!UICONTROL プロファイル属性のマッチング]、および [!UICONTROL パラメーターのマッチング] を参照してください。

以前は、値が空の場合は何も結果が返されませんでした。次の図のように、「*x* が空の場合」ドロップダウンリストを使用することで、条件に空の値があった場合に実行する処理を選択できます。

![empty_value 画像](assets/empty_value.png)

処理を選択するには、歯車アイコン (![icon_gear 画像](assets/icon_gear.png)) をクリックして、目的のアクションを選択します。

| アクション | 利用できるマッチング | 詳細 |
|--- |--- |--- |
| [!UICONTROL このフィルタールールを無視] | [!UICONTROL プロファイル属性のマッチング] および [!UICONTROL パラメーターのマッチング] | このアクションは、 [!UICONTROL プロファイル属性のマッチング] および [!UICONTROL パラメーターのマッチング].<br>このオプションではルールを無視するよう指定します。例えば、3 つのフィルタールールがあり、3 つ目のルールでは何も値が返されなかった場合は、何も結果を返さないのではなく、値が空だった 3 つ目のルールのみを無視できます。 |
| [!UICONTROL この条件の結果を表示しない]<br>（条件のみ） | [!UICONTROL エンティティ属性のマッチング], [!UICONTROL プロファイル属性のマッチング]、および [!UICONTROL パラメーターのマッチング] | このアクションは、 [!UICONTROL エンティティ属性のマッチング].<br>このアクションは次のように実行されます [!DNL Target] は、このオプションが追加される前に空の値を処理しました。この条件の結果は表示されません。 |
| [!UICONTROL 項目をプロモートしない<br>（プロモーションのみ）] | [!UICONTROL エンティティ属性のマッチング], [!UICONTROL プロファイル属性のマッチング]、および [!UICONTROL パラメーターのマッチング] | このアクションは、 [!UICONTROL エンティティ属性のマッチング].<br>このアクションは次のように実行されます [!DNL Target] は、このオプションが追加される前に空の値を処理しました。この条件の結果は表示されません。 |
| [!UICONTROL 静的値を使用] | [!UICONTROL エンティティ属性のマッチング], [!UICONTROL プロファイル属性のマッチング]、および [!UICONTROL パラメーターのマッチング] | 値が空だった場合に静的値を使用するよう設定できます。 |

## 注意事項 {#caveats}

>[!IMPORTANT]
>
>データタイプが異なる属性に対して「次に等しい」および「等しくない」演算子を使用した動的な条件またはプロモーションでは、実行時に互換性がない可能性があります。用途 [!UICONTROL 値], [!UICONTROL 余白], [!UICONTROL 在庫]、および [!UICONTROL 環境] の値は、左側に事前定義済みの属性またはカスタム属性がある場合は、右側に賢明に表示されます。

![left_right 画像](assets/left_right.png)

以下の表に、効果的なルールと実行時に互換性のない可能性のあるルールを示します。

| 互換性のあるルール | 互換性のない可能性のあるルール |
|--- |--- |
| value - is between - 90% and 110% of current item&#39;s - salesValue | salesValue - is between - 90% and 110% of current item&#39;s - value |
| value - is between - 90% and 110% of current item&#39;s - value | clearancePrice - is between - 90% and 110% of current item&#39;s - margin |
| margin - is between - 90% and 110% of current item&#39;s - margin | storeInventory - equals - current item&#39;s - inventory |
| inventory - equals - current item&#39;s - inventory |  |
