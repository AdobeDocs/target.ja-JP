---
keywords: serverstate;targetGlobalSettings;targetglobalsettings;globalSettings;globalsettings;global settings;at.js;functions;function;clientCode;clientcode;serverDomain;serverdomain;cookieDomain;cookiedomain;crossDomain;crossdomain;timeout;globalMboxAutoCreate;visitorApiTimeout;defaultContentHiddenStyle;defaultContentVisibleStyle;bodyHiddenStyle;bodyHidingEnabled;imsOrgId;secureOnly;overrideMboxEdgeServer;overrideMboxEdgeServerTimeout;optoutEnabled;optout;opt out;selectorsPollingTimeout;dataProviders;Hybrid Personalization;deviceIdLifetime
description: Adobe Target at.js JavaScript ライブラリの targetGlobalSettings() 関数について説明します。
title: targetGlobalSettings()
feature: at.js
translation-type: tm+mt
source-git-commit: 6bb75e3b818a71af323614d9150e50e3e9f611b7
workflow-type: tm+mt
source-wordcount: '1698'
ht-degree: 38%

---


# targetGlobalSettings()

[!DNL Target] Standard/Premium UI や REST API を使用して設定を構成する代わりに、`targetGlobalSettings()` を使用して at.js ライブラリで設定を上書きできます。

これは特に、設定の一部を上書きする場合に、at.js が [!DNL Dynamic Tag Management]（DTM）から配信されている場合におこなわれます。

## 設定 {#section_42C759AE9B524A43B8659018677224B8}

次の設定を上書きできます。

### bodyHiddenStyle

* **型**：String
* **デフォルト値**:body { opacity:0 }
* **説明**:ちらつきの発生を最小限 `globalMboxAutocreate === true` に抑える場合にのみ使用します。

   詳しくは、「[at.js によるちらつきの制御方法](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/manage-flicker-with-atjs.md)」を参照してください。

### bodyHidingEnabled

* **タイプ**:ブール値
* **デフォルト値**:true
* **説明**:ちらつきの制御に使用さ `target-global-mbox` れます。ちらつきの制御には、Visual Experience Composerで作成されたオファー(ビジュアルオファーとも呼ばれます)の配信に使用します。

### clientCode

* **型**：String
* **デフォルト値**:UIから設定された値。
* **説明**:クライアントコードを表します。

### cookieDomain

* **型**：String
* **デフォルト値**:可能であれば、トップレベルドメインに設定します。
* **説明**:Cookieの保存時に使用するドメインを表します。

### crossDomain

* **型**：String
* **デフォルト値**:UIから設定された値。
* **説明**:クロスドメイントラッキングが有効かどうかを示します。使用できる値は次のとおりです。無効、有効またはxのみ。

### cspScriptNonce

* **タイプ**:後述の「 [コンテンツセキュリティ](#content-security) ポリシー」を参照してください。
* **デフォルト値**:後述の「 [コンテンツセキュリティ](#content-security) ポリシー」を参照してください。
* **説明**:後述の「 [コンテンツセキュリティ](#content-security) ポリシー」を参照してください。

### cspStyleNonce

* **タイプ**:後述の「 [コンテンツセキュリティ](#content-security) ポリシー」を参照してください。
* **デフォルト値**:後述の「 [コンテンツセキュリティ](#content-security) ポリシー」を参照してください。
* **説明**:後述の「 [コンテンツセキュリティ](#content-security) ポリシー」を参照してください。

### dataProviders

* **タイプ**:以下の [データ](#data-providers) プロバイダーを参照してください。
* **デフォルト値**:以下の [データ](#data-providers) プロバイダーを参照してください。
* **説明**:以下の [データ](#data-providers) プロバイダーを参照してください。

### defaultContentHiddenStyle

* **型**：String
* **デフォルト値**:visibility:hidden
* **説明**:クラス名が「mboxDefault」であるDIVを使用し、デフォルトコンテンツを経由 `mboxCreate()`、または非表示にするmboxのラッピングにのみ使用 `mboxUpdate()`さ `mboxDefine()` れます。

### defaultContentVisibleStyle

* **型**：String
* **デフォルト値**:visibility:visible
* **説明**:クラス名が「mboxDefault」であるDIVを使用し、かつ、適用されたオファー（存在する場合）またはデフォルトのコンテンツを表示する、または経由 `mboxCreate()`で実行されるmboxのラッピングにのみ使用さ `mboxUpdate()` `mboxDefine()` れます。

### deviceIdLifetime

* **タイプ**:数値
* **デフォルト値**:63244800000 ms = 2年
* **説明**:cookieで持続 `deviceId` される時間。

>[!NOTE]
>
>deviceIdLifetime設定は、at.jsバージョン2.3.1以降で上書きできます。

### 有効

* **タイプ**:ブール値
* **デフォルト値**:true
* **説明**:有効にすると、エクスペリエンスを取得する [!DNL Target] 要求と、エクスペリエンスをレンダリングするDOM操作が自動的に実行されます。さらに、[!DNL Target]呼び出しは、`getOffer(s)` / `applyOffer(s)`を介して手動で実行できます。

   無効にした場合、[!DNL Target]リクエストは自動的にも手動でも実行されません。

### globalMboxAutoCreate

* **タイプ**:数値
* **デフォルト値**:UIから設定された値。
* **説明**:グローバルmboxリクエストを実行するかどうかを示します。

### imsOrgId

* **タイプ**:Sting
* **デフォルト値**:true
* **説明**:IMS ORG IDを表します。

### optoutEnabled

* **タイプ**:ブール値
* **デフォルト値**:false
* **説明**:ターゲットが訪問者API `isOptedOut()` 関数を呼び出す必要があるかどうかを示します。これは、デバイスグラフ有効化の一部です。

### overrideMboxEdgeServer

* **タイプ**:ブール値
* **デフォルト値**:true（at.jsバージョン1.6.2で始まる場合）
* **説明**:ドメインまたはドメ `<clientCode>.tt.omtrdc.net` インを使用する必要があるかどうかを示 `mboxedge<clusterNumber>.tt.omtrdc.net` します。

   この値がtrueの場合、`mboxedge<clusterNumber>.tt.omtrdc.net`ドメインはcookieに保存されます。 現在、at.js 1.8.2およびat.js 2.3.1より前のat.jsバージョンを使用する場合、[CNAME](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md)では動作しません。この問題が発生する場合は、[at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)を新しいサポート対象バージョンに更新することを検討してください。

### overrideMboxEdgeServerTimeout

* **タイプ**:数値
* **デフォルト値**:1860000 => 31分
* **説明**:その `mboxedge<clusterNumber>.tt.omtrdc.net` 値を含むcookieの有効期間を示します。

### pageLoadEnabled

* **タイプ**:ブール値
* **デフォルト値**:true
* **説明**:有効にすると、ページの読み込み時に返す必要のあるエクスペリエンスを自動的に取得します。

### secureOnly

* **タイプ**:ブール値
* **デフォルト値**:false
* **説明**:at.jsでHTTPSのみを使用するか、ページのプロトコルに基づいてHTTPとHTTPSとの切り替えを許可するかを示します。

### selectorsPollingTimeout

* **タイプ**:数値
* **デフォルト値**:5000 ms = 5 s
* **説明**:at.js 0.9.6では、を使用して上書きできる新しい設定が [!DNL Target] 導入され `targetGlobalSettings`ました。

   `selectorsPollingTimeout`設定は、セレクターによって識別されるすべての要素がページに表示されるまで、クライアントが待機する時間を表します。

   Visual Experience Composer（VEC）によって作成されたアクティビティには、セレクターが含まれたオファーがあります。

### serverDomain

* **型**：String
* **デフォルト値**:UIから設定された値。
* **説明**:ターゲットエッジサーバーを表します。

### serverState

* **タイプ**:以下の [ハイブリッド](#server-state) パーソナライゼーションを参照してください。
* **デフォルト値**:以下の [ハイブリッド](#server-state) パーソナライゼーションを参照してください。
* **説明**:以下の [ハイブリッド](#server-state) パーソナライゼーションを参照してください。

### timeout

* **タイプ**:数値
* **デフォルト値**:UIから設定された値。
* **説明**:エッ [!DNL Target] ジリクエストのタイムアウトを表します。

### viewsEnabled

* **タイプ**:ブール値
* **デフォルト値**:true
* **説明**:有効な場合、ページの読み込み時に返す必要のある表示を自動的に取得します。表示はat.js 2でサポートされています。*x* のみで使用できます。

### visitorApiTimeout

* **タイプ**:数値
* **デフォルト値**:2000 ms = 2 s
* **説明**: [!UICONTROL 訪問者] API要求のタイムアウトを表します。

## 使用方法 {#section_9AD6FA3690364F7480C872CB55567FB0}

この関数は、at.jsが読み込まれる前、または&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 実装]** > **[!UICONTROL at.js設定の編集]** > **[!UICONTROL コード設定]** > **[!UICONTROL ライブラリヘッダー]**&#x200B;に定義できます。

「ライブラリのヘッダー」フィールドでは、JavaScript を自由形式で入力できます。カスタマイズコードは次の例のようになります。

```javascript
window.targetGlobalSettings = {  
   timeout: 200, // using custom timeout  
   visitorApiTimeout: 500, // using custom API timeout  
   enabled: document.location.href.indexOf('https://www.adobe.com') >= 0 // enabled ONLY on adobe.com  
};
```

## データプロバイダー {#data-providers}

この設定では、Demandbase、BlueKai、カスタムサービスなどのサードパーティのデータプロバイダーからデータを収集し、そのデータをグローバル mbox リクエストで mbox パラメーターとして渡すことができます。非同期および同期リクエストを介した複数のプロバイダーからのデータ収集もサポートしています。この手法では、デフォルトのページコンテンツのちらつきを制御しながら、プロバイダーごとに個別のタイムアウトを指定し、ページのパフォーマンスへの影響を抑制することが簡単にできます。

>[!NOTE]
>
>データプロバイダーは、[!DNL at.js] 1.3 以降を必要とします。

詳細は次のビデオで説明されています。

| ビデオ | 説明 |
|--- |--- |
| [Adobe Target でのデータプロバイダーの使用](https://helpx.adobe.com/jp/target/kt/using/dataProviders-atjs-feature-video-use.html) | データプロバイダーは、サードパーティから Target へデータを簡単に渡すことのできる機能です。サードパーティとしては、気象予報サービス、DMP、自社の Web サービスなども利用可能です。このデータを利用して、オーディエンスやターゲットコンテンツを構築したり、訪問者プロファイルを充実させることができます。 |
| [Adobe Target でのデータプロバイダーの実装](https://helpx.adobe.com/jp/target/kt/using/dataProviders-atjs-technical-video-implement.html) | サードパーティデータプロバイダーからデータを回収し Target リクエストで渡す、Adobe Target のデータプロバイダー機能の使用方法の実装詳細と例。 |

`window.targetGlobalSettings.dataProviders` 設定は、データプロバイダーの配列です。

各データプロバイダーの構造は次のとおりです。

| キー | タイプ | 説明 |
|--- |--- |--- |
| name | 文字列 | プロバイダーの名前。 |
| version | 文字列 | プロバイダーのバージョン。このキーはプロバイダーの展開に使用されます。 |
| timeout | 数値 | ネットワークリクエストの場合は、プロバイダーのタイムアウトを表します。このキーはオプションです。 |
| provider | 関数 | プロバイダーデータの取得ロジックを含む関数。<br>この関数の必須パラメーターは `callback` のみです。この callback パラメーターは、データを適切に取得した場合またはエラーが発生した場合にのみ呼び出す必要があります。<br>このコールバックは、次の 2 つのパラメーターを受け取ります。<ul><li>error：エラーの有無を表します。エラーがない場合、このパラメーターは null に設定されます。</li><li>params：Target リクエストで送信されるパラメーターを表す JSON オブジェクト。</li></ul> |

データプロバイダーで同期実行を使用する場合の例は次のとおりです。

```javascript
var syncDataProvider = { 
  name: "simpleDataProvider", 
  version: "1.0.0", 
  provider: function(callback) { 
    callback(null, {t1: 1}); 
  } 
}; 
  
window.targetGlobalSettings = { 
  dataProviders: [ 
    syncDataProvider 
  ] 
};
```

at.js によって `window.targetGlobalSettings.dataProviders` が処理されると、Target リクエストには `t1=1` という新しいパラメーターが含まれます。

Target のリクエストに追加するパラメーターを、BlueKai、Demandbase などのサードパーティサービスから取得する場合の例は次のとおりです。

```javascript
var blueKaiDataProvider = { 
   name: "blueKai", 
   version: "1.0.0", 
   provider: function(callback) { 
      // simulating network request 
     setTimeout(function() { 
       callback(null, {t1: 1, t2: 2, t3: 3}); 
     }, 1000); 
   } 
} 
  
window.targetGlobalSettings = { 
   dataProviders: [ 
      blueKaiDataProvider 
   ] 
};
```

at.js によって `window.targetGlobalSettings.dataProviders` が処理されると、Target のリクエストには、`t2=2`、`t1=1`、および `t3=3` という追加パラメーターが含まれます。

次の例では、データプロバイダーを使用して weather API データを取得し、Target リクエストでパラメーターとして送信します。Target リクエストには、`country`、`weatherCondition` などのパラメーターも追加されます。

```javascript
var weatherProvider = { 
      name: "weather-api", 
      version: "1.0.0", 
      timeout: 2000, 
      provider: function(callback) { 
        var API_KEY = "caa84fc6f5dc77b6372d2570458b8699"; 
        var lat = 44.426767399999996; 
        var lon = 26.1025384; 
        var url = "//api.openweathermap.org/data/2.5/weather?lang=en"; 
        var data = { 
          lat: lat, 
          lon: lon, 
          appId: API_KEY 
        } 
 
        $.ajax({ 
          type: "GET", 
                url: url, 
          dataType: "json", 
          data: data, 
          success: function(data) { 
            console.log("Weather data", data); 
            callback(null, { 
              country: data.sys.country, 
              weatherCondition: data.weather[0].main 
            }); 
          }, 
          error: function(err) { 
            console.log("Error", err); 
            callback(err); 
          } 
        });         
      } 
    }; 
 
    window.targetGlobalSettings = { 
      dataProviders: [weatherProvider] 
    };
```

`dataProviders` 設定を使用する際は、次の点に注意してください。

* `window.targetGlobalSettings.dataProviders` に追加されたデータプロバイダーが非同期の場合は、同時並行で実行されます。訪問者 API リクエストは、待ち時間を最小限に抑えるために、`window.targetGlobalSettings.dataProviders` に追加された関数と同時に実行されます。
* at.js では、データはキャッシュされません。データプロバイダーが 1 回だけデータを取得する場合は、データをキャッシュし、そのプロバイダーの関数が呼び出されたら、2 回目の呼び出しでキャッシュデータを配信できるようにする必要があります。

## コンテンツセキュリティポリシー{#content-security}

at.js 2.3.0以降では、配信されたターゲットオファーを適用する際に、ページDOMに追加されたSCRIPTタグとSTYLEタグに対するコンテンツセキュリティポリシーノンスの設定をサポートしています。

at.js 2.3.0以降の読み込みの前に、対応して`targetGlobalSettings.cspScriptNonce`と`targetGlobalSettings.cspStyleNonce`にSCRIPTとSTYLEのnoncesを設定する必要があります。 以下の例を参照してください。

```javascript
...
<head>
 <script nonce="<script_nonce_value>">
window.targetGlobalSettings = {
  cspScriptNonce: "<csp_script_nonce_value>",
  cspStyleNonce: "<csp_style_nonce_value>"
};
 </script>
 <script nonce="<script_nonce_value>" src="at.js"></script>
...
</head>
...
```

`cspScriptNonce`と`cspStyleNonce`の設定を指定した後、at.js 2.3.0+は、ターゲットオファーを適用する際にDOMに追加するすべてのSCRIPTタグとSTYLEタグに、これらをnonce属性として設定します。

## ハイブリッドパーソナライゼーション{#server-state}

`serverState` は、at.js v2.2以降で利用できる設定です。ターゲットのハイブリッド統合が実装されている場合、ページのパフォーマンスを最適化するために使用できます。ハイブリッド統合とは、クライアント側でat.js v2.2以降と、配信APIまたはサーバー側でターゲットSDKの両方を使用してエクスペリエンスを提供することです。 `serverState` では、at.js v2.2以降で、サーバー側でフェッチしたコンテンツからエクスペリエンスを直接適用し、提供されるページの一部としてクライアントに返す機能が提供されます。

### 前提条件

[!DNL Target]のハイブリッド統合が必要です。

* **サーバー側**:新しい [配信APIまたは](https://developers.adobetarget.com/api/delivery-api/) ターゲットSDKを使用する必要があります [](https://developers.adobetarget.com/api/delivery-api/#section/SDKs)。
* **クライアント側**:at.jsバージョン2.2以降 [を使用する必要があります](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)。

### コードサンプル

この仕組みをより深く理解するために、お使いのサーバーにある以下のコード例をご覧ください。 このコードでは、[ターゲットNode.js SDK](https://github.com/adobe/target-nodejs-sdk)を使用していることを前提としています。

```javascript
// First, we fetch the offers via Target Node.js SDK API, as usual
const targetResponse = await targetClient.getOffers(options);
// A successfull response will contain Target Delivery API request and response objects, which we need to set as serverState
const serverState = {
  request: targetResponse.request,
  response: targetResponse.response
};
// Finally, we should set window.targetGlobalSettings.serverState in the returned page, by replacing it in a page template, for example
const PAGE_TEMPLATE = `
<!doctype html>
<html>
<head>
  ...
  <script>
    window.targetGlobalSettings = {
      overrideMboxEdgeServer: true,
      serverState: ${JSON.stringify(serverState, null, " ")}
    };
  </script>
  <script src="at.js"></script>
</head>
...
</html>
`;
// Return PAGE_TEMPLATE to the client ...
```

表示プリフェッチ用のサンプル`serverState`オブジェクトJSONは次のようになります。

```
{
 "request": {
  "requestId": "076ace1cd3624048bae1ced1f9e0c536",
  "id": {
   "tntId": "08210e2d751a44779b8313e2d2692b96.21_27"
  },
  "context": {
   "channel": "web",
   "timeOffsetInMinutes": 0
  },
  "experienceCloud": {
   "analytics": {
    "logging": "server_side",
    "supplementalDataId": "7D3AA246CC99FD7F-1B3DD2E75595498E"
   }
  },
  "prefetch": {
   "views": [
    {
     "address": {
      "url": "my.testsite.com/"
     }
    }
   ]
  }
 },
 "response": {
  "status": 200,
  "requestId": "076ace1cd3624048bae1ced1f9e0c536",
  "id": {
   "tntId": "08210e2d751a44779b8313e2d2692b96.21_27"
  },
  "client": "testclient",
  "edgeHost": "mboxedge21.tt.omtrdc.net",
  "prefetch": {
   "views": [
    {
     "name": "home",
     "key": "home",
     "options": [
      {
       "type": "actions",
       "content": [
        {
         "type": "setHtml",
         "selector": "#app > DIV.app-container:eq(0) > DIV.page-container:eq(0) > DIV:nth-of-type(2) > SECTION.section:eq(0) > DIV.container:eq(1) > DIV.heading:eq(0) > H1.title:eq(0)",
         "cssSelector": "#app > DIV:nth-of-type(1) > DIV:nth-of-type(1) > DIV:nth-of-type(2) > SECTION:nth-of-type(1) > DIV:nth-of-type(2) > DIV:nth-of-type(1) > H1:nth-of-type(1)",
         "content": "<span style=\"color:#FF0000;\">Latest</span> Products for 2020"
        }
       ],
       "eventToken": "t0FRvoWosOqHmYL5G18QCZNWHtnQtQrJfmRrQugEa2qCnQ9Y9OaLL2gsdrWQTvE54PwSz67rmXWmSnkXpSSS2Q==",
       "responseTokens": {
        "profile.memberlevel": "0",
        "geo.city": "dublin",
        "activity.id": "302740",
        "experience.name": "Experience B",
        "geo.country": "ireland"
       }
      }
     ],
     "state": "J+W1Fq18hxliDDJonTPfV0S+mzxapAO3d14M43EsM9f12A6QaqL+E3XKkRFlmq9U"
    }
   ]
  }
 }
}
```

ページがブラウザーに読み込まれた後、at.jsは、[!DNL Target]エッジに対するネットワーク呼び出しを実行せずに、`serverState`からのすべての[!DNL Target]オファーを直ちに適用します。 また、at.jsは、サーバーサイドで取り込んだコンテンツで[!DNL Target]オファーが使用可能なDOM要素のみを事前に非表示にし、ページ読み込みのパフォーマンスとエンドユーザーエクスペリエンスに良い影響を与えます。

### 重要な注意事項

`serverState`を使用する場合は、次の点を考慮してください。

* 現時点で、at.js v2.2は、次のエクスペリエンスをserverState経由でのみ配信できます。

   * ページの読み込み時に実行されるVECで作成されたアクティビティ。
   * 事前に取得された表示。

      at.js APIで[!DNL Target]表示と`triggerView()`を使用するSPAの場合、at.js v2.2は、サーバー側でプリフェッチされたすべての表示のコンテンツをキャッシュし、`triggerView()`を介して各表示がトリガーされると同時に、ターゲットへの追加のコンテンツ取得呼び出しを実行せずに適用します。

   * **注意**:現在、サーバー側で取得されたmboxは、ではサポートされていません `serverState`。

* `serverState `オファーを適用する場合、at.jsでは`pageLoadEnabled`と`viewsEnabled`の設定(例：`pageLoadEnabled`設定がfalseの場合、ページ読み込みオファーは適用されません)を考慮します。

   これらの設定をオンにするには、**[!UICONTROL 管理]/[!UICONTROL 実装]/[!UICONTROL 編集]/[!UICONTROL ページ読み込みが有効]**&#x200B;で切り替えます。

   ![ページ型設定](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/page-load-enabled-setting.png)

* `serverState`を使用し、返されるコンテンツで`<script>`タグを使用する場合は、HTMLコンテンツで`</script>`ではなく`<\/script>`を使用していることを確認してください。 `</script>`を使用すると、ブラウザーは`</script>`をインラインスクリプトの最後と解釈し、HTMLページを壊す場合があります。

### その他のリソース

`serverState`の仕組みを詳しく知るには、以下のリソースを調べてください。

* [サンプルコード](https://github.com/Adobe-Marketing-Cloud/target-node-client-samples/tree/master/advanced-atjs-integration-serverstate).
* [単一ページアプリ(SPA)サンプルアプリを使用 `serverState`](https://github.com/Adobe-Marketing-Cloud/target-node-client-samples/tree/master/react-shopping-cart-demo)します。
