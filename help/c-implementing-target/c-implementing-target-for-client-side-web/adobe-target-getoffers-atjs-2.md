---
description: 'at.js の adobe.target.getOffers() 関数についての情報です。 '
keywords: adobe. target. getOffers;getOffers;getオファー;オファーの取得、at. js;関数、関数
seo-description: Adobe Target at.js JavaScript ライブラリの adobe.target.getOffers（options） 関数に関する情報です。
seo-title: Adobe Target at.js JavaScript ライブラリの adobe.target.getOffers（） 関数に関する情報です。
solution: 'Target '
subtopic: 導入
title: adobe.target.getOffers(options)
topic: Standard
translation-type: tm+mt
source-git-commit: b75b6463aa278505ae4f75d43f56f9bfa6313ede

---


# adobe.target.getOffers(options) - at.js 2.x

この関数を使用すると、複数の mbox を渡すことで複数のオファーを取得できます。さらに、アクティブなアクティビティのすべてのビュー向けに複数のオファーを取得できます。

>[!NOTE]
>
>この関数は at.js 2.x で導入されました。この関数は at.js バージョン 1 では使用できません。*x*.

| キー | タイプ | 必須？ | 説明 |
| --- | --- | --- | --- |
| consumerId | 文字列 | × | 指定しない場合、デフォルト値はクライアントのグローバル mbox です。このキーは、A4T 統合に用いられる補助的なデータ ID を生成するために使用されます。このキーは訪問者ごとの一意の文字列です。 |
| リクエスト | オブジェクト | ○ | 下の「リクエスト」の表を参照してください。 |
| timeout | 数値 | × | リクエストのタイムアウト。指定しない場合、at.js のデフォルトのタイムアウトが使用されます。 |

## リクエスト

| フィールド名 | 必須？ | 制限事項 | 説明 |
| --- | --- | --- | --- |
| request &gt; id | × |  | `tntId`、`thirdPartyId`、または `marketingCloudVisitorId` のいずれか 1 つが必須です。 |
| Request &gt; id &gt; thirdPartyId | × | 最大サイズ = 128 |  |  |
| リクエスト/ExperienceCloud | × |  |  |
| リクエスト&gt; ExperienceCloud&gt; analytics | × |  | Adobe Analyticsの統合 |
| リクエスト&gt; ExperienceCloud&gt; analytics&gt;ログ | × | 次のページに実装する必要があります。<ul><li>訪問者 ID サービス</li><li>Appmeasurement. js</li></ul> | 次の値がサポートされています。<br>**client_ side**:指定した場合、Analyticsペイロードは、Data Insertion APIを介してAdobe Analyticsに送信するために使用される呼び出し元に返されます。<br>**server_ side**:これは、TargetとAnalyticsのバックエンドが、レポート用に呼び出しを組み合わせるためにSDIDを使用するデフォルト値です。 |
| Request &gt; prefetch | × |  |  |
| Request &gt; prefetch &gt; views | × | 最大数 = 50<br>名前は空白にはできません<br>名前の長さ `<=` 128<br>値の長さ `<=` 5000<br>名前は「profile」で始まれません<br>使用できない名前：「orderId」、「orderTotal」、「productPurchasedId」 | アクティブなアクティビティで関連するビューを取得するために使用するパラメーターを渡します。 |
| Request &gt; prefetch &gt; views &gt; profileParameters | × | 最大数 = 50<br>名前は空白にはできません<br>名前の長さ `<=` 128<br>値の長さ `<=` 5000<br>名前は「profile」で始まれません | アクティブなアクティビティで関連するビューを取得するために使用するプロファイルパラメーターを渡します。 |
| Request &gt; prefetch &gt; views &gt; product | × |  |  |
| Request &gt; prefetch &gt; views &gt; product -&gt; id | × | 空白にはできません<br>最大サイズ = 128 | アクティブなアクティビティで関連するビューを取得するために使用する製品 ID を渡します。 |
| Request &gt; prefetch &gt; views &gt; product &gt; categoryId | × | 空白にはできません<br>最大サイズ = 128 | アクティビティ内の関連するビューを取得するために使用する製品カテゴリ ID を渡します。 |
| Request &gt; prefetch &gt; views &gt; order | × |  |  |
| Request &gt; prefetch &gt; views &gt; order &gt; id | × | 最大長 = 250 | アクティブなアクティビティで関連するビューを取得するために使用する注文 ID を渡します。 |
| Request &gt; prefetch &gt; views &gt; order &gt; total | × | 合計 `>=` 0 | アクティブなアクティビティで関連するビューを取得するために使用する注文の合計を渡します。 |
| Request &gt; prefetch &gt; views &gt; order &gt; purchasedProductIds | × | 値は空白にはできません<br>各値の最大長 50<br>コンマ区切りで連結された状態<br>製品 ID の合計の長さ `<=` 250 | アクティブなアクティビティで関連するビューを取得するために使用する 購入製品の ID を渡します。 |
| Request &gt; execute | × |  |  |
| Request &gt; execute &gt; pageLoad | × |  |  |
| Request &gt; execute &gt; pageLoad &gt; parameters | × | 最大数 = 50<br>名前は空白にはできません<br>名前の長さ `<=` 128<br>値の長さ `<=` 5000<br>名前は「profile」で始まれません<br>使用できない名前：「orderId」、「orderTotal」、「productPurchasedId」 | ページ読み込み時に、指定されたパラメーターを使用してオファーを取得します。 |
| Request &gt; execute &gt; pageLoad &gt; profileParameters | × | 最大数 = 50<br>名前は空白にはできません<br>名前の長さ `<=` 128<br>値の長さ `<=` 256<br>名前は「profile」で始まれません | ページ読み込み時に、指定されたプロファイルパラメーターを使用してオファーを取得します。 |
| Request &gt; execute &gt; pageLoad &gt; product | × |  |  |
| Request &gt; execute &gt; pageLoad &gt; product -&gt; id | × | 空白にはできません<br>最大サイズ = 128 | ページ読み込み時に、指定された製品 ID を使用してオファーを取得します。 |
| Request &gt; execute &gt; pageLoad &gt; product &gt; categoryId | × | 空白にはできません<br>最大サイズ = 128 | ページ読み込み時に、指定された製品カテゴリー ID を使用してオファーを取得します。 |
| Request &gt; execute &gt; pageLoad &gt; order | × |  |  |
| Request &gt; execute &gt; pageLoad &gt; order &gt; id | × | 最大長 = 250 | ページ読み込み時に、指定された注文 ID を使用してオファーを取得します。 |
| Request &gt; execute &gt; pageLoad &gt; order &gt; total | × | `>=` 0 | ページ読み込み時に、指定された注文の合計を使用してオファーを取得します。 |
| Request &gt; execute &gt; pageLoad &gt; order &gt; purchasedProductIds | × | 値は空白にはできません<br>各値の最大長 50<br>コンマ区切りで連結された状態<br>製品 ID の合計の長さ `<=` 250 | ページ読み込み時に、指定された購入 ID を使用してオファーを取得します。 |
| Request &gt; execute &gt; mboxes | × | 最大サイズ = 50<br>null 要素は使用できません |  |
| Request &gt; execute &gt; mboxes&gt;mbox | ○ | 空白にはできません<br>「-clicked」サフィックスは使用できません<br>最大サイズ = 250<br>使用できる文字： `'-, ._\/=:;&!@#$%^&*()_+|?~[]{}'` | mbox の名前。 |
| Request &gt; execute &gt; mboxes&gt;mbox&gt;index | ○ | null は使用できません<br>一意<br>`>=` 0 | 注意： インデックスは、mbox が処理される順序を表すものではありません。複数のリージョナル mbox を持つ Web ページと同様、mbox が処理される順序は指定できません。 |
| Request &gt; execute &gt; mboxes &gt; mbox &gt; parameters | × | 最大数 = 50<br>名前は空白にはできません<br>名前の長さ `<=` 128<br>値の長さ `<=` 5000<br>名前は「profile」で始まれません<br>使用できない名前：「orderId」、「orderTotal」、「productPurchasedId」 | 指定されたパラメーターを使用して特定の mbox のオファーを取得します。 |
| Request &gt; execute &gt; mboxes&gt;mbox&gt;profileParameters | × | 最大数 = 50<br>名前は空白にはできません<br>名前の長さ `<=` 128<br>値の長さ `<=` 256<br>名前は「profile」で始まれません | 指定されたプロファイルパラメーターを使用して特定の mbox のオファーを取得します。 |
| Request &gt; execute &gt; mboxes&gt;mbox &gt; product | × |  |  |
| Request &gt; execute &gt; mboxes &gt; mbox &gt; product &gt; id | × | 空白にはできません<br>最大サイズ = 128 | 指定された製品 ID を使用して特定の mbox のオファーを取得します。 |
| Request &gt; execute &gt; mboxes &gt; mbox &gt; product &gt; categoryId | × | 空白にはできません<br>最大サイズ = 128 | 指定された製品カテゴリー ID を使用して特定の mbox のオファーを取得します。 |
| Request &gt; execute &gt; mboxes &gt; mbox &gt; order | × |  |  |
| Request &gt; execute &gt; mboxes&gt;mbox &gt; order &gt; id | × | 最大長 = 250 | 指定された注文 ID を持つ特定の mbox のオファーを取得します。 |
| Request &gt; execute &gt; mboxes &gt; mbox &gt; order &gt; total | × | `>=` 0 | 指定された注文合計を持つ特定の mbox のオファーを取得します。 |
| Request &gt; execute &gt; mboxes &gt; mbox &gt; order &gt; purchasedProductIds | × | 値は空白にはできません<br>各値の最大長 = 50<br>コンマ区切りで連結された状態<br>製品 ID の合計の長さ`<=` 250 | 指定された注文で購入された製品 ID を持つ特定の mbox のオファーを取得します。 |

## すべてのビューに `getOffers()` を呼び出す

```
adobe.target.getOffers({
    prefetch: {
      views: []
    }
  }
});
```

## `getOffers()` を呼び出し、渡されたパラメーターとプロファイルを使用して最新ビューを取得する

```
adobe.target.getOffers({
  request: {
    "prefetch": {
      "views": [
        {
          "parameters": {
            "ad": "1"
          },
          "profileParameters": {
            "age": 23
          }
        }
      ]
    }
  }
});
```

## `getOffers()` を呼び出し、渡されたパラメーターとプロファイルを使用して mbox を取得する

```
adobe.target.getOffers({
  request: {
    execute: {
      mboxes: [
        {
          index: 0,
          name: "first-mbox"
        },
        {
          index: 1,
          name: "second-mbox",
          parameters: {
            a: 1
          },
          profileParameters: {
            b: 2
          }
        }
      ]
    }
  }
});
```

## getOffers（）を呼び出して、クライアント側からAnalyticsペイロードを取得します

```
adobe.target.getOffers({
      request: {
        experienceCloud: {
          analytics: {
            logging: "client_side"
          }
        },
        prefetch: {
          mboxes: [{
            index: 0,
            name: "a1-serverside-xt"
          }]
        }
      }
    })
    .then(console.log)
```

**応答**:

```
{
  "prefetch": {
    "mboxes": [{
      "index": 0,
      "name": "a1-serverside-xt",
      "options": [{
        "content": "<img src=\"http://s7d2.scene7.com/is/image/TargetAdobeTargetMobile/L4242-xt-usa?tm=1490025518668&fit=constrain&hei=491&wid=980&fmt=png-alpha\"/>",
        "type": "html",
        "eventToken": "n/K05qdH0MxsiyH4gX05/2qipfsIHvVzTQxHolz2IpSCnQ9Y9OaLL2gsdrWQTvE54PwSz67rmXWmSnkXpSSS2Q==",
        "responseTokens": {
          "profile.memberlevel": "0",
          "geo.city": "bucharest",
          "activity.id": "167169",
          "experience.name": "USA Experience",
          "geo.country": "romania"
        }
      }],
      "analytics": {
        "payload": {
          "pe": "tnt",
          "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
        }
      }
    }]
  }
}
```

その後、Data Insertion APIを [使用してペイロードをAdobe Analyticsに転送](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)できます。

## getOffers() および applyOffers() を介して複数の mbox からデータを取得してレンダリングする {#multiple}

at.js 2.x を使用すると、`getOffers()` API を使用して複数の mbox を取得できます。複数の mbox のデータを取得して、`applyOffers()` CSS セレクターによって識別されるさまざまな場所で、データをレンダリングすることもできます。

次の例は、at.js 2.x を実装した単純な HTML ページを示しています。

```
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>at.js 2.x, multiple selectors and multiple mboxes</title>
  <script src="at.js"></script>
</head>
<body>
  <div id="container1">Default content 1</div>
  
  <div id="container2">Default content 2</div>

  <div id="container3">Default content 3</div>
</body>
</html>
```

[!DNL Target] から受け取ったコンテンツを介して変更したい 3 つのコンテナがあるとします。3 つの mbox に対して 1 つのリクエストを作成し、それぞれの mbox に、それぞれのコンテナにレンダリングするためのコンテンツを含めることができます。

リクエストおよびレンダリングコードは次の例のようになります。

```
adobe.target.getOffers({
  request: {
    prefetch: {
      mboxes: [
        {
          index: 0,
          name: "mbox1"
        },
        {
          index: 1,
          name: "mbox2"
        },
        {
          index: 2,
          name: "mbox3"
        }
      ]
    }
  }
})
.then(response => {
  // get all mboxes from response
  const mboxes = response.prefetch.mboxes;
  let count = 1;

  mboxes.forEach(el => {
    adobe.target.applyOffers({
      selector: "#container" + count,
      response: {
        prefetch: {
          mboxes: [el]
        }
      }
    });

    count += 1;
  });
});
```

`request > prefetch > mboxes` セクションでは、3 つの異なる mbox があります。リクエストが正常に完了した場合は、それぞれの mbox に対する応答を `response > prefetch > mboxes` から受信します。レスポンスとレンダリングに使用する場所が決まったら、`applyOffers()` を呼び出して [!DNL Target] から取得したコンテンツをレンダリングできます。この例では、次のマッピングがあります。

* mbox1／CSS セレクター# container1
* mbox2／CSS セレクター# container2
* mbox3／CSS セレクター# container3

この例では、count 変数を使用して CSS セレクターを作成します。実際のシナリオでは、CSS セレクターと mbox との異なるマッピングを使用できます。

この例では `prefetch > mboxes` を使用していますが、`execute > mboxes` を使用することもできます。`getOffers()` でプリフェッチを使用する場合は、`applyOffers()` 呼び出しでもプリフェッチを使用する必要があります。
