---
keywords: qa、server side、server- side、preview、リンクのプレビュー
description: Adobe [!DNL Target] 変更されないプレビューリンク、オプションのオーディエンスターゲティング、ライブアクティビティデータからセグメント化された QA レポートを使用して、簡単にエンドツーエンドのアクティビティ QA を実行できる QA URL です。
title: では、サーバー側配信でアクティビティ QA を実行することはできますか？
feature: Activities
exl-id: eb6965be-92a6-452d-ac01-7ae1533239cc
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 70%

---

# アクティビティ QA とサーバー側配信の使用

でのサーバー側配信での QA URL の使用 [!DNL Adobe Target] 変更されないプレビューリンク、オプションのオーディエンスターゲティング、実際のアクティビティデータからセグメント化された QA レポートを使用して、簡単にエンドツーエンドのアクティビティ QA を実行できます。

Activity QAの標準実装では、パラメーターによる `qa_mode` `pageUrl` パラメーターの受け渡しがサポートされています。この方法は、標準/ajax に便利です [!DNL Target] 呼び出し。 ただし、サーバー間呼び出しの場合、`pageUrl` を利用できないときに Mobile SDK を使用する方法としては最適ではありません。

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
| token | 暗号化トークン | None.<br>空にすることはできません。 | アクティビティ QA で実行できるアクティビティ ID のリストを含む、暗号化されたエンティティです。<br>[!DNL Target]検証ルール： リクエストで指定されたクライアントに属する暗号化トークンでなければなりません。トークンで指定されているすべてのアクティビティがこのクライアントに属している必要があります。 |
| bypassEntryAudience | ブール値 | False | QA アクティビティのエントリステップターゲットを評価する必要があるかどうか、またはマッチングと見なす必要があるかどうかを指定します。 |
| listedActivitiesOnly | ブール値 | False | QA アクティビティを別個に実行する必要があるかどうか、または現在の環境のアクティブなアクティビティとして評価する必要があるかどうかを指定します。 |
| evaluateAsTrueAudienceIds | ID のリスト | 空のリスト。 | のスコープで常に true として評価される必要があるオーディエンス ID のリスト [!DNL Target] リクエスト。 |
| evaluateAsFalseAudienceIds | ID のリスト | 空のリスト。 | のスコープで常に false として評価される必要があるオーディエンス ID のリスト [!DNL Target] リクエスト。 |
| activityIndex | 整数 | Null。<br>空にすることはできません。 | 暗号化トークン内のアクティビティのインデックスです。activityIndex がトークン内のアクティビティの範囲外にある場合、または null の場合は、無視されます。インデックスは 1 から開始されます。<br>検証ルール：1 つ以上のアクティビティインデックスが指定され、トークンで指定されているアクティビティが参照されていなければなりません。 |
| experienceIndex | 整数 | Null。 | このパラメーターを指定すると、アクティビティ定義内のインデックスを基準にしてエクスペリエンスが選択されます。このパラメーターが指定されていない場合、または範囲外にある場合は、アクティビティのエクスペリエンスセレクター戦略が代わりに使用されます。インデックスは 1 から開始されます。検証ルール：null にすることができます。そうでない場合は、アクティビティ内のエクスペリエンスが参照されていなければなりません。 |
