---
keywords: A4T;Adobe Analytics;Analytics ベースのアクティビティ；Analytics レポートスイート；レポートスイート；Analytics Target統合；レポートスイートの設定；at.js;atjs;adobe experience platform web sdk;aep web sdk;platform web sdk
description: Adobe [!DNL Target] およびAdobe Analytics ソリューションに [!DNL Target]  （A4T）のAnalyticsを実装するために必要な手順に従います。
title: ' [!DNL Target]  （A4T）のAnalyticsを実装するにはどうすればよいですか？'
feature: Analytics for Target (A4T)
exl-id: b5269b9e-01ef-449a-bb03-3dcc2cd68af7
TQID: https://experienceleague.adobe.com/1e51ngQ1R8qogTPpEQ-mNo601s7zq2DGgKi62VhnfYA
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1168
ht-degree: 18%

---

# [!DNL Target]実装用Analytics

[!DNL Adobe Target] （A4T）のレポートソースとして[!DNL Adobe Analytics]を実装する場合は、いくつかの手順が必要です。 プロセスは、[[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja)でA4Tを実装するか、at.jsで実装するかによって異なります。

## ![Adobe Experience Platform Web SDK バッジ &#x200B;](/help/main/assets/platform.png) Adobe Experience Platform Web SDK実装の実装手順 {#platform}

以下の節では、Platform Web SDKを使用する予定の場合に、この統合をサイトにデプロイするために必要な手順について説明します。

### 手順1: [!DNL Analytics]と[!DNL Target]のプロビジョニングをリクエスト

A4Tを実装する前に、[!DNL Analytics]と[!DNL Target]に対してプロビジョニングする必要があります。 [このフォームを使用して、プロビジョニングのリクエストを行います](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y)。

### 手順 2： ユーザー権限を設定します。

[!DNL Target]の[!DNL Analytics]に基づいてアクティビティを作成する前に、ユーザーアカウントの要件を満たす必要があります。 [&#x200B; ユーザー権限の要件](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md)を参照してください。

### 手順3:Edge設定の作成

エッジ設定ツールを使用して、[!DNL Adobe Experience Platform]を使用してEdge設定を作成します。 [&#x200B; データストリームの作成と設定](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=ja)を設定します。

### 手順4:Platform Web SDKのインストールと設定

[!DNL Target] エクスペリエンスの配信を開始し、トラッキングと分析の目的で[!DNL Analytics]を適用するには、[Platform Web SDKをサイトページに](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=ja) インストールし、[設定](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=ja)します。

### 手順5:A4Tを使用するためのオプションを有効にする

[!DNL Target] UIで、**[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer]**&#x200B;をクリックし、**[!UICONTROL Select per activity]**&#x200B;または&#x200B;**[!UICONTROL Adobe Analytics]**&#x200B;のいずれかを選択します。

* **[!UICONTROL Select per activity]**&#x200B;では、各アクティビティの作成時に[!DNL Target]と[!DNL Analytics]のいずれかを選択できます。
* **[!UICONTROL Adobe Analytics]**&#x200B;は、作成するすべてのアクティビティのレポートソースとして[!DNL Analytics]を設定します。

## ![at.js バッジ &#x200B;](/help/main/assets/atjs.png) at.js実装の実装手順{#section_73961BAD5BB4430A95E073DE5C026277}

次の節では、at.jsを使用する予定の場合に、この統合をサイトにデプロイするために必要な手順について説明します。

### 手順1:AnalyticsとTargetのプロビジョニングのリクエスト

[!DNL Analytics]を[!DNL Target]のレポートソースとして実装した後、[!DNL Analytics]と[!DNL Target]に対してプロビジョニングする必要があります。 [このフォームを使用して、プロビジョニングのリクエストを行います](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank}。

### 手順 2： ユーザー権限を設定します。

[!DNL Target]で[!DNL Analytics] ベースのアクティビティを作成する前に、ユーザーアカウントの要件を満たす必要があります。 [&#x200B; ユーザー権限の要件](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md)を参照してください。

### 手順 3： Experience Cloud 訪問者 ID サービスを導入します。

訪問者ID サービスを使用すると、[!DNL Adobe Experience Cloud]個のソリューションでユーザーを識別できます。 必要なバージョンのExperience Cloud訪問者IDを実装するか、移行します。 詳しくは、[実装する前に](/help/main/c-integrating-target-with-mac/a4t/before-implement.md)の「導入に必要な条件」を参照してください。

*Experience Cloud訪問者ID サービス*&#x200B;のドキュメントの「[Experience Cloud ID サービスをTarget](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-target.html?lang=ja)に実装する」を参照してください。

### 手順 4： AppMeasurement for JavaScript または s_code を更新します。

必要なバージョンのappMeasurement.jsを実装または移行します。 詳しくは、[実装する前に](/help/main/c-integrating-target-with-mac/a4t/before-implement.md)の「導入に必要な条件」を参照してください。

新しい実装については、*Analytics実装ガイド*&#x200B;の[JavaScript実装の概要](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html?lang=ja)を参照してください。

移行については、*Analytics実装ガイド*&#x200B;の「[JavaScript版AppMeasurementへの移行](https://experienceleague.adobe.com/docs/analytics/implementation/js/migrate-from-hcode.html?lang=ja)」を参照してください。

### 手順5:at.jsのダウンロードと更新

実稼動アカウントを使用して、必要なバージョンのat.jsを実装または移行します。 コードの修正は必要ありません。

詳しくは、[実装する前に](/help/main/c-integrating-target-with-mac/a4t/before-implement.md)の「導入に必要な条件」を参照してください。

### 手順6:at.jsのホスト

以前にat.jsをデプロイした場合は、既存のファイルを更新されたバージョンに置き換えることができます。 詳しくは、[実装する前に](/help/main/c-integrating-target-with-mac/a4t/before-implement.md)の「導入に必要な条件」を参照してください。

配置していない場合は、最新のファイルを Visitor ID サービスおよび AppMeasurement for JavaScript のファイルとともにホストします。 これらのファイルは、サイトのすべてのページからアクセス可能な Web サーバーでホストする必要があります。 これらのファイルへのパスを、次の手順で使用します。

### 手順7：すべてのサイトページでat.jsを参照する {#step7}

各ページのタグに次のコード行を追加して、VisitorAPI.jsの下にat.jsを含めます。

at.js の場合：

```javascript
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

VisitorAPI.jsは、at.jsの前に読み込む必要があります。 既存のat.js ファイルを更新する場合は、読み込み順序を確認してください。

実装の観点から、[!DNL Target]と[!DNL Analytics]統合のデフォルト設定は、ページから渡されるSDIDを使用して、バックエンドで[!DNL Target]と[!DNL Analytics]のリクエストを自動的に結合することです。

レポート用に[!DNL Target]から[!DNL Analytics]に関連する分析データを送信する方法とタイミングを制御できます。 [!DNL Target]と[!DNL Analytics]がSDIDを介して分析データを自動的に合成するというデフォルト設定をオプトインしない場合は、**window.targetGlobalSettings**&#x200B;を介して&#x200B;**analyticsLogging = client_side**&#x200B;を設定します。 注意：2.1 未満のバージョンでは、この方法をサポートしていません。

次に例を示します。

```javascript
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

この設定にはグローバルな効果があります。つまり、at.jsによって行われたすべての呼び出しには&#x200B;**analyticsLogging: [!DNL Target] リクエスト内で「client_side」**&#x200B;が送信され、分析ペイロードがリクエストごとに返されます。 このオプションを設定すると、返されるペイロードの形式は次のようになります。

```javascript
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

その後、ペイロードは[Data Insertion API](https://helpx.adobe.com/jp/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)を介してAnalyticsに転送できます。 自動配分アクティビティと自動ターゲットアクティビティの場合は、sessionIdも転送する必要があります。 詳しくは、*Adobe Target SDK* ガイドの[Analytics for Target （A4T） レポート &#x200B;](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/integration/a4t-reporting.html?lang=ja){target=_blank}を参照してください。

グローバル設定が望ましくなく、よりオンデマンドなアプローチが望ましい場合は、**analyticsLogging: &quot;client_side&quot;**&#x200B;を渡してat.js関数[getOffers （） &#x200B;](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/adobe-target-getoffers-atjs-2.html){target=_blank}を使用します。 この呼び出しにのみ分析ペイロードが返され、[!DNL Target] バックエンドはペイロードを[!DNL Analytics]に転送しません。 このアプローチを実行すると、すべてのat.js [!DNL Target] リクエストはデフォルトでペイロードを返しますが、必要な場合と指定された場合にのみ返されます。

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

JavaScript ライブラリを更新した後、ページを読み込み、[!DNL Target]呼び出しの`mboxMCSDID` パラメーター値が[!DNL Analytics] ページビュー呼び出しの`sdid` パラメーター値と一致することを確認します。

特に、呼び出しの順序が必ずしも予測可能ではないシングルページアプリケーション（SPA）でこれらの値が一致することを確認することが重要です。

>[!NOTE]
>
>A4Tが正しく機能するためには、これらの値のマッチングが必要です。

### 手順 9： （オプション）以前の統合コードを削除します。

Adobeでは、導入を簡素化し、システム間の不一致を整理する必要がないように、以前の統合を削除することをお勧めします。 以前のSCからT&amp;Tへの統合にデプロイしたコード（`mboxLoadSCPlugin`を含む）を削除できます。

### 手順 10： Analytics を Target のレポートソースとして使用するためのオプションを有効にします。

[!DNL Target]で、**[!UICONTROL Administration > Reporting]**&#x200B;をクリックし、**[!UICONTROL Select per activity]**&#x200B;または&#x200B;**[!UICONTROL Adobe Analytics]**&#x200B;のいずれかを選択してオプションを有効にします。

* **[!UICONTROL Select per activity]**&#x200B;では、各アクティビティの作成時に[!DNL Target]と[!DNL Analytics]のいずれかを選択できます。
* **[!UICONTROL Adobe Analytics]**&#x200B;は、作成するすべてのアクティビティのレポートソースとして[!DNL Analytics]を設定します。


