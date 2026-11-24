---
keywords: 複数値；属性；レコメンデーション；複数値；複数値；複数値
description: 特殊な複数値の演算子を使用して、[!DNL Target Recommendations]の複数値フィールドを操作する方法を説明します。
title: 複数値の属性の扱い
feature: Recommendations
exl-id: 82018a9a-0983-458c-9387-3602dab4409b
TQID: 'https://experienceleague.adobe.com/FrjVxvYfGh2o-qomXRbVh6WS6f65Mja41gBMhejEPlE'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '502'
ht-degree: 2%
---
# 複数値の属性の扱い {#multi-value-attributes}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、複数値データを[!DNL Adobe Target Recommendations]に送信する方法と、複数値の演算子を含めるルールで使用する方法について説明します。

>[!ENDSHADEBOX]

複数値フィールドには、同じ項目または訪問者に対して複数の値が保持されます。 次に例を示します。

* ユーザーに提供される映画：特定の映画には複数の俳優が含まれます。
* コンサートのチケット販売：特定のユーザーには複数のお気に入りのバンドがあります。
* 衣料品販売：シャツは複数のサイズで利用できます。

これらのシナリオでレコメンデーションを処理するには、複数値データを[!DNL Target Recommendations]に渡し、特殊な複数値の演算子で使用します。

## 複数値データの送信 {#send}

[!DNL Recommendations]が多値データを識別できるようにするには、JSON配列として送信する必要があります。

JavaScript （`targetPageParams`）の複数値パラメーターについては、*カスタムエンティティ属性*&#x200B;の[複数値の属性の実装](/help/main/c-recommendations/c-products/custom-entity-attributes.md#section_80FEFE49E8AF415D99B739AA3CBA2A14)を参照してください。

CSV ファイルでは、次のサンプルのように、複数値のエンティティ属性が、属性のセル内のJSON配列として送信されます。

+++ 複数値の属性を持つCSV ファイルの例

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

+++

エンティティ属性、プロファイル属性、またはmbox パラメーターがこの形式で複数値として提供されると、[!DNL Recommendations]はフィールドが複数値であると自動的に推測します。

## 包含ルールで複数値属性を使用する {#multi-value-inclusion-rules}

複数値のエンティティ、プロファイルおよびmbox属性で使用できる演算子は次のとおりです。

* **[!UICONTROL はリスト]**&#x200B;に含まれています
* **[!UICONTROL はリスト]**&#x200B;に含まれていません

>[!NOTE]
>
>複数の値の属性に対する動的マッチングのサポートは、現在、左側の単一の値を右側の複数の値と比較するプロファイル属性マッチングまたはパラメーター（mbox）属性マッチングルールを使用する条件でのみ利用できます。 複数値の属性は、現在、プロモーション、エンティティ属性の一致、または包含ルールの左側のリストではサポートされていません。

### 例：最近視聴した項目を除外

ユーザーの最後の10本の視聴済み映画の映画が推奨されないようにするには、最初に、最後の10本の視聴済み映画をJSON配列として追跡する`user.lastWatchedMovies`というプロファイルスクリプトを作成します。 次の包含ルールを使用して、項目を除外できます。

```
Profile Attribute Matching
id - is not contained in list - user.lastWatchedMovies
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

バンドの演奏がユーザーのお気に入りのバンドの1つである場合にのみコンサートチケットを推薦するには、ユーザーのお気に入りのバンドを含む`profile.favoriteBands`というプロファイル変数と、コンサートで演奏するアーティストを含むカタログ内の属性`entity.artistPerforming`の2つの項目が必要です。 次の包含ルールを使用できます。

```
Profile Attribute Matching
artistPerforming - is contained in list - profile.favoriteBands
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

複数値フィルタリングルールを使用する条件は、すべての条件と同様に、[!DNL Adobe Target] APIを通じて作成できます。 次のAPI呼び出しの例では、エンティティ属性`id`がmbox パラメーターリスト `favorites`に含まれる条件を作成します。

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

この呼び出しは、お気に入りの内容を渡すページ上のJavaScriptと組み合わせられます。

```
<!-- pass in the value of mbox parameter "favorites" as JSON array -->
<script type="text/javascript">
   mboxCreate('myMbox','entity.id=<key>','favorites=["a","b","c"]');
</script>
```
