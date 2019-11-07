---
keywords: 複数値；属性；レコメンデーション；複数値；複数値
description: 特別な複数値演算子を使用したAdobe Target Recommendationsでの複数値フィールドの操作に関する情報です。
title: Adobe Target Recommendationsでの複数値の属性の操作
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# 複数値の属性の操作

複数の値を持つフィールドを使用する場合もあります。 次の例をご覧ください。

* ユーザに映画を提供する。 ある映画には複数の俳優がいる。
* コンサートのチケットを売る。 特定のユーザーには、複数のお気に入りのバンドがあります。
* あなたは服を売る。 1枚のシャツは複数のサイズで購入できます。

これらのシナリオでのレコメンデーションを処理するには、複数値データをに渡し、特 [!DNL Target Recommendations] 別な複数値演算子を使用します。

複数の値 [!DNL Recommendations] を持つデータを識別できるようにするには、以下のコード例のように、JSON配列として送信する必要があります。

## JavaScriptでの複数値のmboxパラメーターの渡し

```
 <!-- pass in the value of mbox parameter “favName” as JSON array -->
<script type="text/javascript">
   mboxCreate('myMbox','entity.id=<key>','favName=["a","b","c"]');
</script>
```

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

エンティティの属性、プロファイル属性またはmboxパラメーターが上記の形式に従って複数の値として指定されている場合、フィールドが複 [!DNL Recommendations] 数の値であることが自動的に推定されます。

複数値のエンティティ、プロファイルおよびmbox属性で使用できる演算子は次のとおりです。

* [!UICONTROL リストに含まれる]
* [!UICONTROL リストに含まれない]

## インクルージョンルールでの複数値の属性の操作

>[!NOTE]
>
>複数値の属性への動的一致のサポートは、現在、単一の値の左辺と複数値の右辺を比較する際に、プロファイル属性の一致またはパラメーター(mbox)属性の一致ルールを使用する場合にのみ利用できます。 プロモーション、エンティティ属性の一致、およびインクルージョンルールの左側のリストのサポートは、2020年の初めに提供されます。


### 例：最近の監視アイテムの除外

ユーザーの最後の10本の視聴済みムービーがレコメンデーションされないようにする場合を考えてみます。 最初に、最近10回視聴された映画をJSON `user.lastWatchedMovies` 配列として追跡するために呼び出されるプロファイルスクリプトを作成します。 次に、以下のインクルージョンルールを使用して、項目を除外できます。

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

例えば、演奏するバンドがユーザーのお気に入りのバンドの1つである場合にのみ、コンサートのチケットを勧めたいとします。 まず、という名前のプロファイル変数にユーザーのお気に入り `profile.favoriteBands` のバンドが含まれていることを確認します。 次に、コンサートで演奏するアーティストを含む属 `entity.artistPerforming` 性がカタログに含まれていることを確認します。 次のインクルージョンルールを使用できます。

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

すべての条件と同様に、複数値のフィルタリングルールを使用する条件は、Adobe I/O APIを使用して作成できます。 エンティティ属性がmboxパラメーターリストに含まれる条件を作成す `id` るためのAPI呼び出しの例を次に `favorites` 示します。

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

これは、ページ上のJavaScriptとペアになって、お気に入りのコンテンツを渡します。

```
<!-- pass in the value of mbox parameter “favorites” as JSON array -->
<script type="text/javascript">
   mboxCreate('myMbox','entity.id=<key>','favorites=["a","b","c"]');
</script>
```
