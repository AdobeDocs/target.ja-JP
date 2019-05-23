---
description: 'at. jsのadobe. target. getOffers（options）関数について取り上げます。 '
keywords: adobe.target.notification;要素;セレクター;通知;拡張子
seo-description: Adobe Target at. js JavaScriptライブラリのadobe. target. getOffers（options）関数について取り上げます。
seo-title: Adobe Target at. js JavaScriptライブラリのadobe. target. getOffers（options）関数について取り上げます。
solution: 'Target '
subtopic: 導入
title: adobe.target.getOffers(options)
topic: Standard
translation-type: tm+mt
source-git-commit: e5ac81441b7bf1c57b1bf62f49100e98673ac65c

---


# adobe. target. getOffers（options）- at. js2. x

この関数を使用すると、複数の mbox を渡すことで複数のオファーを取得できます。さらに、アクティブなアクティビティのすべてのビュー向けに複数のオファーを取得できます。

>[!NOTE]
>
>この関数はat. js2. xで導入されました。この関数はat. jsバージョン1では使用できません。*x*.

| キー | タイプ | 必須？ | 説明 |
| --- | --- | --- | --- |
| consumerId | 文字列 | × | 指定しない場合、デフォルト値はクライアントのグローバル mbox です。このキーは、A4T 統合に用いられる補助的なデータ ID を生成するために使用されます。 |
| リクエスト | オブジェクト | ○ | 下の「リクエスト」の表を参照してください。 |
| timeout | 数値 | × | リクエストのタイムアウト。指定しない場合、at.js のデフォルトのタイムアウトが使用されます。 |

## リクエスト

| フィールド名 | 必須？ | 制限事項 | 説明 |
| --- | --- | --- | --- |
| request &gt; id | × | `tntId`、`thirdPartyId`、または `marketingCloudVisitorId` のいずれか 1 つが必須です。 |
| Request &gt; id &gt; thirdPartyId | × | 最大サイズ = 128 |
| Request &gt; prefetch | × |
| Request &gt; prefetch &gt; views | × | 最大数 = 50<br>名前は空白にはできません<br>名前の長さ `<=` 128<br>値の長さ `<=` 5000<br>名前は「profile」で始まれません<br>使用できない名前：「orderId」、「orderTotal」、「productPurchasedId」 | アクティブなアクティビティで関連するビューを取得するために使用するパラメーターを渡します。 |
| Request &gt; prefetch &gt; views &gt; profileParameters | × | 最大数 = 50<br>名前は空白にはできません<br>名前の長さ `<=` 128<br>値の長さ `<=` 5000<br>名前は「profile」で始まれません | アクティブなアクティビティで関連するビューを取得するために使用するプロファイルパラメーターを渡します。 |
| Request &gt; prefetch &gt; views &gt; product | × |
| Request &gt; prefetch &gt; views &gt; product -&gt; id | × | 空白にはできません<br>最大サイズ = 128 | アクティブなアクティビティで関連するビューを取得するために使用する製品 ID を渡します。 |
| Request &gt; prefetch &gt; views &gt; product &gt; categoryId | × | 空白にはできません<br>最大サイズ = 128 | アクティビティ内の関連するビューを取得するために使用する製品カテゴリ ID を渡します。 |
| Request &gt; prefetch &gt; views &gt; order | × |
| Request &gt; prefetch &gt; views &gt; order &gt; id | × | 最大長 = 250 | アクティブなアクティビティで関連するビューを取得するために使用する注文 ID を渡します。 |
| Request &gt; prefetch &gt; views &gt; order &gt; total | × | 合計 `>=` 0 | アクティブなアクティビティで関連するビューを取得するために使用する注文の合計を渡します。 |
| Request &gt; prefetch &gt; views &gt; order &gt; purchasedProductIds | × | 値は空白にはできません<br>各値の最大長 50<br>コンマ区切りで連結された状態<br>製品 ID の合計の長さ `<=` 250 | アクティブなアクティビティで関連するビューを取得するために使用する 購入製品の ID を渡します。 |
| Request &gt; execute | × |
| Request &gt; execute &gt; pageLoad | × |
| Request &gt; execute &gt; pageLoad &gt; parameters | × | 最大数 = 50<br>名前は空白にはできません<br>名前の長さ `<=` 128<br>値の長さ `<=` 5000<br>名前は「profile」で始まれません<br>使用できない名前：「orderId」、「orderTotal」、「productPurchasedId」 | ページ読み込み時に、指定されたパラメーターを使用してオファーを取得します。 |
| Request &gt; execute &gt; pageLoad &gt; profileParameters | × | 最大数 = 50<br>名前は空白にはできません<br>名前の長さ `<=` 128<br>値の長さ `<=` 256<br>名前は「profile」で始まれません | ページ読み込み時に、指定されたプロファイルパラメーターを使用してオファーを取得します。 |
| Request &gt; execute &gt; pageLoad &gt; product | × |
| Request &gt; execute &gt; pageLoad &gt; product -&gt; id | × | 空白にはできません<br>最大サイズ = 128 | ページ読み込み時に、指定された製品 ID を使用してオファーを取得します。 |
| Request &gt; execute &gt; pageLoad &gt; product &gt; categoryId | × | 空白にはできません<br>最大サイズ = 128 | ページ読み込み時に、指定された製品カテゴリー ID を使用してオファーを取得します。 |
| Request &gt; execute &gt; pageLoad &gt; order | × |
| Request &gt; execute &gt; pageLoad &gt; order &gt; id | × | 最大長 = 250 | ページ読み込み時に、指定された注文 ID を使用してオファーを取得します。 |
| Request &gt; execute &gt; pageLoad &gt; order &gt; total | × | `>=` 0 | ページ読み込み時に、指定された注文の合計を使用してオファーを取得します。 |
| Request &gt; execute &gt; pageLoad &gt; order &gt; purchasedProductIds | × | 値は空白にできません<br>各値の最大長 50<br>コンマ区切りで連結された状態<br>商品 ID の合計の長さ `<=` 250 | ページ読み込み時に、指定された購入 ID を使用してオファーを取得します。 |
| Request &gt; execute &gt; mboxes | × | 最大サイズ = 50<br>null 要素は使用できません |
| Request &gt; execute &gt; mboxes&gt;mbox | ○ | 空白にはできません<br>「-clicked」サフィックスは使用できません<br>最大サイズ = 250<br>使用できる文字： `'-, ._\/=:;&!@#$%^&*()_+|?~[]{}'` | mbox の名前。 |
| Request &gt; execute &gt; mboxes&gt;mbox&gt;index | ○ | null は使用できません<br>一意<br>`>=` 0 | 注意： インデックスは、mbox が処理される順序を表すものではありません。複数のリージョナル mbox を持つ Web ページと同様、mbox が処理される順序は指定できません。 |
| Request &gt; execute &gt; mboxes &gt; mbox &gt; parameters | × | 最大数 = 50<br>名前は空白にはできません<br>名前の長さ `<=` 128<br>値の長さ `<=` 5000<br>名前は「profile」で始まれません<br>使用できない名前：「orderId」、「orderTotal」、「productPurchasedId」 | 指定されたパラメーターを使用して特定の mbox のオファーを取得します。 |
| Request &gt; execute &gt; mboxes&gt;mbox&gt;profileParameters | × | 最大数 = 50<br>名前は空白にはできません<br>名前の長さ `<=` 128<br>値の長さ `<=` 256<br>名前は「profile」で始まれません | 指定されたプロファイルパラメーターを使用して特定の mbox のオファーを取得します。 |
| Request &gt; execute &gt; mboxes&gt;mbox &gt; product | × |
| Request &gt; execute &gt; mboxes &gt; mbox &gt; product &gt; id | × | 空白にはできません<br>最大サイズ = 128 | 指定された製品 ID を使用して特定の mbox のオファーを取得します。 |
| Request &gt; execute &gt; mboxes &gt; mbox &gt; product &gt; categoryId | × | 空白にはできません<br>最大サイズ = 128 | 指定された製品カテゴリー ID を使用して特定の mbox のオファーを取得します。 |
| Request &gt; execute &gt; mboxes &gt; mbox &gt; order | × |
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

## getOffers（）およびapplyOffers（）を使用した複数のmboxからのデータの取得およびレンダリング {#multiple}

at. js2. xを使用すると、 `getOffers()` APIを使用して複数のmboxを取得できます。また、複数のmboxのデータを取得して、 `applyOffers()` CSSセレクターによって識別される様々な場所でデータをレンダリングすることもできます。

次の例は、at. js2. xを実装した単純なHTMLページを示しています。

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

コンテンツを受信したコンテンツを使用して変更する3つのコンテナがあるとし [!DNL Target]ます。それぞれのmboxに、それぞれのコンテナにレンダリングするコンテンツがある3つのmboxに対して単一のリクエストを作成できます。

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

`request > prefetch > mboxes` このセクションでは、3つの異なるmboxがあります。リクエストが正常に完了した場合は、各mboxに対する応答を受信 `response > prefetch > mboxes`します。応答およびレンダリングに使用する場所があると、取得したコンテンツをレンダリング `applyOffers()` するために呼び出すこと [!DNL Target]ができます。この例では、次のマッピングがあります。

* mbox1/CSSセレクター# container1
* mbox2&gt; CSSセレクター# container2
* mbox3/CSSセレクター# container3

この例では、count変数を使用してCSSセレクターを作成します。実際のシナリオでは、CSSセレクターとmboxとの異なるマッピングを使用できます。

この例では使用さ `prefetch > mboxes`れていますが、使用 `execute > mboxes`することもできます。で `getOffers()`プリフェッチを使用する場合は `applyOffers()` 、呼び出しでもプリフェッチを使用する必要があります。