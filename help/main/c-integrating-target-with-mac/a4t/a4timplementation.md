---
keywords: A4T;Adobe Analytics;Analytics ベースのアクティビティ；Analytics レポートスイート；レポートスイート；Analytics Target 統合；レポートスイートの設定；at.js;atjs;adobe experience platform web sdk;aep web sdk;platform web sdk
description: Analytics を実装するために必要な手順に従います。 [!DNL Target] (A4T)Adobe [!DNL Target] およびAdobe Analyticsソリューション
title: Analytics を実装する方法 [!DNL Target] (A4T)?
feature: Analytics for Target (A4T)
exl-id: b5269b9e-01ef-449a-bb03-3dcc2cd68af7
source-git-commit: 231cf7972b7343e02245d12ea9380df8d4b125da
workflow-type: tm+mt
source-wordcount: '1161'
ht-degree: 23%

---

#  Analytics for[!DNL Target]の実装

導入時には、いくつかの手順が必要です。 [!DNL Adobe Analytics] レポートソースとして [!DNL Adobe Target] (A4T)。 プロセスは、 [[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja) または at.js を使用します。

## ![Adobe Experience Platform Web SDK バッジ](/help/main/assets/platform.png) Adobe Experience Platform Web SDK 実装の実装手順 {#platform}

次の節では、Platform Web SDK を使用する予定の場合に、この統合をサイトにデプロイするために必要な手順を説明します。

### 手順 1:のプロビジョニングをリクエスト [!DNL Analytics] および [!DNL Target]

A4T を実装する前に、 [!DNL Analytics] および [!DNL Target]. [プロビジョニングの依頼にこのフォームを使用します](https://adobe.allegiancetech.com/cgi-bin/qwebcorporate.dll?idx=X8SVES).

### 手順 2： ユーザー権限を設定します。

アクティビティを作成する前に、ユーザーアカウントの要件が満たされている必要があります。 [!DNL Analytics] in [!DNL Target]. 詳しくは、 [ユーザー権限の要件](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md).

### 手順 3:Edge 設定の作成

を使用して Edge 設定を作成する [!DNL Adobe Experience Platform] エッジ設定ツールを使用します。 の設定 [[!DNL Analytics] and [!DNL Target] エッジ設定](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/datastreams.html).

### 手順 4:Platform Web SDK のインストールと設定

配信を開始するには [!DNL Target] エクスペリエンスと適用 [!DNL Analytics] 追跡や分析のために [インストール](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html) および [設定](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html) サイトページ上の Platform Web SDK。

### 手順 5:A4T 使用のオプションの有効化

内 [!DNL Target] UI、クリック **[!UICONTROL 管理]** > **[!UICONTROL Visual Experience Composer]**&#x200B;次に、次のいずれかを選択します。 **[!UICONTROL アクティビティごとに選択]** または **[!UICONTROL Adobe Analytics]**.

* **[!UICONTROL 「アクティビティごとに選択」を選択すると、各アクティビティの作成時に か かを選択できます。]**[!DNL Target][!DNL Analytics]
* **[!UICONTROL 「Adobe 」を選択すると、作成したすべてのアクティビティのレポートソースが Analytics に設定されます。]**[!DNL Analytics]

## ![at.js バッジ](/help/main/assets/atjs.png) at.js 実装の実装手順{#section_73961BAD5BB4430A95E073DE5C026277}

次の節では、at.js を使用する予定の場合に、この統合をサイトにデプロイするために必要な手順を説明します。

### 手順 1:Analytics および Target 用のプロビジョニングをリクエストする

導入後 [!DNL Analytics] レポートソースとして [!DNL Target]のプロビジョニングが完了していない場合、 [!DNL Analytics] および [!DNL Target]. [プロビジョニングの依頼にこのフォームを使用します](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank}。

### 手順 2： ユーザー権限を設定します。

ユーザーアカウントの要件を満たしてから、 [!DNL Analytics]のベースとなるアクティビティ [!DNL Target]. 詳しくは、 [ユーザー権限の要件](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md).

### 手順 3： Experience Cloud 訪問者 ID サービスを導入します。

訪問者 ID サービスによって、[!DNL Adobe Experience Cloud] ソリューション全体でユーザーを特定することができます。訪問者 ID の必要なバージョンを実装するか、Experience Cloudに移行します。 詳しくは、[実装する前に](/help/main/c-integrating-target-with-mac/a4t/before-implement.md)の「導入に必要な条件」を参照してください。

詳しくは、 [Experience CloudID サービスの Target への実装](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-target.html) 内 *Experience Cloud訪問者 ID サービス* ドキュメント。

### 手順 4： AppMeasurement for JavaScript または s_code を更新します。

appMeasurement.js の必要なバージョンを実装するか、そのバージョンに移行します。 詳しくは、[実装する前に](/help/main/c-integrating-target-with-mac/a4t/before-implement.md)の「導入に必要な条件」を参照してください。

新規導入の場合は、 [JavaScript 実装の概要](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html) 内 *Analytics 実装ガイド*.

移行の場合は、 [JavaScript 版 AppMeasurement への移行](https://experienceleague.adobe.com/docs/analytics/implementation/js/migrate-from-hcode.html) 内 *Analytics 実装ガイド*.

### 手順 5:at.js のダウンロードと更新

実稼動アカウントを使用して、必要なバージョンの at.js を実装するか、そのバージョンに移行します。 コードの修正は必要ありません。

詳しくは、[実装する前に](/help/main/c-integrating-target-with-mac/a4t/before-implement.md)の「導入に必要な条件」を参照してください。

### 手順 6:at.js をホストします。

以前に at.js をデプロイしている場合は、既存のファイルを最新バージョンに置き換えることができます。 詳しくは、[実装する前に](/help/main/c-integrating-target-with-mac/a4t/before-implement.md)の「導入に必要な条件」を参照してください。

配置していない場合は、最新のファイルを Visitor ID サービスおよび AppMeasurement for JavaScript のファイルとともにホストします。これらのファイルは、サイトのすべてのページからアクセス可能な Web サーバーでホストする必要があります。これらのファイルへのパスを、次の手順で使用します。

### 手順 7:サイトのすべてのページから at.js を参照します。 {#step7}

各ページのタグ内に次のコードを追加して、VisitorAPI.js の下に at.js を含めます。

at.js の場合：

```javascript
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

VisitorAPI.js は at.js の前に読み込む必要があります。 既存の at.js ファイルを更新する場合は、読み込み順序を必ず確認してください。

のデフォルト設定 [!DNL Target] および [!DNL Analytics] 統合は、実装の観点から、ページから渡された SDID を使用して、 [!DNL Target] および [!DNL Analytics] リクエストをバックエンドで自動的におこないます。

分析データを送信する方法とタイミングを制御するには、 [!DNL Target] から [!DNL Analytics] レポート目的で使用します。 デフォルト設定 ( [!DNL Target] および [!DNL Analytics] は、SDID を使用して分析データを自動的にステッチし、 **analyticsLogging = client_side** 経由 **window.targetGlobalSettings**. 注意：2.1 未満のバージョンでは、この方法をサポートしていません。

次に例を示します。

```javascript
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

この設定は全体的に影響します。つまり、at.js によっておこなわれるすべての呼び出しには次のようなものがあります。 **analyticsLogging:&quot;client_side&quot;** 送信される [!DNL Target] リクエストと analytics ペイロードは、リクエストごとに返されます。 このオプションを設定すると、返されるペイロードの形式は次のようになります。

```javascript
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

ペイロードは、その後、 [Data Insertion API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html). 自動配分と自動ターゲットアクティビティの場合は、sessionId も転送する必要があります。 詳しくは、 [Analytics for Target(A4T) レポート](https://developer.adobe.com/target/implement/server-side/sdk-guides/integration-with-experience-cloud/a4t-reporting/){target=_blank} *Adobe Target SDK* ガイド。

グローバル設定は望ましくなく、よりオンデマンドな方法が望ましい場合は、at.js 関数を使用します [getOffers()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffers-atjs-2/){target=_blank} に **analyticsLogging:&quot;client_side&quot;**. 分析ペイロードは、この呼び出しに対してのみ返され、 [!DNL Target] バックエンドはペイロードをに転送しません。 [!DNL Analytics]. このアプローチを続けることで、すべての at.js [!DNL Target] リクエストは、デフォルトではペイロードを返しますが、必要に応じて指定された場合にのみ返します。

次に例を示します。

```javascript
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

```javascript
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

ペイロードは次の場所に転送できます： [!DNL Analytics] 経由 [Data Insertion API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html).

### 手順 8： 実装を検証します。 {#step8}

JavaScript ライブラリを更新した後でページをロードして、 呼び出しの `mboxMCSDID`[!DNL Target] パラメーター値が ページビュー呼び出しの `sdid`[!DNL Analytics] パラメーター値と一致していることを確認します。

呼び出しの順序が常に予測可能とは限らない場合、これらの値がシングルページアプリケーション (SPA) で一致することを確認することが特に重要です。

>[!NOTE]
>
>A4T が正しく機能するには、これらの値の一致が必要です。

### 手順 9： （オプション）以前の統合コードを削除します。

Adobeでは、実装を簡単にし、異なるシステム間の不一致を解消する手間を省くために、以前の統合を削除することをお勧めします。 以前の SC から T&amp;T への統合のために設定したコードを、次のように削除できます。 `mboxLoadSCPlugin`.

### 手順 10： Analytics を Target のレポートソースとして使用するためのオプションを有効にします。

In [!DNL Target]をクリックし、 **[!UICONTROL 管理/レポート]** を選択し、 **[!UICONTROL アクティビティごとに選択]** または **[!UICONTROL Adobe Analytics]** をクリックしてオプションを有効にします。

* **[!UICONTROL 「アクティビティごとに選択」を選択すると、各アクティビティの作成時に か かを選択できます。]**[!DNL Target][!DNL Analytics]
* **[!UICONTROL 「Adobe 」を選択すると、作成したすべてのアクティビティのレポートソースが Analytics に設定されます。]**[!DNL Analytics]


