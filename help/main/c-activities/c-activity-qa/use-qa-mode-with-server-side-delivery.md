---
keywords: qa、server side、server- side、preview、リンクのプレビュー
description: Adobe [!DNL Target] QA URL をサーバーサイド配信で使用して、変更されないプレビューリンク、オプションのオーディエンスのターゲット設定、ライブアクティビティデータからセグメント化されたままの QA レポートで、簡単なエンドツーエンドのアクティビティ QA を実行する方法を説明します。
title: 使用アクティビティ QA をサーバーサイド配信で実行できますか？
feature: Activities
exl-id: eb6965be-92a6-452d-ac01-7ae1533239cc
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 59%

---

# アクティビティ QA とサーバー側配信の使用

のサーバーサイド配信で QA URL を使用して、変更のないプレビューリンク、オプションのオーディエンスのターゲティング、ライブアクティビティデータからセグメント化されたままの QA レポートで、簡単なエンドツーエンドのアクティビティ QA を実行で [!DNL Adobe Target] ます。

アクティビティ QA の標準実装では、パラメーターを介してパラメーター `qa_mode` 渡すこと `pageUrl` サポートされています。 この方法は、標準/ajax [!DNL Target] 呼び出しに便利です。 ただし、サーバー間呼び出しの場合、`pageUrl` を利用できないときに Mobile SDK を使用する方法としては最適ではありません。

次のコードサンプルに、サーバー側呼び出しでのアクティビティ QA を示します。

```json
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
| token | 暗号化トークン | None.<br>空にすることはできません。 | アクティビティ QA で実行できるアクティビティ ID のリストを含む、暗号化されたエンティティです。<br> 検証ルール：[!DNL Target] リクエストで指定されたクライアントに属する暗号化されたトークンである必要があります。 トークンで指定されているすべてのアクティビティがこのクライアントに属している必要があります。 |
| bypassEntryAudience | ブール値 | False | QA アクティビティのエントリステップターゲットを評価する必要があるかどうか、またはマッチングと見なす必要があるかどうかを指定します。 |
| listedActivitiesOnly | ブール値 | False | QA アクティビティを別個に実行する必要があるかどうか、または現在の環境のアクティブなアクティビティとして評価する必要があるかどうかを指定します。 |
| evaluateAsTrueAudienceIds | ID のリスト | 空のリスト。 | [!DNL Target] リクエストの範囲で常に true と評価される必要があるオーディエンス ID のリスト。 |
| evaluateAsFalseAudienceIds | ID のリスト | 空のリスト。 | [!DNL Target] リクエストのスコープで常に false と評価される必要があるオーディエンス ID のリスト。 |
| activityIndex | 整数 | Null。<br>空にすることはできません。 | 暗号化トークン内のアクティビティのインデックスです。activityIndex がトークン内のアクティビティの範囲外にある場合、または null の場合は、無視されます。インデックスは 1 から開始されます。<br>検証ルール：1 つ以上のアクティビティインデックスが指定され、トークンで指定されているアクティビティが参照されていなければなりません。 |
| experienceIndex | 整数 | Null。 | このパラメーターを指定すると、アクティビティ定義内のインデックスを基準にしてエクスペリエンスが選択されます。このパラメーターが指定されていない場合、または範囲外にある場合は、アクティビティのエクスペリエンスセレクター戦略が代わりに使用されます。インデックスが 1 つの検証ルールで始まる：Null を指定するか、アクティビティのエクスペリエンスを参照する必要があります。 |
