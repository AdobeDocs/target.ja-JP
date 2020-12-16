---
keywords: entity;entity attributes;pass information to Recommendations;behavioral data;data counter;define relative URL;display inventory level;define price;define profit margin;custom attributes
description: エンティティ属性を使用して、商品やコンテンツの情報をAdobe TargetRecommendationsに渡します。
title: エンティティの属性
feature: entities
translation-type: tm+mt
source-git-commit: 6704ac2ec73361ad95e110e9182485537d0de642
workflow-type: tm+mt
source-wordcount: '1019'
ht-degree: 90%

---


# ![PREMIUM](/help/assets/premium.png) エンティティの属性{#entity-attributes}

エンティティ属性を使用して、製品やコンテンツの情報を[!DNL Adobe Target Recommendations]に渡します。

[!DNL Recommendations] は、アルゴリズム内で使用されている `productId` または `productPurchasedId`（コード内では `entity.id`）を送信します。

>[!NOTE]
>
>* `entity.id` は、注文確認ページに `productPurchasedId` 送信され、Adobe Analytics製品レポートで `productId` 使用されるものと一致する必要があります。
   >
   >
* 指定されたエンティティの属性値は、61 日後に期限切れになります。各エンティティの最新値がカタログの項目ごとに少なくとも月に一度 Target Recommendations に渡されるようにする必要があります。


大半の事前定義パラメーターでは、単数値のみを使用できるため、新しい値によって古い値が上書きされます。`categoryId` パラメーターは、その商品を含む各カテゴリ用の値のコンマ区切りリストを受け取ることができます。新しい `categoryId` の値は既存の値を上書きせず、代わりにエンティティ更新の際に追加されます（上限 250 文字）。

at.js 1を使用している場合、一般に、表示情報mboxは次の例のようになります。** xwith `mboxCreate`.

>[!NOTE]
>
>* at.js 2を使用している場合。*x*,  `mboxCreate` （次の例で使用されている）はサポートされなくなりました。at.js 2を使用して、商品やコンテンツの情報をRecommendationsに渡す。*x*、 [targetPageParamsを使用します](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md)。この例については、[Recommendations](/help/c-recommendations/plan-implement.md)の計画と実装を参照してください。

>



エンティティのパラメーター属性はすべて大文字と小文字が区別されます。

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

`entity.id` の値には、REST API 呼び出しで渡される際に URL エンコーディングが必要なスラッシュ、アンパサンド、疑問符、パーセント記号、カンマ、その他の句読点を含めることはできません。ハイフンとアンダースコアは使用できます。`entity.id` 値に無効な句読点を含めると、一部の [!DNL Recommendations] 機能が正常に動作しなくなることがあります。

例：`'entity.id=67833'`

### entity.name

単一値のみ。

商品がレコメンデーションされる際に Web サイトに表示される商品名。

例：`'entity.name=Giants& vs& Rockies& 5/12'`

### entity.categoryId

複数値（コンマ区切りリスト）をサポート。

現在のページのカテゴリです。これにより、サブセクションのさらにサブセクションのカーディガン（女性、女性:セーター, 女性:セーター:カーディガン）のように、複数のカテゴリを含めることができます。複数のカテゴリはコンマで区切ります。

`categoryId` は 250 文字に制限されます。

>[!NOTE]
>
>[!UICONTROL カテゴリ]ページでカテゴリに基づいてレコメンデーションを表示するには、1 つの `categoryId` のみ、特定のレコメンデーションの表示に使用される mbox に渡すことができます。`categoryId` の値は、[!UICONTROL 商品詳細]ページで渡される `entity.categoryId`の値と完全に一致する必要があります。

例：

* 商品詳細ページの例：女性、女性:セーター、女性:セーター:カーディガン
* カテゴリページ「セーター」の例：女性:セーター
* カテゴリページ「カーディガン」の例：女性:セーター:カーディガン

カテゴリベースのレコメンデーションの場合、コンマを使用してカテゴリ値を区切ります。コンマで区切られた値はカテゴリになります。また、別の区切り文字（コロン（:）など）を使用してカテゴリ値内のサブカテゴリを区切ることで、サブカテゴリを定義できます。

例えば、次のコードでは、Womens カテゴリがいくつかのサブカテゴリに区切られています。

```javascript
mboxCreate('mboxName', 'entity.id=343942-32', 'entity.categoryId= Womens, Womens:Outerwear, Womens:Outerwear:Jackets, Womens:Outerwear:Jackets:Parka, Womens:Outerwear:Jackets:Caban’, 'entity.thumbnailUrl=...', 'entity.message=...', );
```

mbox 配信の場合、最も長い属性名がキーに使用されます。同じ長さの場合、最後の属性が使用されます。この例では、カテゴリキーは、Womens:Outerwear:Jackets:Caban です。

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

「特価」や「クリアランス」など、レコメンデーションに表示する商品についてのメッセージです。メッセージは通常、商品名よりも長いものとなります。テンプレート内の商品とともに表示する追加情報の定義に使用します。。

例：`'entity.message=Family&nbsp;special'`

### entity.inventory

単一値のみ。整数値または long 値が必要です。

品目の在庫レベルを表示します。

例：`'entity.inventory=1'`

**空の在庫属性処理：**&#x200B;配信については、`entity.inventory` > 0 または `entity.inventory` = 0 に設定されたインクルージョンルール、収集ルール、または条件があり、商品の在庫が設定されていない場合、 [!DNL Target] はこれを TRUE と評価し、在庫が設定されていない商品を含めます。これはデフォルトでおこなわれるので、在庫が設定されていない商品が推奨の結果に表示されます。

同様に、`entity.inventory` = 0 で `entity.inventory` が設定されていないグローバル除外ルールがある場合は、[!DNL Target] はこのルールを TRUE と評価し、その商品を除外します。

**既知の問題：**&#x200B;在庫値の属性が設定されていない場合、製品検索に配信との整合性がありません。例えば、`entity.inventory` = 0 のルールの場合、製品検索は在庫値が設定されていない商品を表示しません。

### entity.value

単一値のみ。

品目の価格や価値を定義します。

例：`'entity.value=15.99'`

### entity.margin

単一値のみ。

その品目の利益幅またはその他の価値。

例：`'entity.margin=1.00'`

### entity.*custom*

複数値（JSON 配列）をサポートします。

品目について追加情報を提供するカスタム変数を最大 100 個まで定義できます。カスタム属性のそれぞれに対し、未使用の属性名を指定できます。例えば、`entity.genre` という名前のカスタム属性を作成して、書籍や映画を定義できます。または、チケット業者は、スポーツイベントでの来訪チームやコンサートの前座など、開催されるイベントの第 2 のパフォーマーに関する属性を作成することができます。

制限事項：

* 事前定義されたエンティティの属性名はカスタムエンティティの属性に使用できません。
* 属性 entity.environment はシステムによって予約されており、カスタムエンティティの属性には使用できません。targetPageParams、フィードまたは API を使用して、entity.environment を渡そうとする試みは無視されます。

例：

`'entity.venue=AT&T&nbsp;Park'`

`'entity.secondary=Rockies'`

カスタムエンティティの属性では、複数の値がサポートされます。文字および値の制限については、[カスタムエンティティの属性](/help/c-recommendations/c-products/custom-entity-attributes.md#limits)を参照してください。

例：`'entity.secondary=["band1",&nbsp;"band2"]'`

>[!NOTE]
>
>複数値のカスタムエンティティの属性には、有効な JSON 配列が必要です。正しい構文情報については、カスタムエンティティの属性を参照してください。

### entity.event.detailsOnly

単一値のみ。

mbox の呼び出しによって、アルゴリズムの行動データカウンターが増加することを回避するために使用します。

例：`'entity.event.detailsOnly=true'`

次の例では、最初の mbox 呼び出しによって、カタログと行動データが更新されます。2 回目の mbox 呼び出しでは、カタログのみが更新されます。

```javascript
mboxCreate('myMbox', 'profile.geo.city = new york', 'profile.geo.state = new york',  'entity.id = 'entity.inventory = 4' )
mboxCreate('myMbox',  'profile.geo.city = new york', 'profile.geo.state = new york',  'entity.id = 123', 'entity.inventory = 4' 'entity.event.detailsOnly=true' )
```

## 関連トピック：

* [カスタムエンティティの属性](/help/c-recommendations/c-products/custom-entity-attributes.md#concept_E5CF39BCAC8140309A73828706288322)
