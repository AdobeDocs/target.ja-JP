---
keywords: 複数値；属性；レコメンデーション；複数値；複数値；複数値
description: Adobeの複数値フィールドを使用する方法を説明します [!DNL Target] 複数のアクターを含むムービーをレコメンデーションする場合など、特殊な複数値オペレーターを使用したレコメンデーション。
title: レコメンデーションで複数値の属性を使用できますか？
feature: Recommendations
exl-id: 82018a9a-0983-458c-9387-3602dab4409b
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 8%

---

# 複数値の属性の扱い

複数の値を持つフィールドを操作したい場合もあります。 次の例をご覧ください。

* ユーザに映画をオファーする場合。 所定の映画には複数の俳優が出演しています。
* コンサートのチケットを販売する場合。 所定のユーザーには、お気に入りのバンドが複数あります。
* 服を販売する場合。 1 種類のシャツには複数のサイズがあります。

これらのシナリオでレコメンデーションを処理するには、複数値データを[!DNL Target Recommendations]に渡し、特殊な複数値の演算子を使用します。

[!DNL Recommendations]が複数の値のデータを識別できるようにするには、次のコードサンプルのように、JSON配列として送信する必要があります。

## JavaScriptで複数値パラメーターを渡す

```
function targetPageParams() { 
  return { 
    'entity.id':                   '123', 
    'entity.categoryId':            '["A", "A:B", "A:B:C", "A:B:C:D"]',        
    'entity.MultiValueAttribute':   '["X", "Y", "Z"]', 
    'entity.event.detailsOnly':     'true', 
    'excludedIds":                  '[123, 3232, 2323, 4344]', 
    'orderId":                      '123456', 
    'orderTotal":                   '195.32', 
    'productPurchaseId":            '[001,002,003]' 
  }; 
}
```

詳しくは、*カスタムエンティティ属性*&#x200B;の[複数値の属性の実装](/help/main/c-recommendations/c-products/custom-entity-attributes.md#section_80FEFE49E8AF415D99B739AA3CBA2A14)を参照してください。

## 複数の値を持つエンティティ属性をCSV ファイルに渡す

```
## RECSRecommendations Upload File,,,,,,,,,,,,,,,,,,,
## RECS''## RECS'' indicates a Recommendations pre-process header. Please do not remove these lines.,,,,,,,,,,,,,,,,,,,
## RECS,,,,,,,,,,,,,,,,,,,
## RECSUse this file to upload product display information to Recommendations. Each product has its own row. Each line must contain 19 values and if not all are filled a space should be left.,,,,,,,,,,,,,,,,,,,
## RECSThe last 100 columns (entity.custom1 - entity.custom100) are custom. The name 'customN' can be replaced with a custom name such as 'onSale' or 'brand'.,,,,,,,,,,,,,,,,,,,
## RECSIf the products already exist in Recommendations then changes uploaded here will override the data in Recommendations. Any new attributes entered here will be added to the product''s entry in Recommendations.,,,,,,,,,,,,,,,,,,,
## RECSentity.id ,entity.name,entity. categoryId ,entity. message ,entity.thumbnailUrl ,entity.value ,entity.pageUrl ,entity.inventory ,entity.margin ,entity.custom1 ,entity.custom2 ,entity.custom3 ,entity.custom4,entity.custom5,entity.custom6,entity.custom7,entity.custom8,entity.custom9,entity.custom10,
1,Sample Product 1,category1,Save 10%,http://sample.store/products/images/product1_th.jpg,325,http://sample.store/products/product_detail.jsp?productId=1,1000,48,a,"[ ""v1"", ""v2"" ]",, , , , , , , ,
2,Sample Product 2,category1,Save 10%,http://sample.store/products/images/product2_th.jpg,369,http://sample.store/products/product_detail.jsp?productId=2,1000,52,a,"[ ""v1"", ""v2"" ]",, , , , , , , ,
3,Sample Product 3,category1,Save 10%,http://sample.store/products/images/product3_th.jpg,479,http://sample.store/products/product_detail.jsp?productId=3,1000,78,a,"[ ""v1"", ""v2"" ]",,,,,,,,,
4,Sample Product 4,category1,Save 10%,http://sample.store/products/images/product4_th.jpg,409,http://sample.store/products/product_detail.jsp?productId=4,1000,66,a,"[ ""v1"", ""v2"" ]",,,,,,,,,
5,Sample Product 5,category1,Save 10%,http://sample.store/products/images/product5_th.jpg,325,http://sample.store/products/product_detail.jsp?productId=5,1000,45,a,"[ ""v1"", ""v2"" ]",,,,,,,,, 
```

エンティティ属性、プロファイル属性、またはmbox パラメーターが上記の形式に従って複数値として指定されると、[!DNL Recommendations]はフィールドが複数値であると自動的に推測します。

複数値のエンティティ、プロファイルおよびmbox属性で使用できる演算子は次のとおりです。

* [!UICONTROL is contained in list]
* [!UICONTROL is not contained in list]

## 包含ルールでの複数値の属性の操作

>[!NOTE]
>
>複数の値の属性に対する動的マッチングのサポートは、現在、単一の値を左側から右側に複数値で比較する際に、プロファイル属性マッチングまたはパラメーター（mbox）属性マッチングルールを使用する場合にのみ、条件でのみ利用できます。 複数値の属性は、現在、プロモーション、エンティティ属性の一致、または包含ルールの左側のリストではサポートされていません。

### 例：最近視聴した項目を除外

例えば、ユーザーの最後の10本のムービーの中にあるムービーが推奨されないようにするとします。 まず、`user.lastWatchedMovies`というプロファイルスクリプトを作成して、最後に閲覧した10本のムービーをJSON配列として追跡します。 次に、次の包含ルールを使用して、項目を除外できます。

```
`Profile Attribute Matching`
`id - is not contained in list - user.lastWatchedMovies`
```

包含ルールのJSON API表現：

```
{
    "attribute": "id",
    "operation": "isNotContainedInList",
    "source": {
        "name": "user.lastWatchedMovies",
        "type": "PROFILE"
    }
} 
```

### 例：ユーザーのお気に入りから商品をレコメンドする

バンドの再生がユーザーのお気に入りのバンドの1つである場合、コンサートのチケットのみを推奨するとします。 まず、ユーザーのお気に入りのバンドを含む`profile.favoriteBands`というプロファイル変数があることを確認します。 次に、カタログに、コンサートでパフォーマンスするアーティストを含む属性`entity.artistPerforming`が含まれていることを確認します。 次に、次の包含ルールを使用できます。

```
`Profile Attribute Matching`
`artistPerforming - is contained in list - profile.favoriteBands`
```

包含ルールのJSON API表現：

```
{
    "attribute": "artistPerforming",
    "operation": "isContainedInList",
    "source": {
        "name": "profile.favoriteBands",
        "type": "PROFILE"
    }
}
```

### 例：ユーザーのお気に入りからの項目を推奨する基準のAPI作成

あらゆる基準と同様に、複数値のフィルタリングルールを使用する基準は、Adobe I/O APIを介して作成できます。 エンティティ属性`id`がmbox パラメーターリスト `favorites`に含まれる条件を作成するためのAPI呼び出しの例は、次のとおりです。

```
curl -X POST \
  https://<serverhost>/api/recs/<client>/criteria/item \
  -H 'Accept: application/vnd.adobe.target.v1+json' \
  -H 'Accept-Encoding: gzip, deflate' \
  -H 'Cache-Control: no-cache' \
  -H 'Connection: keep-alive' \
  -H 'Content-Type: application/json' \
  -H 'User-Agent: <from API client>' \
  -H 'X-Target-user-email: <email address>' \
  -H 'cache-control: no-cache' \
  -d '{
    "name": "viewed criteria",
    "criteriaTitle": "test title",
    "type": "VIEWED_CF",
    "key": "CURRENT",
    "daysCount": "TWO_WEEKS",
    "aggregation": "NONE",
    "backupDisabled": false,
    "partialDesignAllowed": true,
    "configuration": {
        "inclusionRules": [
            {
                "attribute": "id",
                "operation": "isContainedInList",
                "source": {
                    "name": "mbox.favorites",
                    "type": "MBOX"
                }
            }
        ]
    }
}'
```

これは、お気に入りのコンテンツを渡すために、ページ上のJavaScriptと組み合わせられます。

```
<!-- pass in the value of mbox parameter “favorites” as JSON array -->
<script type="text/javascript">
   mboxCreate('myMbox','entity.id=<key>','favorites=["a","b","c"]');
</script>
```
