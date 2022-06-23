---
keywords: adobe.target.sendNotifications;sendNotifications;sendnotifications;send notifications;notifications;at.js;関数
description: at.js の adobe.target.sendNotifications() を使用して、 [!DNL Target] エッジで囲まれます。 （at.js.2.1 以降）
title: adobe.target.sendNotifications() 関数の使用方法を教えてください。
feature: at.js
role: Developer
exl-id: 71b7167d-729c-4d43-8f54-f43619e14f32
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 94%

---

# adobe.target.sendNotifications(options)

この関数は、`adobe.target.applyOffer()` や `adobe.target.applyOffers()` を使用せずにエクスペリエンスがレンダリングされる場合、Target Edge に通知を送信します。

>[!NOTE]
>
>この関数は、at.js 2.1.0 で導入され、2.1.0 以上の任意のバージョンで使用できます。

| キー | タイプ | 必須？ | 説明 |
| --- | --- | --- | --- |
| consumerId | 文字列 | × | 指定しない場合、デフォルト値はクライアントのグローバル mbox です。このキーは、A4T 統合に使用される補助的なデータ ID を生成するために使用されます。 |
| リクエスト | オブジェクト | ○ | 下の「リクエスト」の表を参照してください。 |
| timeout | 数値 | × | リクエストのタイムアウト。指定しない場合、at.js のデフォルトのタイムアウトが使用されます。 |

## リクエスト

| フィールド名 | タイプ | 必須？ | 制限事項 | 説明 |
| --- | --- | --- | --- | --- |
| Request > notifications | オブジェクトの配列 | ○ |  | 表示されるコンテンツに対する通知、クリックされたセクター、訪問されたビューまたは mbox。 |
| Request > notifications > address | オブジェクト | × |  |  |
| Request > notifications > address > url | 文字列 | × |  | 通知の送信元の URL。 |
| Request > notifications > address > referringUrl | 文字列 | × |  | 通知の送信元のリファラル URL。 |
| Request > notifications > parameters | 文字列 | × | 以下の名前はパラメーターに使用できません。<ul><li>orderId</li><li>orderTotal</li><li>productPurchasedIds</li></ul>次の点に留意してください。<ul><li>最大 50 パラメーターの制限。</li><li>パラメーター名は空にできない。</li><li>パラメーター名の最大長は 128。</li><li>パラメーター名は「profile」で始めることはできない。</li><li>パラメーター値最大長は 5000。</li></ul> |  |
| Request > notifications > profileParameters | 文字列 | × | 以下の名前はパラメーターに使用できません。<ul><li>orderId</li><li>orderTotal</li><li>productPurchasedIds</li></ul>次の点に留意してください。<ul><li>最大 50 パラメーターの制限。</li><li>パラメーター名は空にできない。</li><li>パラメーター名の最大長は 128。</li><li>パラメーター名は「profile」で始めることはできない。</li><li>パラメーター値最大長は 5000。</li></ul> |  |
| Request > notifications > order | オブジェクト | × |  | 注文の詳細を説明するオブジェクト。 |
| Request > notifications > order > id | 文字列 | × | `<=` 250 文字。 | 注文 ID。 |
| Request > notifications > order > total | 文字列 | × | `>=` 0 | 合計注文額。 |
| Request > notifications > order > purchasedProductIds | 文字列の配列 | × | <ul><li>空の値は許可されない。</li><li>各製品 ID の最大長は 50。</li><li>（コンマ区切りで連結された）製品 ID の合計の長さは 250 以内。</li></ul> | 注文製品 ID。 |
| Request > notifications > product | オブジェクト | × |  |  |
| Request > notifications > product > id | 文字列 | × | `<=` 128 文字。空にできない。 | 製品 ID。 |
| Request > notifications > product > categoryId | 文字列 | × | `<=` 128 文字。空にできない。 | カテゴリ ID. |
| Request > notifications > id | 文字列 | ○ | `<=` 200 文字。 | 通知 ID は応答で返され、通知が正常に処理されたことを示す。 |
| Request > notifications > impressionId | 文字列 | × | `<= 128` 文字。 | インプレッション ID が、現在の通知を以前の通知とスティッチ（リンク）したり、リクエストを実行したりするのに使用される。それらの両方が一致する場合、2 番目以降のクエストはアクティビティまたはエクスペリエンスに新しいインプレッションを生成しません。 |
| Request > notifications > type | 文字列 | ○ | 「click」または「display」がサポートされる。 | 通知タイプ。 |
| Request > notifications > timestamp | 数値 `<int64>` | ○ |  | UNIX エポックから経過したミリ秒で示す通知のタイムスタンプ。 |
| Request > notifications > tokens | 文字列の配列 | ○ |  | 通知のタイプに基づく、表示されたコンテンツまたはクリックされたセクターのトークンのリスト。 |
| Request > notifications > mbox | オブジェクト | × |  | mbox の通知。 |
| Request > notifications > mbox > name | 文字列 | × | 空の値は許可されない。<br>許可される文字：この表の後にある注意を参照。 | mbox 名。 |
| Request > notifications > mbox > state | 文字列 | × |  | mbox 状態トークン。 |
| Request > notifications > view | オブジェクト | × |  |  |
| Request > notifications > view > id | 整数 `<int64>` | × |  | ビュー ID。ビューがビュー API で作成された際にビューに割り当てられた ID。 |
| Request > notifications > view > name | 文字列 | × | `<= 128` 文字。 | ビューの名前。 |
| Request > notifications > view > key | 文字列 | × | `<=` 512 文字。 | ビューキー。API でビューに設定されたキー。 |
| Request > notifications > view > state | 文字列 | × |  | ビュー状態トークン。 |

**注意**:次の文字は次のとおりです *not* 許可される `Request > notifications > mbox > name`:

```
- '-, ./=`:;&!@#$%^&*()+|?~[]{}'
```

## プリフェッチされた mbox のレンダリング後の sendNotifications() 呼び出し

```javascript
function createTokens(options) {
  return options.map(e => e.eventToken);
}

function createNotification(mbox, type, tokens) {
  const id = 11111; // here we should use a random ID like UUID
  const timestamp = Date.now();
  const { name, state, parameters, profileParameters, order, product } = mbox;
  const result = {
    id,
    type,
    timestamp,
    parameters,
    profileParameters,
    order,
    product
  };

  result.mbox = { name, state };
  result.tokens = tokens;

  return result;
}

adobe.target.getOffers({
  request: {
    prefetch: {
      mboxes: [
        {
          index: 0,
          name: "a1-serverside-ab"
        }
      ]
    }
  }
})
.then(response => {
  const mboxes = response.prefetch.mboxes;
  const notifications = mboxes.map(mbox => {
    const type = "display";
    const tokens = createTokens(mbox.options);

    return createNotification(mbox, type, tokens);
  });
  
  adobe.target.sendNotifications({
    request: { notifications }
  });
})
```

>[!NOTE]
>
>Adobe Analytics、プリフェッチのみの `getOffers()` および `sendNotifications()` を使用している場合、Analytics リクエストは、`sendNotifications()` が実行された後におこなう必要があります。この目的は、`sendNotifications()` によって生成された SDID が Analytics および Target に送信された SDID と一致するようにするためです。
