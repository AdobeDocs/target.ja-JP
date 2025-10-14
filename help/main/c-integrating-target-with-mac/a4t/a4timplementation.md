---
keywords: A4T;Adobe Analytics;Analytics ベースのアクティビティ；Analytics レポートスイート；レポートスイート；Analytics Target の統合；レポートスイートの設定；at.js;atjs;adobe experience platform web sdk;aep web sdk;platform web sdk
description: AdobeおよびAdobe Analytics ソリューションに Analytics for [!DNL Target]  （A4T）を実装するために必要  [!DNL Target]  手順に従います。
title: Analytics for [!DNL Target]  （A4T）の実装方法
feature: Analytics for Target (A4T)
exl-id: b5269b9e-01ef-449a-bb03-3dcc2cd68af7
source-git-commit: ddfb06a17a24200b2aa4f01d370cc0e92ff5f180
workflow-type: tm+mt
source-wordcount: '1055'
ht-degree: 18%

---

# Analytics for [!DNL Target] の実装

[!DNL Adobe Analytics] を [!DNL Adobe Target] のレポートソースとして実装する場合（A4T）は、いくつかの手順が必要です。 プロセスは、A4T を [[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja) で実装するか at.js で実装するかによって異なります。

## ![Adobe Experience Platform Web SDK バッジ &#x200B;](/help/main/assets/platform.png)Adobe Experience Platform Web SDK実装の実装手順 {#platform}

次の節では、Platform Web SDKを使用する予定がある場合に、この統合をサイトにデプロイするために必要な手順を説明します。

### 手順 1:[!DNL Analytics] および [!DNL Target] のプロビジョニングをリクエスト

A4T を実装する前に、[!DNL Analytics] と [!DNL Target] をプロビジョニングする必要があります。 [&#x200B; このフォームを使用して、プロビジョニングをリクエストします &#x200B;](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y)。

### 手順 2： ユーザー権限を設定します。

[!DNL Analytics] の [!DNL Target] に基づいてアクティビティを作成するには、ユーザーアカウントの要件を満たす必要があります。 [&#x200B; ユーザー権限の要件 &#x200B;](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md) を参照してください。

### 手順 3:Edge設定の作成

エッジ設定ツールを使用して、[!DNL Adobe Experience Platform] を使用してEdge設定を作成します。 [&#x200B; データストリームの作成と設定 &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=ja) を設定します。

### 手順 4:Platform Web SDKをインストールして設定する

[!DNL Target] エクスペリエンスの配信を開始し、トラッキングと分析の目的で [!DNL Analytics] を適用するには、サイトページに Platform Web SDKを [&#x200B; インストール &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=ja) および [&#x200B; 設定 &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=ja) します。

### 手順 5:A4T を使用するためのオプションを有効にする

[!DNL Target] の UI で、**[!UICONTROL Administration]**/**[!UICONTROL Visual Experience Composer]** をクリックし、**[!UICONTROL Select per activity]** または **[!UICONTROL Adobe Analytics]** を選択します。

* **[!UICONTROL Select per activity]** 各アクティビティの作成時に、[!DNL Target] から [!DNL Analytics] のいずれかを選択できます。
* **[!UICONTROL Adobe Analytics]** は、作成するすべてのアクティビティのレポートソースとして [!DNL Analytics] を設定します。

## ![at.js バッジ &#x200B;](/help/main/assets/atjs.png)at.js 実装の実装手順{#section_73961BAD5BB4430A95E073DE5C026277}

次の節では、at.js を使用する予定の場合に、この統合をサイトにデプロイするために必要な手順を説明します。

### 手順 1:Analytics と Target のプロビジョニングリクエスト

[!DNL Analytics] を [!DNL Target] のレポートソースとして実装したら、[!DNL Analytics] と [!DNL Target] をプロビジョニングする必要があります。 [&#x200B; このフォームを使用して、プロビジョニングをリクエストします &#x200B;](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank}。

### 手順 2： ユーザー権限を設定します。

[!DNL Analytics] で [!DNL Target] ベースのアクティビティを作成するには、ユーザーアカウントの要件を満たす必要があります。 [&#x200B; ユーザー権限の要件 &#x200B;](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md) を参照してください。

### 手順 3： Experience Cloud 訪問者 ID サービスを導入します。

訪問者 ID サービスを使用すると、ソリューションをまたいでユーザー [!DNL Adobe Experience Cloud] 識別できます。 を実装するか、必要なバージョンのExperience Cloud訪問者 ID に移行します。 詳しくは、[実装する前に](/help/main/c-integrating-target-with-mac/a4t/before-implement.md)の「導入に必要な条件」を参照してください。

[2&rbrace;Experience Cloud訪問者 ID サービス &#x200B;](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-target.html?lang=ja) ドキュメントの Target のExperience Cloud ID サービスの実装 *を参照してください。*

### 手順 4： AppMeasurement for JavaScript または s_code を更新します。

appMeasurement.js を実装するか、必要なバージョンに移行します。 詳しくは、[実装する前に](/help/main/c-integrating-target-with-mac/a4t/before-implement.md)の「導入に必要な条件」を参照してください。

新規実装については、{Analytics 実装ガイド [&#x200B; の &#x200B;](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html?lang=ja)0}JavaScript実装の概要 *を参照してください。*

移行については、[Analytics 実装ガイド &#x200B;](https://experienceleague.adobe.com/docs/analytics/implementation/js/migrate-from-hcode.html?lang=ja) の *JavaScript用AppMeasurementへの移行* を参照してください。

### 手順 5:at.js のダウンロードとアップデート

実稼動アカウントを使用して、at.js を実装するか、必要なバージョンに移行します。 コードの修正は必要ありません。

詳しくは、[実装する前に](/help/main/c-integrating-target-with-mac/a4t/before-implement.md)の「導入に必要な条件」を参照してください。

### 手順 6:at.js のホスト

以前に at.js をデプロイした場合は、既存のファイルを更新後のバージョンに置き換えることができます。 詳しくは、[実装する前に](/help/main/c-integrating-target-with-mac/a4t/before-implement.md)の「導入に必要な条件」を参照してください。

配置していない場合は、最新のファイルを Visitor ID サービスおよび AppMeasurement for JavaScript のファイルとともにホストします。これらのファイルは、サイトのすべてのページからアクセス可能な Web サーバーでホストする必要があります。これらのファイルへのパスを、次の手順で使用します。

### 手順 7：すべてのサイトページから at.js を参照する {#step7}

各ページのタグに次のコード行を追加して、VisitorAPI.js の下に at.js を含めます。

at.js の場合：

```javascript
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

VisitorAPI.js は at.js より前に読み込む必要があります。 既存の at.js ファイルを更新する場合は、必ず読み込み順序を確認してください。

実装の観点から見ると、[!DNL Target] と [!DNL Analytics] の統合のデフォルト設定は、ページから渡された SDID を使用して、[!DNL Target] と [!DNL Analytics] のリクエストをバックエンドで自動的に結合します。

レポートの目的で、[!DNL Target] に関連する分析データを [!DNL Analytics] に送信する方法とタイミングを制御できます。 [!DNL Target] を使用するデフォルト設定のオプトインを希望せず、SDID を介して [!DNL Analytics] が自動的に分析データをステッチする場合は、**window.targetGlobalSettings** から **analyticsLogging = client_side** を設定します。 注意：2.1 未満のバージョンでは、この方法をサポートしていません。

次に例を示します。

```javascript
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

この設定はグローバルな影響を及ぼします。つまり、at.js によっておこなわれるすべての呼び出しには、**リクエスト内で** analyticsLogging: &quot;client_side&quot;[!DNL Target] が送信され、すべてのリクエストに対して分析ペイロードが返されます。 このオプションを設定すると、返されるペイロードの形式は次のようになります。

```javascript
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

その後、ペイロードは [Data Insertion API](https://helpx.adobe.com/jp/analytics/kb/data-insertion-api-post-method-adobe-analytics.html) を介して Analytics に転送できます。 自動配分および自動ターゲット アクティビティの場合、sessionId を転送する必要もあります。 詳しくは、[Adobe Target SDK](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/integration/a4t-reporting.html?lang=ja){target=_blank} ガイドの *Analytics for Target （A4T）レポート* を参照してください。

グローバル設定を使用しない場合でよりオンデマンドのアプローチを使用したい場合は、at.js 関数 [getOffers （） &#x200B;](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/adobe-target-getoffers-atjs-2.html?lang=ja){target=_blank} を使用して **analyticsLogging: &quot;client_side&quot;** を渡します。 Analytics のペイロードはこの呼び出しにのみ返され、[!DNL Target] のバックエンドはペイロードを [!DNL Analytics] に転送しません。 このアプローチに従うと、すべての at.js [!DNL Target] リクエストは、デフォルトでペイロードを返しますが、必要に応じて指定した場合にのみ返されます。

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

その後、ペイロードは [&#x200B; Data Insertion API](https://helpx.adobe.com/jp/analytics/kb/data-insertion-api-post-method-adobe-analytics.html) を介して [!DNL Analytics] に転送できます。

### 手順 8： 実装を検証します。 {#step8}

JavaScript ライブラリを更新した後にページを読み込み、`mboxMCSDID` 呼び出しの [!DNL Target] パラメーター値が `sdid` のページビュー呼び出しの [!DNL Analytics] パラメーター値と一致することを確認します。

呼び出しの順序が常に予測可能とは限らない単一ページアプリケーション（SPA）では、これらの値が一致することを確認することが特に重要です。

>[!NOTE]
>
>A4T が正しく機能するには、これらの値の一致が必要です。

### 手順 9： （オプション）以前の統合コードを削除します。

Adobeでは、以前の統合を削除して実装を簡素化し、システム間の不一致を整理する必要をなくすことをお勧めします。 `mboxLoadSCPlugin` など、以前の SC から T&amp;T への統合にデプロイしたコードはすべて削除できます。

### 手順 10： Analytics を Target のレポートソースとして使用するためのオプションを有効にします。

[!DNL Target] で、「**[!UICONTROL Administration > Reporting]**」をクリックし、**[!UICONTROL Select per activity]** または **[!UICONTROL Adobe Analytics]** を選択してオプションを有効にします。

* **[!UICONTROL Select per activity]** 各アクティビティの作成時に、[!DNL Target] から [!DNL Analytics] のいずれかを選択できます。
* **[!UICONTROL Adobe Analytics]** は、作成するすべてのアクティビティのレポートソースとして [!DNL Analytics] を設定します。


