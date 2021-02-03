---
keywords: qa、server side、server- side、preview、リンクのプレビュー
description: サーバー側の配信でAdobe TargetQA URLを使用して、変更のないプレビューリンク、オプションのオーディエンスターゲット設定、ライブアクティビティデータからセグメント化されたQAレポートを使用して、エンドツーエンドのアクティビティQAを簡単に実行します。
title: アクティビティ QA とサーバー側配信の使用
feature: Activities
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 72%

---


# アクティビティ QA とサーバー側配信の使用

[!DNL Adobe Target]のサーバー側配信でQA URLを使用して、変更のないプレビューリンク、オプションのオーディエンスターゲット設定、実アクティビティデータからセグメント化されたQAレポートを使用して、エンドツーエンドの簡単なアクティビティQAを実行します。

Activity QAの標準実装では、パラメーターによる `qa_mode` `pageUrl` パラメーターの受け渡しがサポートされています。この方法は、標準/ajax [!DNL Target]呼び出しに便利です。 ただし、サーバー間呼び出しの場合、`pageUrl` を利用できないときに Mobile SDK を使用する方法としては最適ではありません。

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
| evaluateAsTrueAudienceIds | ID のリスト | 空のリスト。 | [!DNL Target]要求の範囲で常にtrueと評価されるオーディエンスIDのリスト。 |
| evaluateAsFalseAudienceIds | ID のリスト | 空のリスト。 | [!DNL Target]要求の範囲で常にfalseとして評価される必要があるオーディエンスIDのリスト。 |
| activityIndex | 整数 | Null。<br>空にすることはできません。 | 暗号化トークン内のアクティビティのインデックスです。activityIndex がトークン内のアクティビティの範囲外にある場合、または null の場合は、無視されます。インデックスは 1 から開始されます。<br>検証ルール：1 つ以上のアクティビティインデックスが指定され、トークンで指定されているアクティビティが参照されていなければなりません。 |
| experienceIndex | 整数 | Null。 | このパラメーターを指定すると、アクティビティ定義内のインデックスを基準にしてエクスペリエンスが選択されます。このパラメーターが指定されていない場合、または範囲外にある場合は、アクティビティのエクスペリエンスセレクター戦略が代わりに使用されます。インデックスは 1 から開始されます。検証ルール：null にすることができます。そうでない場合は、アクティビティ内のエクスペリエンスが参照されていなければなりません。 |