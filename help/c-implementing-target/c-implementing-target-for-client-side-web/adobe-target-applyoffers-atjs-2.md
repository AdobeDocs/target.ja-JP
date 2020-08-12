---
keywords: adobe.target.applyOffers;applyOffers;applyoffers;apply offers;at.js;functions;function
description: Adobe Target at.js JavaScript ライブラリの adobe.target.applyOffers(options) 関数について説明します。
title: Adobe Target at.js JavaScript ライブラリの adobe.target.applyOffers(options) 関数について説明します。
feature: null
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 95%

---


# adobe.target.applyOffers(options) - at.js 2.x

この関数を使用すると、`adobe.target.getOffers()` で取得した複数のオファーを適用できます。

>[!NOTE]
>
>この関数は at.js 2.x で導入されました。この関数は at.js バージョン 1 では使用できません。*x*.

| キー | タイプ | 必須？ | 説明 |
| --- | --- | --- | --- |
| selector | 文字列 | × | [!DNL Target] がオファーコンテンツを配置する必要がある HTML 要素を特定するために使用される HTML 要素または CSS セレクター。If a selector is not provided, [!DNL Target] assumes that the HTML element to use is HTML HEAD. |
| 応答 | オブジェクト | ○ | `getOffers()` からのレスポンスオブジェクト。<br>下の「リクエスト」の表を参照してください。 |

## 応答

>[!NOTE]
>
>以下に示すすべてのフィールドに使用できるタイプについては、 [配信APIのドキュメント](http://developers.adobetarget.com/api/delivery-api/#tag/Delivery-API) を参照してください。

| フィールド名 | 説明 |
| --- | --- |
| response > prefetch > views > options > content | 注意：「オプション」の内容は明確に定義されておらず、オプションのタイプ／テンプレートの構造に直接依存しています。 |
| response > prefetch > views > options > type | オプションのタイプ。「コンテンツ」フィールドのタイプを反映します。サポートされているタイプはアクションです。 |
| response > prefetch > views > state | ビューの表示通知で転送する必要がある不透明なビューステートトークン。 |
| response > prefetch > views > options > responseTokens | 現在のオプションの処理時に収集された `responseTokens` のマップが含まれています。 |
| response > prefetch > views > analytics > payload | ビューが適用された後に Analytics に送信される必要があるクライアントサイド統合のための Analytics ペイロード。 |
| response > prefetch > views > trace | ビューごとのプリフェッチコールの全トレースデータを含むオブジェクト。<br>トレースオブジェクトにはトレースのバージョンも含まれます。<br>トレースオブジェクトには、現在のビューの詳細も含まれます。 |
| response > prefetch > views > options > eventToken | イベントログはオプションごとに実行されます。適用されるオプションごとに、それぞれのイベントトークンを通知トークンのリストに追加する必要があります。注意： ビューは複数のオプションで構成されています。すべてのオプションの適用および表示されている場合、通知にすべての `eventTokens` を含める必要があります。 |
| response > prefetch > views > name | 人間が解読可能な形式のビュー名。 |
| response > prefetch > views > metrics | 監視してから [!DNL Target] に通知する必要のあるレポート指標。現在、クリック指標のみがサポートされています。要素がクリックされると、適切な `eventTokens` が収集され、通知が送信されます。 |
| response > prefetch > views > key | ビューを識別するキーまたはフィンガープリント。 |
| response > prefetch > views > id | ビューの ID。 |
| response > notifications > id | 通知 ID。 |
| response > notifications > events > type | 通知、クリックまたは表示のタイプ。 |
| response > notifications > events > trace | 通知イベントのトレース。 |
| response > notifications > events > token | 通知イベントで送信されたトークン。 |
| response > notifications > events > timestamp | 通知イベントで送信されたタイムスタンプ。 |
| response > notifications > events > errorCode | 通知が失敗した場合、コードは失敗の理由を示します。 |
| response > notifications > events | 現在の通知について記録されたか、記録が失敗したイベント。 |
| response > notifications | 通知が記録されたか、記録が失敗したかを示します。 |
| response > execute > mboxes > mbox > trace | 個々の mbox リクエストの全トレースデータを含むオブジェクト。 |
| response > execute > mboxes > mbox > responseTokens | 特定の mbox リクエストの実行のための `responseTokens` のマップが含まれています。 |
| response > execute > mboxes > mbox > option > content | 注意：「オプション」の内容は明確に定義されておらず、オプションのタイプ／テンプレートの構造に直接依存しています。 |
| response > execute > mboxes > mbox > option > type | オプションのタイプ。「コンテンツ」フィールドのタイプを反映します。サポートされているタイプは、html、redirect、JSON、および dynamic です。 |
| response > execute > mboxes > mbox > options | レスポンスオプション。 |
| response > execute > mboxes > mbox > metrics > eventToken | クリックイベントのトークン。 |
| response > execute > mboxes > mbox > metrics > type | &quot;click&quot; |
| response > execute > mboxes > mbox > metrics | `clickThrough` 指標のリストが含まれています。 |
| response > execute > mboxes > mbox > mbox | mbox の名前。 |
| response > execute > mboxes > mbox >index | レスポンスが、リクエストからのこのインデックスを持つ mbox に対するものであることを示します。 |
| response > execute > mboxes > mbox > analytics > payload | mbox の適用後に Analytics に送信する必要がある、クライアントサイド統合用の Analytics ペイロード（「A4T が有効なキャンペーン」セクションを参照してください） |
| response > execute > mboxes | 実行された mbox のリスト。 |
| response > execute > pageLoad > options > content | 注意：「オプション」の内容は明確に定義されておらず、オプションのタイプ／テンプレートの構造に直接依存しています。 |
| response > execute > pageLoad > options > type | オプションのタイプ。「コンテンツ」フィールドのタイプを反映します。サポートされているタイプは、html、redirect、JSON、dynamic、および action です。 |
| response > execute > pageLoad > options | ビューでグループ化されていないオプション（target-global-mbox およびビューでグループ化されていないビューを持つアクティビティのオプション）。 |
| response > execute > pageLoad > metrics | 特定のビューに属していないクリック指標。 |
| response > execute > pageLoad > trace | pageLoad リクエストのすべてのトレースデータを含むオブジェクト。 |
| response > execute > pageLoad > analytics > payload | ページロードコンテンツが適用された後に Analytics に送信する必要がある、クライアントサイド統合用の Analytics ペイロード。（「A4T が有効なキャンペーン」セクションを参照してください） |

## applyOffers() の呼び出しの例

```
adobe.target.applyOffers({response:{
  "execute": {
    "pageLoad": {
      "options": [{
        "type": "html",
        "content": "page-load"
      },
      {
        "type": "actions",
        "content": [{
          "type": "setHtml",
          "content": "<h1>Container 1</h1>",
          "selector": "#container1",
          "cssSelector": "#container1"
        },
        {
          "type": "setHtml",
          "content": "<h3>Container 3</h3>",
          "selector": "#container3",
          "cssSelector": "#container3"
        }]
      }],
 
 
      "metrics": [{
        "type": "click",
        "selector": "#container1",
        "eventToken": "page-load-click-metric" 
      }]
    }
  }
}});
```

## Promise ベースである `getOffers()` と `applyOffers()` をチェイニングする Promice の呼び出し例

```
adobe.target.getOffers({...})
.then(response => adobe.target.applyOffers({ response: response }))
.then(() => console.log("Success"))
.catch(error => console.log("Error", error));
```
