---
keywords: A4T;Adobe Analytics;Analyticsベースのアクティビティ；Analyticsレポートスイート；レポートスイート；Analytics Target統合；レポートスイートの設定；at.js;atjs;adobe experience platform web sdk;aep web sdk；プラットフォームWeb sdk
description: ' [!DNL Target] (A4T) in your Adobe [!DNL Target] およびAdobe Analyticsソリューション用にAnalyticsを実装するために必要な手順に従います。'
title: Analytics for [!DNL Target] (A4T)を実装する方法を教えてください。
feature: Analytics for Target（A4T）
exl-id: b5269b9e-01ef-449a-bb03-3dcc2cd68af7
source-git-commit: ed4e6715c120fe692c7f3f84f6b869b5ad9bd1b7
workflow-type: tm+mt
source-wordcount: '1164'
ht-degree: 22%

---

# [!DNL Target]用Analyticsの実装

[!DNL Adobe Analytics]を[!DNL Adobe Target](A4T)のレポートソースとして実装する場合は、いくつかの手順が必要です。 プロセスは、A4Tを[[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html)で実装するか、at.jsで実装するかによって異なります。

## ![Adobe Experience Platform Web SDKバッ](/help/assets/platform.png) ジAdobe Experience Platform Web SDK実装の実装手順 {#platform}

>[!NOTE]
>
>この記事で説明する[!DNL Adobe Experience Platform Web SDK]実装のA4Tサポートは、[!DNL Platform Web SDK]バージョン2.5.0リリース（2021年5月24日）で利用可能になる予定です。

以下の節では、Platform Web SDKを使用する予定の場合に、この統合をサイトにデプロイするために必要な手順を説明します。

### 手順1:[!DNL Analytics]と[!DNL Target]のプロビジョニングをリクエストします

A4Tを実装する前に、[!DNL Analytics]と[!DNL Target]のプロビジョニングをおこなう必要があります。 [プロビジョニングの依頼にはこのフォームを使用します](https://adobe.allegiancetech.com/cgi-bin/qwebcorporate.dll?idx=X8SVES)。

### 手順 2： ユーザー権限を設定します。

[!DNL Target]の[!DNL Analytics]に基づくアクティビティを作成するには、ユーザーアカウントの要件が満たされている必要があります。 [ユーザー権限の要件](/help/c-integrating-target-with-mac/a4t/account-reqs.md)を参照してください。

### 手順3:Edge設定の作成

エッジ設定ツールを使用して、[!DNL Adobe Experience Platform Launch]を使用してEdge設定を作成します。 [[!DNL Analytics] and [!DNL Target] エッジ設定](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/datastreams.html)を設定します。

### 手順4:Platform Web SDKのインストールと設定

[!DNL Target]エクスペリエンスの配信を開始し、追跡や分析のために[!DNL Analytics]を適用するには、サイトページに[](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html)と[Platform Web SDKを設定](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html)します。

### 手順5:A4T使用のオプションの有効化

[!DNL Target] UIで、**[!UICONTROL 管理]** / **[!UICONTROL Visual Experience Composer]**&#x200B;をクリックし、「**[!UICONTROL アクティビティごとに選択]**」または「**[!UICONTROL Adobe Analytics]**」を選択します。

* **[!UICONTROL 「アクティビティごとに選択」を選択すると、各アクティビティの作成時に か かを選択できます。]**[!DNL Target][!DNL Analytics]
* **[!UICONTROL 「Adobe 」を選択すると、作成したすべてのアクティビティのレポートソースが Analytics に設定されます。]**[!DNL Analytics]

## ![at.jsバッ](/help/assets/atjs.png) ジat.js実装の実装手順{#section_73961BAD5BB4430A95E073DE5C026277}

次の節では、at.jsを使用する予定の場合に、この統合をサイトにデプロイするために必要な手順を説明します。

### 手順1:AnalyticsとTargetのプロビジョニングをリクエストする

[!DNL Analytics]を[!DNL Target]のレポートソースとして実装した後、[!DNL Analytics]と[!DNL Target]のプロビジョニングをおこなう必要があります。 [プロビジョニングの依頼にはこのフォームを使用します](http://www.adobe.com/go/audiences)。

### 手順 2： ユーザー権限を設定します。

[!DNL Target]で[!DNL Analytics]ベースのアクティビティを作成するには、ユーザーアカウントの要件が満たされている必要があります。 [ユーザー権限の要件](/help/c-integrating-target-with-mac/a4t/account-reqs.md)を参照してください。

### 手順 3： Experience Cloud 訪問者 ID サービスを導入します。

訪問者 ID サービスによって、[!DNL Adobe Experience Cloud] ソリューション全体でユーザーを特定することができます。訪問者IDの必要なバージョンを実装するか、Experience Cloudします。 詳しくは、[実装する前に](/help/c-integrating-target-with-mac/a4t/before-implement.md)の「導入に必要な条件」を参照してください。

*Experience Cloud訪問者IDサービス*&#x200B;のドキュメントの[Target用Experience CloudIDサービスの実装](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-target.html)を参照してください。

### 手順 4： AppMeasurement for JavaScript または s_code を更新します。

必要なバージョンのappMeasurement.jsを実装するか、そのバージョンに移行します。 詳しくは、[実装する前に](/help/c-integrating-target-with-mac/a4t/before-implement.md)の「導入に必要な条件」を参照してください。

新しい実装については、『Analytics実装ガイド』の「[JavaScript実装の概要](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html)」を参照してください。**

移行の場合は、『Analytics導入ガイド』の[JavaScript版AppMeasurement](https://experienceleague.adobe.com/docs/analytics/implementation/js/migrate-from-hcode.html)への移行&#x200B;*を参照してください。*

### 手順5:at.jsのダウンロードと更新

実稼動アカウントを使用して、必要なバージョンのat.jsを実装するか、そのバージョンに移行します。 コードの修正は必要ありません。

詳しくは、[実装する前に](/help/c-integrating-target-with-mac/a4t/before-implement.md)の「導入に必要な条件」を参照してください。

### 手順6:at.jsのホスト

以前にat.jsをデプロイしている場合は、既存のファイルを最新バージョンに置き換えます。 詳しくは、[実装する前に](/help/c-integrating-target-with-mac/a4t/before-implement.md)の「導入に必要な条件」を参照してください。

配置していない場合は、最新のファイルを Visitor ID サービスおよび AppMeasurement for JavaScript のファイルとともにホストします。これらのファイルは、サイトのすべてのページからアクセス可能な Web サーバーでホストする必要があります。これらのファイルへのパスを、次の手順で使用します。

### 手順7:サイトのすべてのページからat.jsを参照します。 {#step7}

各ページのタグ内に次のコードを追加して、VisitorAPI.jsの下にat.jsを含めます。

at.js の場合：

```javascript
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

VisitorAPI.jsは、at.jsの前に読み込む必要があります。 既存のat.jsまたはmbox.jsファイルを更新する場合は、必ず読み込み順序を確認してください。

実装の観点から見ると、[!DNL Target]と[!DNL Analytics]統合のデフォルト設定は、ページから渡されたSDIDを使用して、[!DNL Target]リクエストと[!DNL Analytics]リクエストをバックエンドで自動的にステッチすることです。

[!DNL Target]に関連する分析データをレポート目的でいつどのように送信するかを制御できます。 [!DNL Analytics]SDIDを使用して[!DNL Target]と[!DNL Analytics]で分析データを自動的にステッチするデフォルト設定をオプトインしない場合は、**window.targetGlobalSettings**&#x200B;を使用して&#x200B;**analyticsLogging = client_side**&#x200B;を設定します。 注意：2.1 未満のバージョンでは、この方法をサポートしていません。

次に例を示します。

```javascript
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

この設定は全体的に影響します。つまり、at.jsによるすべての呼び出しに&#x200B;**analyticsLogging:[!DNL Target]リクエスト内で送信された「client_side」**&#x200B;と、各リクエストに対して分析ペイロードが返されます。 このオプションを設定すると、返されるペイロードの形式は次のようになります。

```javascript
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

ペイロードは、その後、[Data Insertion API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)を使用してAnalyticsに転送できます。 自動配分および自動ターゲットアクティビティの場合は、 sessionIdも転送する必要があります。 詳しくは、『*Adobe Target SDK*』ガイドの[Analytics for Target(A4T)レポート](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting)を参照してください。

グローバル設定は望ましくなく、よりオンデマンドな方法が望ましい場合は、**analyticsLoggingを渡すことで、at.js関数[getOffers()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md)を使用します。&quot;client_side&quot;**&#x200B;です。 分析ペイロードはこの呼び出しに対してのみ返され、[!DNL Target]バックエンドはペイロードを[!DNL Analytics]に転送しません。 この方法を続行すると、すべてのat.js [!DNL Target]リクエストは、デフォルトでペイロードを返しますが、代わりに、必要に応じて指定した場合に返します。

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

ペイロードは、その後、[Data Insertion API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)を使用して[!DNL Analytics]に転送できます。

### 手順 8： 実装を検証します。 {#step8}

JavaScript ライブラリを更新した後でページをロードして、 呼び出しの `mboxMCSDID`[!DNL Target] パラメーター値が ページビュー呼び出しの `sdid`[!DNL Analytics] パラメーター値と一致していることを確認します。

呼び出しの順序が常に予測可能とは限らないシングルページアプリケーション(SPA)で、これらの値が一致することを確認することが特に重要です。

>[!NOTE]
>
>A4Tが正しく機能するには、これらの値の一致が必要です。

### 手順 9： （オプション）以前の統合コードを削除します。

Adobeでは、実装を簡略化し、システム間の不一致を解消する手間を省くために、以前の統合を削除することをお勧めします。 以前のSCからT&amp;Tへの統合用にデプロイしたコードを、`mboxLoadSCPlugin`を含めてすべて削除できます。

### 手順 10： Analytics を Target のレポートソースとして使用するためのオプションを有効にします。

[!DNL Target]で、**[!UICONTROL 管理/Visual Experience Composer]**&#x200B;をクリックし、「**[!UICONTROL アクティビティごとに選択]**」または「**[!UICONTROL Adobe Analytics]**」を選択してオプションを有効にします。

* **[!UICONTROL 「アクティビティごとに選択」を選択すると、各アクティビティの作成時に か かを選択できます。]**[!DNL Target][!DNL Analytics]
* **[!UICONTROL 「Adobe 」を選択すると、作成したすべてのアクティビティのレポートソースが Analytics に設定されます。]**[!DNL Analytics]


