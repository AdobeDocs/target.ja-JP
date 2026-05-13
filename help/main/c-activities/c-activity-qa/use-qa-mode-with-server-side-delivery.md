---
keywords: qa、server side、server- side、preview、リンクのプレビュー
description: Adobe [!DNL Target] QA URLとサーバーサイド配信を使用して、変更のないプレビューリンク、オプションのオーディエンスターゲティング、ライブアクティビティデータからセグメント化された状態のQA レポートを使用して、簡単なエンドツーエンドのアクティビティ QAを実行する方法について説明します。
title: 使用サーバーサイド配信でアクティビティ QAを実行できますか？
feature: Activities
exl-id: eb6965be-92a6-452d-ac01-7ae1533239cc
TQID: https://experienceleague.adobe.com/zZJmFqpXtAigTiEWMZhRqXBJqvG3ANLussSPE3-NoDA
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 408
ht-degree: 47%

---

# アクティビティ QA とサーバー側配信の使用

[!DNL Adobe Target]のサーバーサイド配信でQA URLを使用すると、変更のないプレビューリンク、オプションのオーディエンスターゲティング、ライブアクティビティデータからセグメント化されたままのQA レポートを使用して、簡単なエンドツーエンドのアクティビティ QAを実行できます。

Activity QAの標準実装では、`pageUrl`個のパラメーターを介して`qa_mode`個のパラメーターを渡すことがサポートされています。 この方法は、標準/ajax [!DNL Target]呼び出しに便利です。 ただし、サーバー間呼び出しの場合、`pageUrl` を利用できないときに Mobile SDK を使用する方法としては最適ではありません。

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
| token | 暗号化トークン | なし。<br>空にすることはできません。 | Activity QAで実行できるアクティビティ IDのリストを含む暗号化されたエンティティ。<br>検証ルール：[!DNL Target] リクエストで指定されたクライアントに属する暗号化されたトークンである必要があります。 トークンで指定されているすべてのアクティビティがこのクライアントに属している必要があります。 |
| bypassEntryAudience | ブール値 | False | QA アクティビティのエントリステップターゲットを評価する必要があるかどうか、またはマッチングと見なす必要があるかどうかを指定します。 |
| listedActivitiesOnly | ブール値 | False | QA アクティビティを別個に実行する必要があるかどうか、または現在の環境のアクティブなアクティビティとして評価する必要があるかどうかを指定します。 |
| evaluateAsTrueAudienceIds | ID のリスト | 空のリスト。 | [!DNL Target] リクエストの範囲で常にtrueとして評価する必要があるオーディエンス IDのリスト。 |
| evaluateAsFalseAudienceIds | ID のリスト | 空のリスト。 | [!DNL Target] リクエストの範囲で常にfalseとして評価する必要があるオーディエンス IDのリスト。 |
| activityIndex | 整数 | Null.<br>空にすることはできません。 | 暗号化トークン内のアクティビティのインデックスです。 activityIndex がトークン内のアクティビティの範囲外にある場合、または null の場合は、無視されます。 インデックスは1から始まります。<br>検証ルール：少なくとも1つのアクティビティインデックスである必要があり、トークンで指定されたアクティビティを参照する必要があります。 |
| experienceIndex | 整数 | Null。 | このパラメーターを指定すると、アクティビティ定義内のインデックスを基準にしてエクスペリエンスが選択されます。 このパラメーターが指定されていない場合、または範囲外にある場合は、アクティビティのエクスペリエンスセレクター戦略が代わりに使用されます。 インデックスは1つの検証ルールで始まります。nullにすることも、アクティビティのエクスペリエンスを参照することもできます。 |
