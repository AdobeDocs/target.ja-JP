---
keywords: qa、server side、server- side、preview、リンクのプレビュー
description: Adobe [!DNL Target]のQA URLをサーバーサイド配信と共に使用して、変更されないプレビューリンク、オプションのオーディエンスターゲティング、ライブアクティビティデータからセグメント化されたままのQA レポートを使用して、簡単なエンドツーエンドのアクティビティ QAを実行する方法について説明します。
title: 使用サーバーサイド配信でアクティビティ QAを実行できますか？
feature: Activities
exl-id: eb6965be-92a6-452d-ac01-7ae1533239cc
TQID: 'https://experienceleague.adobe.com/zZJmFqpXtAigTiEWMZhRqXBJqvG3ANLussSPE3-NoDA'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: 6efa6b7a-8062-5c41-aef4-b4853cc306ae
    internal-label: Activities
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 0a683f6e68bb7481b9e45c91a275a46b84a1ffd8
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 18%
---
# アクティビティ QA とサーバー側配信の使用 {#qa-server-side}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、`pageUrl`が利用できない場合にアクティビティをテストできるように、サーバーサイド [!DNL Adobe Target]呼び出しでアクティビティ QA パラメーターを渡す方法について説明します。

>[!ENDSHADEBOX]

Activity QAの標準実装では、`pageUrl`個のパラメーターを介して`qa_mode`個のパラメーターを渡すことがサポートされています。 この方法は、標準/ajax [!DNL Target]呼び出しに便利です。 ただし、`pageUrl`が使用できないMobile SDKの実装などのサーバー間の呼び出しには適していません。 このような場合は、リクエスト自体にQA パラメーターを渡します。これにより、ライブアクティビティデータからセグメント化された同じプレビューリンク、オプションのオーディエンスターゲティング、QA レポートが保持されます。

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

次の表に、サーバーサイドリクエストのパラメーターを示します。

| パラメーター | タイプ | デフォルト値 | 説明 |
|--- |--- |--- |--- |
| token | 暗号化トークン | なし。 空にすることはできません。 | Activity QAで実行できるアクティビティ IDのリストを含む暗号化されたエンティティ。<br>検証ルール：トークンは、[!DNL Target]要求で指定されたクライアントに属する暗号化されたトークンである必要があります。 トークンで指定されたすべてのアクティビティは、クライアントに属している必要があります。 |
| bypassEntryAudience | ブール値 | False | QA アクティビティのエントリ ステップ ターゲットを評価するか、一致と見なすかを指定します。 |
| listedActivitiesOnly | ブール値 | False | QA アクティビティを単独で実行するか、現在の環境のアクティブなアクティビティとして評価するかを指定します。 |
| evaluateAsTrueAudienceIds | ID のリスト | 空のリスト | [!DNL Target] リクエストの範囲で常にtrueとして評価されるオーディエンス IDのリスト。 |
| evaluateAsFalseAudienceIds | ID のリスト | 空のリスト | [!DNL Target] リクエストの範囲で常にfalseとして評価されるオーディエンス IDのリスト。 |
| activityIndex | 整数 | Null. 空にすることはできません。 | 暗号化トークン内のアクティビティのインデックスです。 `activityIndex`がnullであるか、トークン内のアクティビティの境界から外れている場合、それは無視されます。 インデックスは1.<br>検証ルールで始まります。少なくとも1つのアクティビティインデックスが必要で、トークンで指定されたアクティビティを参照する必要があります。 |
| experienceIndex | 整数 | Null | このパラメーターを指定すると、アクティビティ定義内のインデックスを基準にしてエクスペリエンスが選択されます。 指定しないか範囲外の場合は、アクティビティのエクスペリエンスセレクター戦略にフォールバックします。 インデックスは1.<br>検証ルールで始まります。値はnullにすることも、アクティビティ内のエクスペリエンスを参照する必要があります。 |
