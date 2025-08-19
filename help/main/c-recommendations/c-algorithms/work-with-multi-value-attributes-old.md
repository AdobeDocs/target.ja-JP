---
keywords: 複数値；属性；レコメンデーション；複数値；複数値；複数値
description: Adobe [!DNL Target] Recommendations で、特別な複数値演算子を使用して複数値フィールドを操作する方法を説明します。例えば、複数のアクターを持つムービーをレコメンデーションする場合などです。
title: レコメンデーションで複数値の属性を使用できますか？
feature: Recommendations
exl-id: 82018a9a-0983-458c-9387-3602dab4409b
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 9%

---

# 複数値の属性の扱い

複数値のフィールドでの作業が必要となることがあります。 次の例をご覧ください。

* ユーザに映画をオファーする場合。所定の映画には複数の俳優が出演しています。
* コンサートのチケットを販売する場合。所定のユーザーには、お気に入りのバンドが複数あります。
* 服を販売する場合。1 種類のシャツには複数のサイズがあります。

これらのシナリオでの推奨事項を処理するには、複数値のデータを [!DNL Target Recommendations] に渡し、特別な複数値演算子を使用します。

複数値データを識別で [!DNL Recommendations] るようにするには、以下のコードサンプルに示すように、JSON 配列として送信する必要があります。

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

詳しくは、[ カスタムエンティティ属性 ](/help/main/c-recommendations/c-products/custom-entity-attributes.md#section_80FEFE49E8AF415D99B739AA3CBA2A14) の *複数値の属性の実装* を参照してください。

## CSV ファイルで複数値エンティティ属性を渡す

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

上記の形式でエンティティ属性、プロファイル属性または mbox パラメーターが複数値として指定されている場合、[!DNL Recommendations] はフィールドが複数値であると自動的に推測します。

次の演算子を複数値のエンティティ、プロファイルおよび mbox 属性で使用できます。

* [!UICONTROL is contained in list]
* [!UICONTROL is not contained in list]

## インクルージョンルールでの複数値の属性の使用

>[!NOTE]
>
>複数値の属性に対する動的な一致は、現在、単一の値の左側と複数値の右側を比較する際に、プロファイル属性の一致またはパラメーター（mbox）属性の一致ルールを使用する場合の条件でのみサポートされています。 複数値の属性は、現在、プロモーション、エンティティ属性のマッチング、包含ルールの左側のリストではサポートされていません。

### 例：最近監視した項目を除外する

例えば、ユーザーが最後に視聴した 10 本のムービーに含まれるムービーをレコメンデーションできないようにするとします。 まず、「`user.lastWatchedMovies`」という名前のプロファイルスクリプトを作成して、最後に閲覧された 10 本のムービーを JSON 配列として追跡します。 次に、以下のインクルージョンルールを使用して項目を除外できます。

```
`Profile Attribute Matching`
`id - is not contained in list - user.lastWatchedMovies`
```

包含ルールの JSON API 表現：

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

### 例：ユーザーのお気に入りから項目をレコメンデーションする

演奏しているバンドがユーザーのお気に入りのバンドの 1 つである場合に、コンサートにのみチケットをレコメンデーションするとします。 まず、ユーザーのお気に入りのバンドを含んだ `profile.favoriteBands` というプロファイル変数があることを確認します。 次に、コンサートで演奏しているアーティストを含む属性 `entity.artistPerforming` がカタログに含まれていることを確認します。 次に、以下のインクルージョンルールを使用できます。

```
`Profile Attribute Matching`
`artistPerforming - is contained in list - profile.favoriteBands`
```

包含ルールの JSON API 表現：

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

### 例：ユーザーのお気に入りから項目を推奨する条件の API 作成

複数値のフィルタリングルールを使用した条件（すべての条件と同様）は、Adobe I/O API を使用して作成できます。 エンティティ属性 `id` が mbox パラメーターリスト `favorites` に含まれている条件を作成するための API 呼び出しの例を以下に示します。

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

これはページ上のJavaScriptとペアになり、お気に入りのコンテンツを渡します。

```
<!-- pass in the value of mbox parameter “favorites” as JSON array -->
<script type="text/javascript">
   mboxCreate('myMbox','entity.id=<key>','favorites=["a","b","c"]');
</script>
```
