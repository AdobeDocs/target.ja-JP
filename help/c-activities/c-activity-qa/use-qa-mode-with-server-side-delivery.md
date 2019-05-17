---
description: サーバー側配信と組み合わせて QA URL を利用すると、変更されないプレビューリンク、オプションのオーディエンスのターゲット設定、実際のアクティビティデータとは別に保持されている QA レポートを使用して、簡単なエンドツーエンドのアクティビティ QA を実行できます。
keywords: qa、server side、server- side、preview、リンクのプレビュー
seo-description: サーバー側配信と組み合わせて QA URL を利用すると、変更されないプレビューリンク、オプションのオーディエンスのターゲット設定、実際のアクティビティデータとは別に保持されている QA レポートを使用して、簡単なエンドツーエンドのアクティビティ QA を実行できます。
seo-title: アクティビティ QA とサーバー側配信の使用
solution: 'Target '
title: アクティビティ QA とサーバー側配信の使用
topic: Advanced,Standard,Classic
uuid: c1875243-e37f-4205-9e6b-6e96cadf4a7f
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# アクティビティ QA とサーバー側配信の使用{#use-activity-qa-with-server-side-delivery}

サーバー側配信と組み合わせて QA URL を利用すると、変更されないプレビューリンク、オプションのオーディエンスのターゲット設定、実際のアクティビティデータとは別に保持されている QA レポートを使用して、簡単なエンドツーエンドのアクティビティ QA を実行できます。

Activity QAの標準実装では、mboxパラメーターによる `qa_mode` `pageUrl` パラメーターの受け渡しがサポートされています。これは、標準および ajax mbox 呼び出しに便利な方法です。ただし、サーバー間呼び出しの場合、`pageUrl` を利用できないときに Mobile SDK を使用する方法としては最適ではありません。

次のコードサンプルに、サーバー側呼び出しでのアクティビティ QA を示します。

```
{
  "mbox" : "orderConfirmPage",
  "clientSideAnalyticsLogging": true,
  "clicked" : true,
  "tntId" : "12121212.17_01",
  "order" : {
    ...
  },
  "profileParameters" : {
    ...
  },
  "mboxParameters" : {
    ...
  },
  "requestLocation" : {
    ...
  },
  "qaMode" : {
    "token" : "<encrypted token string>",
    "bypassEntryAudience" : true,
    "listedActivitiesOnly" : true,
    "evaluateAsTrueAudienceIds" : [audienceId1, audienceId2...],
    "evaluateAsFalseAudienceIds" : [audienceId3, audienceId4...],
    "previewIndexes" : [
       {
         "activityIndex" : 1,
         "experienceIndex" : 1
       }
     ],
  },
  "mboxTrace" : true
}
```

次の表は、サーバー側リクエストの詳細をまとめたものです。

| パラメーター | タイプ | デフォルト値 | 説明 |
|--- |--- |--- |--- |
| token | 暗号化トークン | None.<br>空にすることはできません。 | アクティビティ QA で実行できるアクティビティ ID のリストを含む、暗号化されたエンティティです。<br>検証ルール：mbox リクエストで指定されたクライアントに属する暗号化トークンでなければなりません。トークンで指定されているすべてのアクティビティがこのクライアントに属している必要があります。 |
| bypassEntryAudience | ブール値 | False | QA アクティビティのエントリステップターゲットを評価する必要があるかどうか、またはマッチングと見なす必要があるかどうかを指定します。 |
| listedActivitiesOnly | ブール値 | False | QA アクティビティを別個に実行する必要があるかどうか、または現在の環境のアクティブなアクティビティとして評価する必要があるかどうかを指定します。 |
| evaluateAsTrueAudienceIds | ID のリスト | 空のリスト。 | mbox リクエストのスコープ内で常に true として評価する必要があるオーディエンス ID のリストです。 |
| evaluateAsFalseAudienceIds | ID のリスト | 空のリスト。 | mbox リクエストのスコープ内で常に false として評価する必要があるオーディエンス ID のリストです。 |
| activityIndex | 整数 | Null。<br>空にすることはできません。 | 暗号化トークン内のアクティビティのインデックスです。activityIndex がトークン内のアクティビティの範囲外にある場合、または null の場合は、無視されます。インデックスは 1 から開始されます。<br>検証ルール：1 つ以上のアクティビティインデックスが指定され、トークンで指定されているアクティビティが参照されていなければなりません。 |
| experienceIndex | 整数 | Null。 | このパラメーターを指定すると、アクティビティ定義内のインデックスを基準にしてエクスペリエンスが選択されます。このパラメーターが指定されていない場合、または範囲外にある場合は、アクティビティのエクスペリエンスセレクター戦略が代わりに使用されます。インデックスは 1 から開始されます。検証ルール：null にすることができます。そうでない場合は、アクティビティ内のエクスペリエンスが参照されていなければなりません。 |