---
description: 'at.js の adobe.target.applyOffers() 関数について説明します。 '
keywords: adobe. target. applyOffers;applyOffers;applyers;オファーの適用、at. js;関数、関数
seo-description: Adobe Target at.js JavaScript ライブラリの adobe.target.applyOffers(options) 関数について説明します。
seo-title: Adobe Target at.js JavaScript ライブラリの adobe.target.applyOffers(options) 関数について説明します。
solution: 'Target '
subtopic: 導入
title: adobe.target.applyOffers(options)
topic: Standard
translation-type: tm+mt
source-git-commit: ef2c4ac78fef5889d5a6e9e053dfd36b77919dd4

---


# adobe.target.applyOffers(options) - at.js 2.x

この関数を使用すると、`adobe.target.getOffers()` で取得した複数のオファーを適用できます。

>[!NOTE]
>
>この関数は at.js 2.x で導入されました。この関数は at.js バージョン 1 では使用できません。*x*.

| キー | タイプ | 必須？ | 説明 |
| --- | --- | --- | --- |
| selector | 文字列 | × | [!DNL Target] がオファーコンテンツを配置する必要がある HTML 要素を特定するために使用される HTML 要素または CSS セレクター。セレクターがない場合、[!DNL Target] は、使用する必要がある HTML 要素が HTML HEAD であると仮定します。 |
| 応答 | オブジェクト | ○ | `getOffers()` からのレスポンスオブジェクト。<br>下の「リクエスト」の表を参照してください。 |

## 応答

| フィールド名 | 説明 |
| --- | --- |
| response &gt; prefetch &gt; views &gt; options &gt; content | 注意：「オプション」の内容は明確に定義されておらず、オプションのタイプ／テンプレートの構造に直接依存しています。 |
| response &gt; prefetch &gt; views &gt; options &gt; type | オプションのタイプ。「コンテンツ」フィールドのタイプを反映します。サポートされているタイプはアクションです。 |
| response &gt; prefetch &gt; views &gt; state | ビューの表示通知で転送する必要がある不透明なビューステートトークン。 |
| response &gt; prefetch &gt; views &gt; options &gt; responseTokens | 現在のオプションの処理時に収集された `responseTokens` のマップが含まれています。 |
| response &gt; prefetch &gt; views &gt; analytics &gt; payload | ビューが適用された後に Analytics に送信される必要があるクライアントサイド統合のための Analytics ペイロード。 |
| response &gt; prefetch &gt; views &gt; trace | ビューごとのプリフェッチコールの全トレースデータを含むオブジェクト。<br>トレースオブジェクトにはトレースのバージョンも含まれます。<br>トレースオブジェクトには、現在のビューの詳細も含まれます。 |
| response &gt; prefetch &gt; views &gt; options &gt; eventToken | イベントログはオプションごとに実行されます。適用されるオプションごとに、それぞれのイベントトークンを通知トークンのリストに追加する必要があります。注意： ビューは複数のオプションで構成されています。すべてのオプションの適用および表示されている場合、通知にすべての `eventTokens` を含める必要があります。 |
| response &gt; prefetch &gt; views &gt; name | 人間が解読可能な形式のビュー名。 |
| response &gt; prefetch &gt; views &gt; metrics | 監視してから [!DNL Target] に通知する必要のあるレポート指標。現在、クリック指標のみがサポートされています。要素がクリックされると、適切な `eventTokens` が収集され、通知が送信されます。 |
| response &gt; prefetch &gt; views &gt; key | ビューを識別するキーまたはフィンガープリント。 |
| response &gt; prefetch &gt; views &gt; id | ビューの ID。 |
| response &gt; notifications &gt; id | 通知 ID。 |
| response &gt; notifications &gt; events &gt; type | 通知、クリックまたは表示のタイプ。 |
| response &gt; notifications &gt; events &gt; trace | 通知イベントのトレース。 |
| response &gt; notifications &gt; events &gt; token | 通知イベントで送信されたトークン。 |
| response &gt; notifications &gt; events &gt; timestamp | 通知イベントで送信されたタイムスタンプ。 |
| response &gt; notifications &gt; events &gt; errorCode | 通知が失敗した場合、コードは失敗の理由を示します。 |
| response &gt; notifications &gt; events | 現在の通知について記録されたか、記録が失敗したイベント。 |
| response &gt; notifications | 通知が記録されたか、記録が失敗したかを示します。 |
| response &gt; execute &gt; mboxes &gt; mbox &gt; trace | 個々の mbox リクエストの全トレースデータを含むオブジェクト。 |
| response &gt; execute &gt; mboxes &gt; mbox &gt; responseTokens | 特定の mbox リクエストの実行のための `responseTokens` のマップが含まれています。 |
| response &gt; execute &gt; mboxes &gt; mbox &gt; option &gt; content | 注意：「オプション」の内容は明確に定義されておらず、オプションのタイプ／テンプレートの構造に直接依存しています。 |
| response &gt; execute &gt; mboxes &gt; mbox &gt; option &gt; type | オプションのタイプ。「コンテンツ」フィールドのタイプを反映します。サポートされているタイプは、html、redirect、JSON、および dynamic です。 |
| response &gt; execute &gt; mboxes &gt; mbox &gt; options | レスポンスオプション。 |
| response &gt; execute &gt; mboxes &gt; mbox &gt; metrics &gt; eventToken | クリックイベントのトークン。 |
| response &gt; execute &gt; mboxes &gt; mbox &gt; metrics &gt; type | "click" |
| response &gt; execute &gt; mboxes &gt; mbox &gt; metrics | `clickThrough` 指標のリストが含まれています。 |
| response &gt; execute &gt; mboxes &gt; mbox &gt; mbox | mbox の名前。 |
| response &gt; execute &gt; mboxes &gt; mbox &gt;index | レスポンスが、リクエストからのこのインデックスを持つ mbox に対するものであることを示します。 |
| response &gt; execute &gt; mboxes &gt; mbox &gt; analytics &gt; payload | mbox の適用後に Analytics に送信する必要がある、クライアントサイド統合用の Analytics ペイロード（「A4T が有効なキャンペーン」セクションを参照してください） |
| response &gt; execute &gt; mboxes | 実行された mbox のリスト。 |
| response &gt; execute &gt; pageLoad &gt; options &gt; content | 注意：「オプション」の内容は明確に定義されておらず、オプションのタイプ／テンプレートの構造に直接依存しています。 |
| response &gt; execute &gt; pageLoad &gt; options &gt; type | オプションのタイプ。「コンテンツ」フィールドのタイプを反映します。サポートされているタイプは、html、redirect、JSON、dynamic、および action です。 |
| response &gt; execute &gt; pageLoad &gt; options | ビューでグループ化されていないオプション（target-global-mbox およびビューでグループ化されていないビューを持つアクティビティのオプション）。 |
| response &gt; execute &gt; pageLoad &gt; metrics | 特定のビューに属していないクリック指標。 |
| response &gt; execute &gt; pageLoad &gt; trace | pageLoad リクエストのすべてのトレースデータを含むオブジェクト。 |
| response &gt; execute &gt; pageLoad &gt; analytics &gt; payload | ページロードコンテンツが適用された後に Analytics に送信する必要がある、クライアントサイド統合用の Analytics ペイロード。（「A4T が有効なキャンペーン」セクションを参照してください） |

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
