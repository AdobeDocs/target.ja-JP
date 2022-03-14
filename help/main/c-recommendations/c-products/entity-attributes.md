---
keywords: エンティティ;エンティティの属性;レコメンデーションへの情報の転送;行動データ, データカウンター;相対 URL の定義;在庫レベルの表示;価格の定義;利益幅の定義;カスタム属性
description: エンティティの属性を使用して製品やコンテンツの情報をに渡す方法を説明します。 [!DNL Target] Recommendations。
title: エンティティ属性の使用方法
feature: Recommendations
exl-id: 4ed5fad3-b8b6-4675-a741-9f85cf73fcf1
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1074'
ht-degree: 54%

---

# ![PREMIUM](/help/main/assets/premium.png) エンティティの属性

エンティティの属性を使用して、製品やコンテンツの情報をに渡します。 [!DNL Adobe Target Recommendations].

エンティティとは、レコメンデーションする項目を指します。エンティティには、製品、コンテンツ（記事、スライドショー、画像、映画、テレビ番組）、求人情報、レストランなどが含まれます。

[!DNL Recommendations] は、アルゴリズム内で使用されている `productId` または `productPurchasedId`（コード内では `entity.id`）を送信します。

次の点に留意してください。

* `entity.id` は、 `productPurchasedId` を注文確認ページに送信し、 `productId` 使用される [!DNL Adobe Analytics] 製品レポート。
* に渡すエンティティ属性値 [!DNL Recommendations] は 61 日後に期限切れになります。 Adobeでは、各エンティティ属性の最新の値をに渡すことをお勧めします。 [!DNL Recommendations] カタログの各項目に対して、少なくとも 1 ヶ月に 1 回

ほとんどの事前定義パラメーターでは、単一の値のみを受け取り、新しい値によって古い値が上書きされます。 `categoryId` パラメーターは、その商品を含む各カテゴリ用の値のコンマ区切りリストを受け取ることができます。新しい `categoryId` の値は既存の値を上書きせず、代わりにエンティティ更新の際に追加されます（上限 250 文字）。

一般に、表示情報 mbox は、at.js 1.*x* と `mboxCreate`. エンティティのパラメーター属性はすべて、大文字と小文字が区別されます。

>[!NOTE]
>
>at.js 2.*x*, `mboxCreate` （次の例で使用）はサポートされなくなりました。 製品またはコンテンツの情報をに渡すには [!DNL Recommendations] at.js 2.*x*，使用 [targetPageParams](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md). 例については、 [Recommendationsの計画と実装](/help/main/c-recommendations/plan-implement.md).

```javascript
<div class="mboxDefault"></div><script language="JavaScript1.2"> 
 
mboxCreate('productPage', 
 
'entity.id=67833', 
 
'entity.name=GIANTS VS ROCKIES 5/12', 
 
'entity.categoryId=BASEBALL, GIANTS, SF BAY AREA', 
 
'entity.pageUrl=/help/baseball/giants-tix/giantsvrockies5.12.2000-67833', 
 
'entity.venue=AT&T PARK', 
 
'entity.secondary=ROCKIES', 
 
'entity.thumbnailUrl=/help/baseball/giants-tix/giants-136px.gif', 
 
'entity.message=FAMILY SPECIAL', 
 
'entity.value=15.99', 
 
'entity.inventory=1' 
 
); 
 
</script>
```

>[!NOTE]
>
>Recommendations は、サイト上のすべての環境から送信されるデータを受信するので、`pageUrl` および `thumbnailUrl` には、絶対 URL ではなく相対 URL を指定することをお勧めします。相対 URL を使用すると、ステージングサーバーや開発サーバーへのハードコーディングされたリンクを回避できます。

mbox が商品ページにある場合、商品 ID とカテゴリ ID の両方を含めることができます。そのどちらが表示されるかは選択されているアルゴリズムで決定されます。商品 ID は親和性アルゴリズムで使用され、カテゴリ ID はカテゴリアルゴリズムで使用されます。

## 使用できる変数

次のリストで、使用できる変数について説明します。

### entity.id

単一値のみ。

この必須パラメーターで商品を識別します。様々な商品の品目を識別してそのデータを共有するために、この英数字 ID は、使用するすべての [!DNL Adobe Experience Cloud] 製品（[!DNL Analytics] を含む）で同じにする必要があります。

この `entity.id` 値は *not* には、REST API 呼び出しで渡される際に URL エンコーディングが必要なスラッシュ、アンパサンド、疑問符、パーセント記号、コンマ、その他の句読点が含まれます。 ハイフンとアンダースコアを使用できます。 `entity.id` 値に無効な句読点を含めると、一部の [!DNL Recommendations] 機能が正常に動作しなくなることがあります。

例：`'entity.id=67833'`

### entity.name

単一値のみ。

商品がレコメンデーションされる際に Web サイトに表示される商品名。

例：`'entity.name=Giants& vs& Rockies& 5/12'`

### entity.categoryId

複数値（コンマ区切りリスト）をサポート。

現在のページのカテゴリです。entity.categoryID には、サブセクションのカーディガン（女性、女性：セーター、女性など）のように、複数のカテゴリを含めることができます:sweaters:カーディガン )。 複数のカテゴリはコンマで区切る必要があります。

この `categoryId` の値は 250 文字に制限されます。

>[!NOTE]
>
>[!UICONTROL カテゴリ]ページでカテゴリに基づいてレコメンデーションを表示するには、1 つの `categoryId` のみ、特定のレコメンデーションの表示に使用される mbox に渡すことができます。`categoryId` の値は、[!UICONTROL 商品詳細]ページで渡される `entity.categoryId`の値と完全に一致する必要があります。

例：

* 製品の詳細ページの例：女性、女性：セーター、女性:sweaters:心臓
* カテゴリページ「セーター」の例：女性:セーター
* カテゴリページのカーディガンの例：女性:sweaters:心臓

カテゴリベースのレコメンデーションの場合、カテゴリ値はコンマで区切られます。 コンマで区切られた値はカテゴリになります。また、別の区切り文字（コロン（:）など）を使用してカテゴリ値内のサブカテゴリを区切ることで、サブカテゴリを定義できます。

例えば、次のコードでは、Women&#39;s カテゴリが複数のサブカテゴリに分割されています。

```javascript
mboxCreate('mboxName', 'entity.id=343942-32', 'entity.categoryId= Womens, Womens:Outerwear, Womens:Outerwear:Jackets, Womens:Outerwear:Jackets:Parka, Womens:Outerwear:Jackets:Caban’, 'entity.thumbnailUrl=...', 'entity.message=...', );
```

mbox 配信の場合、最も長い属性名がキーに使用されます。同じ長さの場合、最後の属性が使用されます。上記の例では、カテゴリキーは Womens です。:Outerwear:ジャケット：カバン。

### entity.brand

単一値のみ。

品目のブランド名を表示します。

例：`'entity.brand=brandxyz'`

### entity.pageUrl

単一値のみ。

その品目を購入できるページの相対 URL を定義します。

例：`'entity.pageUrl=baseball/giants-tix/giantsvrockies5.12.2000-67833'`

### entity.thumbnailUrl

単一値のみ。

品目と共に表示されるサムネールの相対 URL を定義します。

例：`'entity.thumbnailUrl=baseball/giants-tix/giants-136px.gif'`

### entity.message

単一値のみ。

「特価」や「クリアランス」など、レコメンデーションに表示する商品についてのメッセージです。メッセージは通常、商品名よりも長いものとなります。entity.message を使用して、テンプレートで製品と共に表示する追加情報を定義します。

例：`'entity.message=Family&nbsp;special'`

### entity.inventory

単一値のみ。整数値または long 値が必要です。

品目の在庫レベルを表示します。

例：`'entity.inventory=1'`

**空の在庫属性の処理：** 配信の場合、 `entity.inventory` > 0 または `entity.inventory` = 0 で、製品の在庫が設定されていない場合 [!DNL Target] は、この値を TRUE に評価し、在庫が設定されていない製品を含めます。 その結果、在庫が設定されていない商品がレコメンデーションの結果に表示されます。

同様に、`entity.inventory` = 0 で `entity.inventory` が設定されていないグローバル除外ルールがある場合は、[!DNL Target] はこのルールを TRUE と評価し、その商品を除外します。

**既知の問題：** 製品検索は、設定されていない在庫値属性の配信と一致しません。 例えば、 `entity.inventory` = 0 の場合、製品検索では、在庫値が設定されていない製品は表示されません。

### entity.value

単一値のみ。

品目の価格や価値を定義します。

例：`'entity.value=15.99'`

entity.value は、10 進数形式（例：15.99）のみをサポートします。 コンマフォーマット (15,99) はサポートされていません。

### entity.margin

単一値のみ。

その品目の利益幅またはその他の価値。

例：`'entity.margin=1.00'`

### entity.*custom*

複数値（JSON 配列）をサポートします。

品目について追加情報を提供するカスタム変数を最大 100 個まで定義できます。カスタム属性のそれぞれに対し、未使用の属性名を指定できます。例えば、 `entity.genre` ：本または映画を定義します。 チケット業者は、スポーツイベントでの来訪チームやコンサートの前座など、イベントの第 2 のパフォーマーに関する属性を作成できます。

制限事項：

* 事前定義されたエンティティの属性名はカスタムエンティティの属性に使用できません。
* 属性 entity.environment はシステムによって予約されており、カスタムエンティティの属性には使用できません。targetPageParams、フィードまたは API を使用して entity.environment を渡そうとしても無視されます。

例：

`'entity.venue=AT&T&nbsp;Park'`

`'entity.secondary=Rockies'`

カスタムエンティティの属性では、複数の値がサポートされます。文字および値の制限については、[カスタムエンティティの属性](/help/main/c-recommendations/c-products/custom-entity-attributes.md#limits)を参照してください。

例：`'entity.secondary=["band1",&nbsp;"band2"]'`

複数値のカスタムエンティティの属性には、有効な JSON 配列が必要です。正しい構文情報については、 [カスタムエンティティの属性](/help/main/c-recommendations/c-products/custom-entity-attributes.md).

### entity.event.detailsOnly

単一値のみ。

mbox の呼び出しによって、アルゴリズムの行動データカウンターが増加することを回避するために使用します。

例：`'entity.event.detailsOnly=true'`

以下の例では、最初の mbox 呼び出しによってカタログと行動データが更新されます。 2 番目の mbox 呼び出しは、カタログのみを更新します。

```javascript
mboxCreate('myMbox', 'profile.geo.city = new york', 'profile.geo.state = new york',  'entity.id = 'entity.inventory = 4' )
mboxCreate('myMbox',  'profile.geo.city = new york', 'profile.geo.state = new york',  'entity.id = 123', 'entity.inventory = 4' 'entity.event.detailsOnly=true' )
```

>[!MORELIKETHIS]
>
>* [カスタムエンティティの属性](/help/main/c-recommendations/c-products/custom-entity-attributes.md#concept_E5CF39BCAC8140309A73828706288322)

