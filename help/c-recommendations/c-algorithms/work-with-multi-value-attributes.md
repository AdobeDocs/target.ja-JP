---
keywords: multi-value;attributes;recommendations;multi value;multivalue;multi-value
description: 特殊な複数値演算子を使用したAdobe TargetRecommendationsの複数値フィールドの操作に関する情報です。
title: Adobe TargetRecommendationsでの複数値の属性の操作
feature: null
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 0%

---


# 複数値の属性の操作

場合によっては、複数値のフィールドを使用する必要があります。 次の例をご覧ください。

* ユーザに映画をオファーする。 映画には複数の俳優がいる。
* コンサートのチケットを売る。 所定のユーザーには、複数のお気に入りのバンドがあります。
* あなたは服を売る。 1枚のシャツには複数のサイズがあります。

これらのシナリオでのレコメンデーションを処理するには、複数値のデータをに渡し、特別な複数値の演算子 [!DNL Target Recommendations] を使用します。

複数値のデータ [!DNL Recommendations] を識別できるようにするには、次のコード例のようにJSON配列として送信する必要があります。

## JavaScriptで複数値のパラメーターを渡す

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

詳しくは、「 [カスタムエンティティ属性での複数値の属性の](/help/c-recommendations/c-products/custom-entity-attributes.md#section_80FEFE49E8AF415D99B739AA3CBA2A14) 実装 *」を参照してください*。

## 複数値のエンティティ属性をCSVファイルに渡す

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

エンティティの属性、プロファイルの属性またはmboxパラメーターが上記の形式に従って複数の値として指定されている場合、は、フィールドが複数の値であることを [!DNL Recommendations] 自動的に検出します。

複数値のエンティティ、プロファイル、mboxの属性で使用できる演算子は、次のとおりです。

* [!UICONTROL がリストに含まれている場合]
* [!UICONTROL がリストに含まれていない]

## インクルージョンルールでの複数値の属性の操作

>[!NOTE]
>
>複数値の属性に対する動的一致のサポートは、現在、単一の値の左側と複数値の右側を比較する際に、プロファイル属性の一致またはパラメーター(mbox)属性の一致ルールを使用する場合の条件でのみ利用できます。 複数値の属性は、現在、プロモーション、エンティティ属性の一致、またはインクルージョンルールの左側のリストではサポートされていません。


### 例：最近監視した項目の除外

ユーザーの最後の10本の視聴済みムービーがレコメンデーションされないようにする場合を考えてみます。 最初に、最近10回閲覧されたムービーをJSON配列 `user.lastWatchedMovies` として追跡するために呼び出されるプロファイルスクリプトを作成します。 次に、次のインクルージョンルールを使用して、項目を除外できます。

```
`Profile Attribute Matching`
`id - is not contained in list - user.lastWatchedMovies`
```

インクルージョンルールのJSON API表現：

```
{
    "attribute": "id",
    "operation": "isNotContainedInList",
    "source": {
        "name": " user.lastWatchedMovies",
        "type": "PROFILE"
    }
} 
```

### 例：ユーザーのお気に入りのレコメンデーション項目

例えば、演奏中のバンドがユーザーのお気に入りのバンドの1つである場合に限り、コンサートのチケットを勧めたいとします。 まず、という名前のプロファイル変数にユーザーのお気に入りの帯域が含まれてい `profile.favoriteBands` ることを確認します。 次に、コンサートでパフォーマンスを上げているアーティスト `entity.artistPerforming` を含む属性がカタログに含まれていることを確認します。 次のインクルージョンルールを使用できます。

```
`Profile Attribute Matching`
`artistPerforming - is contained in list - profile.favoriteBands`
```

インクルージョンルールのJSON API表現：

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

### 例：ユーザーのお気に入りから品目をレコメンデーションする条件のAPI作成

すべての条件と同様、複数値のフィルタリングルールを使用する条件は、AdobeI/O APIを介して作成できます。 エンティティ属性がmboxパラメーターリストーに含まれる条件を作成す `id` るためのAPI呼び出しの例を次に示 `favorites` します。

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

これは、ページ上のJavaScriptとペアになって、お気に入りのコンテンツが渡されます。

```
<!-- pass in the value of mbox parameter “favorites” as JSON array -->
<script type="text/javascript">
   mboxCreate('myMbox','entity.id=<key>','favorites=["a","b","c"]');
</script>
```
