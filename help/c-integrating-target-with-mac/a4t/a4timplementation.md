---
keywords: A4T;Adobe Analytics;Analytics-based activity;Analytics report suite;report suite;Analytics Target integration;configure report suite
description: Adobe Analytics を Target のレポートソースとして実装する場合（A4T）には、いくつかの手順が必要になります。
title: Analytics for Target の実装
feature: null
uuid: da6498c8-1549-4c36-ae42-38c731a28f08
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '879'
ht-degree: 62%

---


# Analytics for Target の実装{#analytics-for-target-implementation}

Several steps are required when implementing [!DNL Adobe Analytics] as the reporting source for [!DNL Target] (A4T).

## Implementation steps {#section_73961BAD5BB4430A95E073DE5C026277}

次の節では、この統合をサイトに導入するために必要な手順について説明します。

## 手順1:Analyticsとターゲットのプロビジョニングのリクエスト

After you implement [!DNL Analytics] as the reporting source for [!DNL Target], you must be provisioned for [!DNL Analytics] and [!DNL Target]. [プロビジョニングの依頼にはこのフォームを使用します](http://www.adobe.com/go/audiences)。

## 手順 2： ユーザー権限を設定します。

User account requirements must be met before you can create an [!DNL Analytics]-based activity in [!DNL Target]. See [User permission requirements](/help/c-integrating-target-with-mac/a4t/account-reqs.md).

## 手順 3： Experience Cloud 訪問者 ID サービスを導入します。

訪問者 ID サービスによって、[!DNL Adobe Experience Cloud] ソリューション全体でユーザーを特定することができます。Experience Cloud 訪問者 ID の必要なバージョンを実装するか、そのバージョンに移行する必要があります。詳しくは、[実装する前に](/help/c-integrating-target-with-mac/a4t/before-implement.md)の「導入に必要な条件」を参照してください。

See [Implement the Experience Cloud ID Service for Target](https://docs.adobe.com/content/help/en/id-service/using/implementation-guides/setup-target.html) in the *Experience Cloud Visitor ID Service* documentation.

## 手順 4： AppMeasurement for JavaScript または s_code を更新します。

appMeasurement.js の必要なバージョンを実装するか、そのバージョンに移行する必要があります。詳しくは、[実装する前に](/help/c-integrating-target-with-mac/a4t/before-implement.md)の「導入に必要な条件」を参照してください。

新規導入の場合は、『 [Analytics導入ガイド』の](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/javascript-implementation-overview.html) 「JavaScript導入の概要 *」を参照してください*。

移行については、 [Analytics導入ガイドのJavaScript版AppMeasurementへの](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs-migrate.html) 移行を参照してください **。

## 手順 5：at.js または mbox.js をダウンロードして更新します。

実稼動アカウントで使用する at.js または mbox.js の必要なバージョンを実装するか、そのバージョンに移行する必要があります。コードの修正は必要ありません。

詳しくは、[実装する前に](/help/c-integrating-target-with-mac/a4t/before-implement.md)の「導入に必要な条件」を参照してください。

## 手順 6： at.js または mbox.js をホストします。

at.js または mbox.js を事前にデプロイしている場合、既存のファイルを最新版に置き換えられます。詳しくは、[実装する前に](/help/c-integrating-target-with-mac/a4t/before-implement.md)の「導入に必要な条件」を参照してください。

配置していない場合は、最新のファイルを Visitor ID サービスおよび AppMeasurement for JavaScript のファイルとともにホストします。これらのファイルは、サイトのすべてのページからアクセス可能な Web サーバーでホストする必要があります。これらのファイルへのパスを、次の手順で使用します。

## 手順 7： サイトのすべてのページから at.js または mbox.js を参照します。 {#step7}

各ページのタグ内に以下のコードを追加して、VisitorAPI.js の下に at.js または mbox.js を含めます。

at.js の場合：

```
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

mbox.js の場合：

```
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/mbox.js"></script>
```

VisitorAPI.js は、at.js や mbox.js より先に読み込まれている必要があります。既存の at.js や mbox.js ファイルを更新中の場合、読み込む順序を必ず確認してください。

The way the out-of-the-box settings are configured for [!DNL Target] and [!DNL Analytics] integration from an implementation perspective is to use the SDID that is passed from the page to stitch the [!DNL Target] and [!DNL Analytics] request together on the backend automatically for you.

However, if you want more control on how and when to send analytics data related to [!DNL Target] to [!DNL Analytics] for reporting purposes, and you do not want to opt-in to the default settings of having [!DNL Target] and [!DNL Analytics] automatically stitch the analytics data via the SDID, then you can set **analyticsLogging = client_side** via **window.targetGlobalSettings**. 注意：2.1 未満のバージョンでは、この方法をサポートしていません。

次に例を示します。

```
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

この設定は全体的に影響します。つまり、at.js によっておこなわれた各呼び出しには、 リクエストと共に送信された **analyticsLogging: &quot;client_side&quot;** があり、各リクエストに対して分析ペイロードが返されます。[!DNL Target]これが設定された場合、返されるペイロードの形式は、以下のようになります。

```
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

ペイロードは、 [Data Insertion APIを介してAnalyticsに転送できます](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)。

グローバル設定は望まず、よりオンデマンドな方法が好ましい場合は、at.js 関数 [getOffers()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) を使用して、**analyticsLogging: &quot;client_side&quot;** に渡すことでこれを実現します。The analytics payload will be returned for only this call and the [!DNL Target] backend will not forward the payload to [!DNL Analytics]. By pursuing this approach, every at.js [!DNL Target] request will not return the payload by default, but instead only when desired and specified.

次に例を示します。

```
adobe.target.getOffers({
      request: {
        experienceCloud: {
          analytics: {
            logging: "client_side"
          }
        },
        prefetch: {
          mboxes: [{
            index: 0,
            name: "a1-serverside-xt"
          }]
        }
      }
    })
    .then(console.log)
```

この呼び出しは、分析ペイロードを抽出できる応答を呼び出します。

応答は以下のようになります。

```
{
  "prefetch": {
    "mboxes": [{
      "index": 0,
      "name": "a1-serverside-xt",
      "options": [{
        "content": "<img src=\"http://s7d2.scene7.com/is/image/TargetAdobeTargetMobile/L4242-xt-usa?tm=1490025518668&fit=constrain&hei=491&wid=980&fmt=png-alpha\"/>",
        "type": "html",
        "eventToken": "n/K05qdH0MxsiyH4gX05/2qipfsIHvVzTQxHolz2IpSCnQ9Y9OaLL2gsdrWQTvE54PwSz67rmXWmSnkXpSSS2Q==",
        "responseTokens": {
          "profile.memberlevel": "0",
          "geo.city": "bucharest",
          "activity.id": "167169",
          "experience.name": "USA Experience",
          "geo.country": "romania"
        }
      }],
      "analytics": {
        "payload": {
          "pe": "tnt",
          "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
        }
      }
    }]
  }
}
```

ペイロードは、 [!DNL Analytics] Data Insertion API [を介してに転送できます](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)。

## 手順 8：実装を検証します。{#step8}

JavaScript ライブラリを更新した後でページをロードして、 呼び出しの `mboxMCSDID`[!DNL Target] パラメーター値が ページビュー呼び出しの `sdid`[!DNL Analytics] パラメーター値と一致していることを確認します。

これは、呼び出しの命令が常に予測可能なわけではないシングルページアプリケーション（SPA）で確認することが特に重要です。

**注意：** A4T が正常に機能するために、これらの値が一致している必要があります。

## 手順 9： （オプション）以前の統合コードを削除します。

実装を簡単にし、異なるシステム間の不一致を解消する手間を省くために、以前の統合を削除することをお勧めします。以前の SC から T&amp;T への統合のために設定したコードを、`mboxLoadSCPlugin` を含めてすべて削除します。

## 手順 10： Analytics を Target のレポートソースとして使用するためのオプションを有効にします。

In [!DNL Target], click **[!UICONTROL Administation > Visual Experience Composer]** and choose either **[!UICONTROL Select per activity]** or **[!UICONTROL Adobe Analytics]** to enable the options.

* **[!UICONTROL 「アクティビティごとに選択」を選択すると、各アクティビティの作成時に か かを選択できます。]**[!DNL Target][!DNL Analytics]
* **[!UICONTROL 「Adobe 」を選択すると、作成したすべてのアクティビティのレポートソースが Analytics に設定されます。]**[!DNL Analytics]

