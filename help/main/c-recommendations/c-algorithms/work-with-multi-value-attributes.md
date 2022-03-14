---
keywords: 複数値；属性；レコメンデーション；複数値；複数値；複数値
description: Adobeの複数値フィールドの操作方法を説明します [!DNL Target] Recommendationsでは、特別な複数値演算子を使用します。例えば、複数の俳優を含む映画をレコメンデーションする場合などです。
title: 複数値の属性をRecommendationsで使用できますか？
feature: Recommendations
exl-id: 82018a9a-0983-458c-9387-3602dab4409b
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 8%

---

# 複数値の属性の扱い

複数値のフィールドを使用する場合もあります。 次の例をご覧ください。

* ユーザに映画をオファーする場合。所定の映画には複数の俳優が出演しています。
* コンサートのチケットを販売する場合。所定のユーザーには、お気に入りのバンドが複数あります。
* 服を販売する場合。1 種類のシャツには複数のサイズがあります。

このような状況でレコメンデーションを処理するには、複数値のデータをに渡します [!DNL Target Recommendations] とは、特別な複数値演算子を使用することです。

許可する手順は次のとおりです。 [!DNL Recommendations] 複数値のデータを識別するには、次のコードサンプルのように JSON 配列として送信する必要があります。

## JavaScript での複数値パラメーターの渡し

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

詳しくは、 [複数値の属性の実装](/help/main/c-recommendations/c-products/custom-entity-attributes.md#section_80FEFE49E8AF415D99B739AA3CBA2A14) in *カスタムエンティティの属性*.

## 複数値のエンティティ属性を CSV ファイルに渡す

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

上記の形式に従って、エンティティ属性、プロファイル属性、または mbox パラメーターが複数値として指定される場合、 [!DNL Recommendations] は、フィールドが複数値であると自動的に解釈します。

複数値のエンティティ、プロファイルおよび mbox 属性で使用できる演算子は次のとおりです。

* [!UICONTROL はリストに含まれています]
* [!UICONTROL はリストに含まれていません]

## インクルージョンルールでの複数値の属性の使用

>[!NOTE]
>
>複数値の属性への動的一致のサポートは、現在、単一値の左辺と複数値の右辺を比較する際に、プロファイル属性の一致またはパラメーター (mbox) 属性の一致ルールを使用する条件でのみ使用できます。 複数値の属性は、現在、プロモーション、エンティティ属性のマッチング、インクルージョンルールの左側にあるリストではサポートされていません。

### 例：最近の監視項目を除外

ユーザーの最後の 10 本の視聴済みムービーに含まれるムービーがレコメンデーションされないようにするとします。 まず、という名前のプロファイルスクリプトを作成します。 `user.lastWatchedMovies` をクリックして、最後に 10 回視聴された映画を JSON 配列として追跡します。 次のインクルージョンルールを使用して、項目を除外できます。

```
`Profile Attribute Matching`
`id - is not contained in list - user.lastWatchedMovies`
```

インクルージョンルールの JSON API 表現：

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

### 例：ユーザーのお気に入りから品目をレコメンデーション

ユーザーの好きなバンドの 1 つである場合にのみ、コンサートのチケットをレコメンデーションしたいとします。 まず、という名前のプロファイル変数があることを確認します。 `profile.favoriteBands` ユーザーのお気に入りのバンドを含む 次に、カタログに属性が含まれていることを確認します `entity.artistPerforming` コンサートで演奏するアーティストを含む その後、次のインクルージョンルールを使用できます。

```
`Profile Attribute Matching`
`artistPerforming - is contained in list - profile.favoriteBands`
```

インクルージョンルールの JSON API 表現：

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

### 例：ユーザーのお気に入りから品目をレコメンデーションする条件の API 作成

すべての条件と同様に、複数値のフィルタールールを使用する条件は、Adobe I/OAPI を使用して作成できます。 エンティティ属性が指定された条件を作成するための API 呼び出しの例 `id` は mbox パラメーターリストに含まれています `favorites` 以下に示します。

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

これは、ページ上の JavaScript と対になり、お気に入りのコンテンツが渡されます。

```
<!-- pass in the value of mbox parameter “favorites” as JSON array -->
<script type="text/javascript">
   mboxCreate('myMbox','entity.id=<key>','favorites=["a","b","c"]');
</script>
```
