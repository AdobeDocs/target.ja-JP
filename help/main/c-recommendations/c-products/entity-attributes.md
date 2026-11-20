---
keywords: エンティティ;エンティティの属性;レコメンデーションへの情報の転送;行動データ, データカウンター;相対 URL の定義;在庫レベルの表示;価格の定義;利益幅の定義;カスタム属性
description: エンティティ属性を使用して、商品またはコンテンツ情報を[!DNL Target]件の推奨事項に渡す方法を説明します。
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
title: エンティティ属性の使用方法
feature: Recommendations
exl-id: 4ed5fad3-b8b6-4675-a741-9f85cf73fcf1
TQID: 'https://experienceleague.adobe.com/GXQOxQxTV0vTYsWy9Ky9wPNEqoRSAhIA5zlBd4Cr4Ec'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
    internal-label: at.js
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
    internal-label: Behavioral data
source-git-commit: 5ed511322cc9f04c349471f8ad84a17526d4925f
workflow-type: tm+mt
source-wordcount: '1173'
ht-degree: 61%
---
# エンティティの属性 {#entity-attributes}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、どのエンティティ属性が製品またはコンテンツの情報を[!DNL Adobe Target Recommendations]に渡すか、および各属性の定義方法について説明します。

>[!ENDSHADEBOX]

エンティティ属性を使用して、製品またはコンテンツの情報を[!DNL Adobe Target Recommendations]に渡します。この情報はデザインに表示され、包含ルール、コレクション、除外で使用できます。 エンティティは、製品、コンテンツ（記事、スライドショー、画像、映画、テレビ番組）、求人、レストランなど、おすすめのアイテムです。 [!DNL Recommendations] は、アルゴリズムで使用される `productId` または `productPurchasedId`（コードでは `entity.id` と呼ばれる）を送信します。

次の点に留意してください。

* `entity.id` は、注文確認ページに送信される `productPurchasedId` および [!DNL Adobe Analytics] 製品レポートで使用される `productId` と一致する必要があります。
* [!DNL Recommendations] に渡すエンティティ属性値は、61 日後に期限切れになります。 アドビでは、カタログ内の各項目について、各エンティティ属性の最新の値を月に 1 回以上 [!DNL Recommendations] に渡すことをお勧めします。

ほとんどの定義済みパラメーターでは単一の値のみを受け取り、新しい値により古い値が上書きされます。 `categoryId` パラメーターは例外です（[entity.categoryId](#entity-category-id)を参照）。

一般に、at.js 1.*x* を `mboxCreate` と使用している場合、表示情報 mbox は次の例のようになります。 エンティティのパラメーター属性はすべて大文字と小文字を区別します。

at.js 2.*x* を使用している場合、`mboxCreate`（次の例で使用）はサポートされなくなりました。 at.js 2.*x* を使用して [!DNL Recommendations] に製品情報またはコンテンツ情報を渡すには、[targetPageParams](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/targetpageparams.html?lang=ja){target=_blank} を使用します。 例について詳しくは、[Recommendations の計画と実装](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html?lang=ja){target=_blank}を参照してください。

+++ エンティティ属性を渡すmboxの例

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

+++

>[!NOTE]
>
>レコメンデーションは、サイト上のすべての環境から送信されるデータを受信するので、`pageUrl` および `thumbnailUrl` には、絶対 URL ではなく相対 URL を指定することをお勧めします。 相対 URL を使用すると、ステージングサーバーや開発サーバーへのハードコーディングされたリンクを回避できます。

mbox が製品ページにある場合は、製品 ID とカテゴリ ID の両方を含めることができます。 そのどちらが表示されるかは選択されているアルゴリズムで決定されます。 商品 ID は親和性アルゴリズムで使用され、カテゴリ ID はカテゴリアルゴリズムで使用されます。

## 使用できる変数

次の表に、使用可能な変数を示します。 テーブルの後のサブセクションには、それを必要とする変数に関する詳細な情報が表示されます。

| 変数 | 値 | 説明 | 例 |
|---|---|---|---|
| `entity.id` | 単一の値のみ。 必須。 | 製品の識別： [entity.id](#entity-id)を参照してください。 | `'entity.id=67833'` |
| `entity.name` | 単一の値のみ。 | 製品が推奨される際にweb サイトに表示される製品名。 | `'entity.name=Giants& vs& Rockies& 5/12'` |
| `entity.categoryId` | 複数値（コンマ区切りリスト）。 | 現在のページのカテゴリ。 [entity.categoryId](#entity-category-id)を参照してください。 | `'entity.categoryId=womens:sweaters'` |
| `entity.brand` | 単一の値のみ。 | 品目のブランド名を表示します。 | `'entity.brand=brandxyz'` |
| `entity.pageUrl` | 単一の値のみ。 | その品目を購入できるページの相対 URL を定義します。 | `'entity.pageUrl=baseball/giants-tix/giantsvrockies5.12.2000-67833'` |
| `entity.thumbnailUrl` | 単一の値のみ。 | 品目と共に表示されるサムネールの相対 URL を定義します。 | `'entity.thumbnailUrl=baseball/giants-tix/giants-136px.gif'` |
| `entity.message` | 単一の値のみ。 | 「特価」や「クリアランス」など、レコメンデーションに表示する商品についてのメッセージです。 メッセージは通常、商品名よりも長いものとなります。 `entity.message`を使用して、テンプレート内の製品と共に表示する追加情報を定義します。 | `'entity.message=Family&nbsp;special'` |
| `entity.inventory` | 単一の値のみ。 整数値または long 値が必要です。 | 品目の在庫レベルを表示します。 [entity.inventory](#entity-inventory)を参照してください。 | `'entity.inventory=1'` |
| `entity.value` | 単一の値のみ。 | 品目の価格や価値を定義します。 10進数形式（例：15.99）のみがサポートされます。 コンマ形式（15,99）はサポートされていません。 | `'entity.value=15.99'` |
| `entity.margin` | 単一の値のみ。 | その品目の利益幅またはその他の価値。 | `'entity.margin=1.00'` |
| `entity.`*custom* | 複数値（JSON配列）。 | 項目に関する追加情報を提供するカスタム変数。 [&#x200B; エンティティを参照してください。*カスタム*](#entity-custom)。 | `'entity.secondary=Rockies'` |
| `entity.event.detailsOnly` | 単一の値のみ。 | mbox呼び出しがアルゴリズムの行動データカウンターを増分するのを防ぎます。 [entity.event.detailsOnly](#entity-event-details-only)を参照してください。 | `'entity.event.detailsOnly=true'` |

### entity.id {#entity-id}

英数字IDは、様々な製品がアイテムを認識し、それに関するデータを共有するために、[!DNL Analytics]を含め、使用されているすべての[!DNL Adobe Experience Cloud]製品で同じである必要があります。

`entity.id` の値には、スペース、スラッシュ、アンパサンド、疑問符、パーセント記号、コンマまたは REST API 呼び出しで渡される際に URL エンコーディングが必要となるその他の句読点文字を含めることはでき&#x200B;*ません*。 ハイフンとアンダースコアは許可されています。 `entity.id` 値に無効な句読点を含めると、一部の [!DNL Recommendations] 機能が正常に動作しなくなることがあります。

### entity.categoryId {#entity-category-id}

`entity.categoryId`の値には、カーディガン サブセクションなど、複数のカテゴリを含めることができます（例：`womens`、`womens:sweaters`、`womens:sweaters:cardigans`）。 複数のカテゴリはコンマで区切る必要があります。 新しい`categoryId`値は既存の値を上書きせず、エンティティの更新中に追加されます。 `categoryId` の値は 250 文字に制限されています。

>[!NOTE]
>
>**[!UICONTROL カテゴリ]** ページのカテゴリに基づいたレコメンデーションを表示するには、特定のレコメンデーションの表示に使用するmboxに渡すことができる`categoryId`は1つだけです。 `categoryId`の値は、**[!UICONTROL 製品の詳細]** ページで渡された`entity.categoryId`の値と完全に一致する必要があります。

例：

* Product Detail ページの例：`womens`、`womens:sweaters`、`womens:sweaters:cardigans`
* カテゴリページ「セーター」の例：`womens:sweaters`
* カテゴリページ「カーディガン」の例：`womens:sweaters:cardigans`

カテゴリベースのレコメンデーションの場合、カテゴリ値はコンマで区切られます。 コンマで区切られた値はカテゴリになります。 また、別の区切り文字（コロン（:）など）を使用してカテゴリ値内のサブカテゴリを区切ることで、サブカテゴリを定義できます。

例えば、次のコードでは、Women&#39;s カテゴリが複数のサブカテゴリに分割されています。

```javascript
mboxCreate('mboxName', 'entity.id=343942-32', 'entity.categoryId= Womens, Womens:Outerwear, Womens:Outerwear:Jackets, Womens:Outerwear:Jackets:Parka, Womens:Outerwear:Jackets:Caban', 'entity.thumbnailUrl=...', 'entity.message=...');
```

mbox 配信の場合、最も長い属性名がキーに使用されます。 同じ長さの場合、最後の属性が使用されます。 上記の例では、カテゴリキーは `Womens:Outerwear:Jackets:Caban` です。

### entity.inventory {#entity-inventory}

**空の在庫属性処理：**&#x200B;配送の場合、`entity.inventory` > 0または`entity.inventory` = 0で包含ルール、コレクション ルール、または条件設定があり、製品に在庫が設定されていない場合、[!DNL Target]はこの値をTRUEと評価し、在庫が設定されていない製品を含めます。 その結果、在庫が設定されていない製品がレコメンデーション結果に表示されます。

同様に、`entity.inventory` = 0 で `entity.inventory` が設定されていないグローバル除外ルールがある場合は、[!DNL Target] はこのルールを TRUE と評価し、その商品を除外します。

>[!NOTE]
>
>**既知の問題：**&#x200B;在庫値の属性が設定されていない場合、製品検索に配送との一貫性がありません。 例えば、`entity.inventory` = 0のルールの場合、在庫値が設定されていない商品は商品検索に表示されません。

### entity.*custom* {#entity-custom}

最大100個のカスタム変数を定義できます。 カスタム属性のそれぞれに対し、未使用の属性名を指定できます。 例えば、書籍や映画を定義するために、`entity.genre` というカスタム属性を作成できます。 チケットベンダーは、スポーツイベントの来訪チームやコンサートの前座など、2 次的な出演者向けにイベント会場の属性を作成できます。

制限事項：

* 事前定義されたエンティティの属性名はカスタムエンティティの属性に使用できません。
* 属性 `entity.environment` はシステムによって予約されており、カスタムエンティティの属性には使用できません。 `targetPageParams`、フィード、またはAPIを使用して`entity.environment`を渡そうとしても、無視されます。

例：

`'entity.venue=AT&T&nbsp;Park'`

`'entity.secondary=Rockies'`

カスタムエンティティの属性では、複数の値がサポートされます。 文字および値の制限については、[カスタムエンティティの属性](/help/main/c-recommendations/c-products/custom-entity-attributes.md#limits)を参照してください。

例：`'entity.secondary=["band1",&nbsp;"band2"]'`

複数値のカスタムエンティティの属性には、有効な JSON 配列が必要です。 正しい構文情報については、[&#x200B; カスタムエンティティ属性](/help/main/c-recommendations/c-products/custom-entity-attributes.md)を参照してください。

### entity.event.detailsOnly {#entity-event-details-only}

このパラメーターを使用すると、mbox呼び出しがアルゴリズムの行動データカウンターを増やさないようにすることができます。

次の例では、最初のmbox呼び出しはカタログと行動データを更新します。 2 回目の mbox 呼び出しでは、カタログのみが更新されます。

```javascript
mboxCreate('myMbox', 'profile.geo.city = new york', 'profile.geo.state = new york', 'entity.id = 123', 'entity.inventory = 4' )
mboxCreate('myMbox', 'profile.geo.city = new york', 'profile.geo.state = new york', 'entity.id = 123', 'entity.inventory = 4', 'entity.event.detailsOnly=true' )
```
